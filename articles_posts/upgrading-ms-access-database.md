---
permalink: /articles/upgrading-ms-access-database
head-title: Upgrading or converting MS Access 2000, 2003 or 2007
head_description: How to convert Access 2003 and 2007 database files in .mdb format to the .accdb format or just get the .mdb file format to run in the latest version of Access.
---


# How to convert or upgrade an MS Access application

This article describes a  best practice procedure for converting or upgrading an old MS Access database application. If you need help with upgrading I'm happy to offer a free assessment of your application so please [get in touch](/ms-access-upgrade). This procedure can be used to:

- Convert Access 2000 or 2003 .mdb to .accdb for use in 2013, 2016, 2019 and Microsoft 365.
- Convert Access 2007 .mdb to .accdb for use in 2013, 2016, 2019 and Microsoft 365.
- Get Access 2000, 2003 and 2007 .mdb to run in 365 when User Level Security or replication is used

## Notes

- April 2014 marked Microsoft’s end of development support for Access 2003 and its .mdb file format. That means there are no more automatic upgrades and patches making an Access 2003 database a potential security risk.

- If you use User Level Security or replication then you need to keep using the old .mdb file format.

- When upgrading from .mdb to .accdb Microsoft recommend using Access 2016 to do the initial conversion. This is because features needed to upgrade the older formats are deprecated in later versions of Access. This can lead to the conversion process completing without any apparent errors when in fact something did go wrong which doesn't become apparent until some time later. If you don't have MS Access 2016 you can use 2010 or 2013 instead.
After you have converted to 2016 (or 2010 or 2013) you can upgrade to 365.

- If when converting from 2003 or 2007 you find straight off that the .mdb file won't open then you will have to convert using 2010 then upgrade to 365.

**Keeping .mdb file format?** Go straight to the upgrade/conversion steps

**Converting to .accdb?** Convert to 2016 first by following the upgrade/conversion steps then repeat the steps to upgrade to the latest version. If that application fails to open in 2016 and you cant find a reason for it convert to 2010 then upgrade to the latest version.

## Prerequisite

The database should be split into its two components meaning the backend (BE) which is all the data (tables) and the frontend (FE) which is everything else i.e. all the code, forms, reports, queries and macros.

## Upgrade/conversion steps

**Step 1.** Make a copy of the backend and frontend so that they are backed up and safe.

**Step 2.** Open up the application in the latest version of Access and then save it. You will either save it in .accdb format or if you are using User Level Security just save it again in .mdb format.

**Step 3.** Delete old backup copies of your forms and reports. If you look at your forms and reports you may find quite a few backup copies of old versions. It will be obvious from the name that they are backup copies.  You don't want to waste time converting these especially if there is VBA code behind them so now is the time to delete them. If in doubt do not delete! Before deleting anything it's good practice to make a list of everything you intend to delete and then ask everyone who uses the application if there is anything on the list that shouldn't be deleted. Once you're happy go ahead and delete them. You always have a backup copy should you find at a later date that you deleted something that you still in fact need.

**Step 4.** Clean up the code as follows:

- All variables should be declared. To ensure this is the case add the following line to the top of every Class Object and Module: `Option Explicit`

- Check the error handling. Some code may have poor error handling meaning that when some errors occur they are just silently caught and ignored. This makes it very difficult to see what or why something isn't working. Prior to a conversion check the error handling and make sure no errors are just silently caught. If you're not sure what to do then at least log the error.

**Step 5.** Check the VBA reference libraries and use the latest libraries. You will certainly need to update the MS Office libraries if your application uses Word or Excel.

**Step 6.** Compile the VBA code and fix all compilation errors. This is the first real upgrade step as you are getting the old code to compile in the latest version of Access. Yey!

**Step 7.** Fix the queries.

**Step 8.** Fix the macros

**Step 9.** Run Compact and Repair

**Step 10** Finally run the application, give it a thorough testing and fixed any issues. Pay attention to the data that is displayed. Sometimes at a casual glance it seems ok but if you look closely you may find a filter has not been applied or the order is wrong. In fact you should compare the new version with the old version to confirm they both display the same data.

## Common problems

### Unsupported 3rd party dll's

You may be using 3rd party dlls that aren't supported anymore. Hopefully they will still work. If not you will have to be creative and find an alternative way of doing whatever isn't working anymore.

### Runtime error 13 type mismatch

VBA Access projects default to ADO when DAO is not explicitly specified. This can result in an error 13 being thrown and/or slowness. The fix is to explicitly specify DAO throughout.

### Error 3845

Access does not support linking to Access database or Excel worksheet  saved in a format that is a later version than the current database format. Solution: search the code for the creation of any temporary database tables and update the jet engine file format accordingly
