---
permalink: /articles/ms-access-database
head-title: Is MS Access still being used?
head_description: MA Access is still going strong but you might want to upgrade to SQL Server
---

![MS Access Databse](/assets/images/ms-access.jpg)

# Is MS Access still being used?

Microsoft still have a lot of love for MS Access. They recognise it as being fantastic for developing robust and very powerful desktop applications. So if you've got an MS Access desktop application you certainly want to keep it. Great stuff!

## Limitations of MS Access
MS Access is not scalable. For example it is limited to being 2GB in size which these days isn't that much. So if you've got plans for growth you need to think 
about moving the database backend to SQL Server and have it hosted in the cloud.

What is the database backend?
The desktop database application is in two parts. There is the front end which is all the stuff you see visually and interact with e.g the reports, forms, queries etc. and there is the backend which is the data and data engine ie the actual database. The backend can change from MS Access to SQL Server leaving your front end untouched. 

Assuming you have upgraded your Access database to the latest version then 


You split the database into FE and BE. Migrate the back end data to SQL server and the FE end application, all the reports, forms, queries, macros etc will now effectively connect to SQL server backend. You will still have the rapid application development that Access provides but with the scalability of SQL server which is running in the (Azure) a cloud. SQL server can run on your own server but very rarely is that necessary these days. Host it in the cloud!!!!


## Why upgrade to SQL Server?

### Scalable in size
Whereas Access is limited to 2GB in size there is no limit with SQL Server

### Back it up while it's still be used
You dont have to tell everyone to stop using it because you're going to back it up.

### Faster
SQL Server processes queries much faster and efficiently

### Improved security
SQL Server integrates with Windows system security and unlike Access it is designed to securely store confidential information. 

### Less need for database administration.
If the SQL server database falls over (crashes), it can automatically recover and become available again in a matter of minutes.  

### SQL Server runs in the cloud 
You can purchase SQL Server and run it on your own server but in most cases these days you want to have it hosted in the cloud

#### Benefits of having SQL Server in the cloud (Azure)
- No downtime
- No hardware costs
- Reduced administration

## Jump into cloud!
If you've got an MS Access database running on a computer in your office it's time to get your database into the cloud. Contact us to see how we can help you do this.
