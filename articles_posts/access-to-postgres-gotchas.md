---
permalink: /access-to-progress-problems
head-title: Problems Converting Microsoft Access to PostgreSQL
head_description: Common problems that need to be worked around when migrating from Microsoft Access to PostgreSQL.
---

# Problems Converting Microsoft Access to PostgreSQL

## How to perform the initial schema and data migration

The first thing you need to do is get the schema and data out of the Access database and into Postgres. Bullzip have a free and simple [Access to PostgreSQL](https://www.bullzip.com/products/a2p/info.php) tool to do this. Its best to  dump the schema to SQL script because then you can edit the SQL as needed using a simple text editor. Once the initial schema is successfully imported into PostgreSQL you can migrate the data over. Again you can dump the data to SQL script first or if there is a lot of data the bullzip tool usually does a good job of migrating it directly using ODBC.

## Common problems and gotchas

### PostgreSQL requires primary keys

You may very well find that some (or quite a few!) tables in Access do not have a primary key defined. You will have to specify one in the corresponding PostgreSQL table. If you can't find a suitable candidate then generate one.

### Access prefixes the schema to the tables

When Access links to the tables in PostgreSQL it prefixes the schema name to the table name. You will have to remove it. This isn't a problem if you programmatically link to the tables on Access application startup because then you can specify what the correct table names are.

### Boolean incompatibility

Boolean incompatibility is a common problem and a real pain when migrating from one database system to another. PostgreSQL has a true boolean data type where as MS Access has Yes/No which is mapped internally to  -1 and 0. This leads to teh following error message being displayed:

``
operator does not exist boolean = integer
``

A solution to boolean incompatibility can be found here:
[The Access ODBC PostgreSQL boolean mess - Bahut](http://bahut.alma.ch/2006/04/access-odbc-postgresql-boolean-mess.html) although instead of using plpgsql functions I use plain sql functions instead as they perform much better and are more transparent to the PostgreSQL query planner.

### PostgreSQL is case sensitive

Postgres is case sensitive where as MS Access is case insensitive. This means that searching on forms does not return the expected results. You cannot re-train MS Access users to be mindful of capital letters so you have set up Postgres to make it case insensitive. This is not so straight forward.

#### Solution

1. Use the lower() function for comparisons in conjunction with a functional index. You need the functional index otherwise Postgres will use a sequential scan for matching.

2. (Deprecated) Pull in the citext module.

3. Use collation

In  practice you will use non-deterministic collation for <, <=, >, or >= comparisons but for pattern matching queries such as Like the non-deterministic collation will not work resulting in the error:

`
ERROR:  nondeterministic collations are not supported for LIKE
`

so for pattern matching queries you have to override the non-deterministic collation with a deterministic collation and use a functional index.

### Updates are really slow

Access does some crazy stuff behind scenes. For example with a SELECT statement with a WHERE clause Access retrieves all the records from a table and then it applies the WHERE clause. Similarly a simple UPDATE statement which updates all the records actually results in Access selecting each record and then updating it. You can see the crazy stuff going on by monitoring the ODBC connection and the Postgres log. All this may be just about acceptable in a pure desktop environment but when the communication is to a remote database server then its too slow and also it's expensive

#### Solution

Re-engineer the relevant queries and use Pass Through Queries.

### Bulk maintenance and update operations take forever or crash

All bulk operations and maintenance tasks should be done on the Postgres server. Access isn't designed to do those sort of tasks anyhow. This means creating stored procedures and setting up cron jobs when applicable. All good stuff!
