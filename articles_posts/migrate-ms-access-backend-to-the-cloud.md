---
permalink: /articles/microsoft-access-and-the-cloud
head-title: Microsoft Access and the Cloud
head_description: A strategy for getting an Microsoft Access database into the cloud
---

<nav aria-label="breadcrumb">
  <ol class="breadcrumb">
    <li class="breadcrumb-item"><a href="/">Services</a></li>
    <li class="breadcrumb-item"><a href="/database-developer">Database Application Development</a></li>
    <li class="breadcrumb-item active" aria-current="page">Microsoft Access and the Cloud</li>
  </ol>
</nav>

<div class="splash-back splash-back-cloud">
           <div class="splash-back-overlay">

            <h1>Microsoft Access and the Cloud</h1>
        

        </div>
        </div>



<!-- # Microsoft Access and the Cloud

![](/assets/images/cloud.png) -->

## What's the cloud got to do with Microsoft Access

<p class="center" style=""><em>The cloud is the future of computing. Get into the cloud or get left behind.</em></p>

Microsoft still fully support Access. They have wobbled over it a fair bit though. They tried to make it work with the web but then abandoned that idea. Now they're left with a dated desktop application format but one they recognise is still popular for quickly developing robust and powerful database applications that are also easily integrated with other Microsoft Office applications. So if you've got an old MS Access desktop application you certainly don't need to be replacing it but you really should be upgrading it and even more than that thinking about moving the database backend into the cloud.

## What is the database backend

A Microsoft Access application is comprised of two components. There is the frontend which is basically all the things you see visually (forms, reports etc) and there is the backend which is the actual data. In a typical office setup the Access backend is on a server somewhere and everyone's computer connects up to it.

## What does it mean to move the backend into the cloud

It means moving the data from your Access database which is on your local office network and putting it into a database that is in the cloud. The frontend application remains on your office computers and works just the same as it does now.

You can't put your Access database in the cloud. Instead you have to use another database. Microsoft  recommend moving the backend from Access to their enterprise grade database called SQL Server. They call it upsizing. The problem with this is that SQL server is expensive. The good news is that you can use many other databases instead and a great choice is PostgreSQL. PostgreSQL is licence free and is a popular database amongst none Microsoft developers.

## Why would I want to move the backend into the cloud

### Reason 1

Below are just some of the things you gain from having the database taken off your hands and hosted by the experts

- No downtime
- No hardware costs
- Reduced database administration
- Scalable in size
- Automatic backups and data retention.
- Improved security
- Upgrades taken care of

### Reason 2

When you move the backend database into the cloud the Microsoft Access frontend continues to work exactly like it does now. However you can now share your data securely with other application services and also access your data on mobile and web apps. Basically your data will become accessible anytime, from anywhere and on any device. The possibilities for future technical growth are literally endless.

## Common objections to moving the database into the cloud

### The data is confidential and needs to be secure not on the internet

Your data in the cloud will be more secure than the data is sitting on a networked server in your office. Have you ever had a malware scare? In the cloud you are using the same infrastructure as the credit card companies and the Inland Revenue. Thats pretty secure! All access to your database is authenticated and over SSL and you have complete control over who has access to the database just as you do with the database in your office.

### The data is just for the business, it will never be displayed publicly

Being able to share your data with mobile and web apps is not just about displaying it to the public. It's also required for modern internal business only and B2B applications. Imagine being able to view and edit at least some of your data whilst out of the office. You probably already exchange data with other external services such as CMS and analysis applications and the only way you can do what with an Access database is to export and import data in the form of manual entry or data files such as Excel or csv. Furthermore every time you export your data somewhere you are exposing it and you should also make sure that you're not breaching the requirements of the Data Protection Act and various auditing bodies.

## Signs not being in the cloud is holding you back

- You've had a mobile app developed
- You have a public facing website
- You wish you could do some 'stuff' on your mobile or tablet
- You're on the look out for growth opportunities
- Your software looks old and tired and is not very nice to use
- You are manually sharing data between applications
- You have got notes in various places reminding you to update "that" if you change "this"
- You are exporting data and sending it elsewhere

## For the more technically minded

You are migrating from this legacy system

<div style="background-color:white; text-align:center; padding-bottom:1rem">
<img src="/assets/images/your-office-access.png" title="Microsoft access database on a server on a LAN" alt="Microsoft access database on a server on a LAN"/>
<p><b>Your database and data is imprisoned in the office -  just like you.</b></p>
</div>

to a modern system

<div style="background-color:white; text-align:center;padding-bottom:1rem">
<img src="/assets/images/migrated-access.png" style="width:100%" title="Putting a Microsoft Access database into the cloud" alt="Putting a Microsoft Access database into the cloud"/>
<p><b>Your data is secure but it is now also available to mobile and web apps.</b></p>
</div>


## That looks very complicated and very expensive

Well it's not as complicated as it probably looks and depending on the size and the current state of the Access database it need not be expensive. It is an investment though but its an investment in the future.

## How long does it take

There are actually 4 stages along the path to moving your data into the cloud. At the end of each stage you will have a new improved modernised useable product

### Stage 1

- Upgrade Access frontend to the latest version

### Stage 2

- Migrate the backend to PostgreSQL database
- Implement user security rules

### Stage 3

- Move the PostgreSQL database into the cloud

### Stage 4

- Implement an showcase basic read only web app page

## Jump into the cloud!

Im already excited about getting you into the cloud so please contact me for a free assessment and lets see what we can do.

[Contact Me](/contact)

