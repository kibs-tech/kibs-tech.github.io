---
permalink: /articles/oracle-to-postgres-problems
head-title: Oracle to PostgreSQL Migration Notes
head_description: Problems t0 look for when migrating from Oracle to PostgreSQL.
---

# Oracle to PostgreSQL Migration Notes

These are notes for migrating Oracle to PostgreSQL.

The best approach is to export the schema to an SQL file and then write a script to process the SQL and change it to make it PostgreSQL compliant.  The script can then be applied to other schemas.

Similarly a script is created to edit the PLSQL procedures and convert them to PL/pgSQL.  This works surprisingly well without the need for much re-implementation.

## Schema

- PostgreSQL does not like VARCHAR2(100 CHAR). Replace with VARCHAR

- Remove ordered="false" from CreateSequence statements (Postgres does not allow it).

- Oracle export file has REM lines. These cause error in Postgres. Delete them.  

- SET DEFINE OFF;  This causes an error in Postgres. Delete it.

## Functions and procedure

- In oracle we have:

`
DECLARE CURSOR current_name_cur
`

but in Postgres it must be:

`
DECLARE current_name_cur CURSOR
`

- Replace VARCHAR2 with VARCHAR

- Replace SYS_REFCURSOR with REFCURSOR

- Oracle SYSDATE returns the date and time on the server where the database instance is
running. Postgres equivalent is CURRENT_TIMESTAMP

## Problems with data import

- Sequences are different:

insert into table_a (id, username, GROUP_ID) values 

`
(ID_SEQ.nextval,'blah',3201);
`

becomes:

`
insert into table_a (id, username, GROUP_ID) values (nextval('ID_SEQ'),'blah',3201);
`

- Remember to change the hibernate dialect

- Some ids which are sequences are strings and have junk in them. When determining what to set the sequence to (normally max(id)+1 you need to ignore the junk and manually insert a value

- Change statements like this:

`
SELECT COUNT(ID) FROM TABLE_A cm WHERE cm.ROLE_ID = this_.id
`

to

`
SELECT COUNT(*) FROM TABLE_A cm WHERE cm.ROLE_ID = this_.id
`

- It's `deleted = '0'` not `deleted = 0`

- With `getJdbcTemplate().query` use ? not named parameters (will throw a Column index out of range  exception) 

## Hibernate

- The optional clause MAXVALUE  determines the maximum value for the sequence. If this clause is not supplied or NO MAXVALUE is specified, then default values will be used. The defaults are 263-1 and -1 for ascending and descending sequences, respectively.
