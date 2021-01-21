---
permalink: /articles/future-options-for-old-ms-access-database
head-title: Options to future proof an MS Access database application
head_description: MS Access is still supported but what can you do to future proof your database application especially if you have an application that was built many years ago. 
---


# What can be done to future proof MS Access database applications

MS Access is still supported by Microsoft but what can you do to future proof your database application especially if you have an application that was built many years ago.

## Don't do anything

Some Access database applications have grown so big over the years and have been coded in such a complex and tightly coupled manner that even upgrading may not be possible. It such cases either leave it as it is or to do a re-write. A re-write is not a trivial undertaking but an audit of the application will determine what areas of the application are actually still used and what data can be archived off without being migrated over to a new system. In other words an audit often results in a much leaner application that is significantly easier to re-write. Furthermore if a modern data centric application builder is used a re-write may be quite an attractive proposition.

## Keep it as is but upgrade to latest version of Access

If you are quite happy with your desktop application and you really see no need to ever want to access the data from other applications such as a web or mobile app then just upgrade it to the latest version of Access and carry on using it.

## Move it off your premises and have it hosted remotely

Desktop as a service or DaaS has really taken off in recent years thanks to Amazon and Google providing hosting infrastructure for it. DaaS is a virtual desktop infrastructure (VDI) hosted in the cloud and paid for as a subscription service. It enables you to access everything on your desktop from wherever you are and from any device with an internet connection. It can be quite expensive though for a small business.

## Keep the frontend as it is but migrate the backend to a cloud based database

The backend (BE) does not need to be an Access database. It can be another database and that  database can be hosted in the cloud which is really exciting as it opens up access to your data to all sorts of applications. Microsoft actually encourage moving the BE away from Access. They call it upsizing. They would like you to use SQL Server running in Azure which is Microsoft's cloud but you can use other database servers. I use PostgreSQL. PostgreSQL is licence free making it much cheaper than SQL server and it is a big favourite amongst developers outside the Microsoft community. I was once tasked with moving a suite of applications for a big non-profit organisation from using an in-house hosted Oracle database server to a cloud hosted PostgreSQL database. PostgreSQL is a serious heavy weight amongst database servers but it is entirely appropriate for small applications and small budgets as well.

## Re-write and move away from MS Access completely

This means replacing the desktop application with a cloud based web application. Modern day quick build no coding solutions mean this need not necessarily be a such an expensive or time consuming undertaking.

### Some web application alternatives to MS Access

#### [Microsoft Power Apps](https://powerapps.microsoft.com/)

Microsoft encourage using PowerApps to develop data centric business applications. However building PowerApp applications is complicated and really needs for a Microsoft developer making it all quite expensive.

#### [Quick Base](https://quickbase.com)

Quick Base claims to be zero code and easy to use but their minimum payment plan is several hundred dollars a month. That makes it too expensive for a small business requiring only a minimum level plan. They also don't offer a free developer account (although they might do if you ask nicely.

#### [Caspio](https://caspio.com)

Caspio has a range of usage plans making it cheaper and more accessible than other no code application builders. At the top most level it requires no coding knowledge and non-technical people can create reports etc just by using drag and drop. From a developers perspective they offer a very flexible framework with API'S, webpage and mobile plug and play functionality.

### A cost effective efficient strategy for the initial re-write

The simplest re-write strategy is a one-to-one translation. This is when each process as it currently is in Access is re-implemented on the new platform. Once the new app has been rolled out and users are comfortable with the new interface, you can start making improvements to suit the business needs. This approach is recommended because the limited scope of change simplifies migration and shortens the time frame.
