---
date: 2019-12-17
permalink: /blog/js/firebase-nodemailer-free-account
linktitle: Sending email from Node functions in Firebase free tier
title: Sending email from Node functions in Firebase free tier
weight: 10
---

To send emails from your Firebase functions you need to use Nodemailer and a gmail account. You cannot use the SMTP server for your domain. 

When nodemailer is configured to use a gmail address you may still get the following error but its just a warning and can be ignored

>Billing account not configured. External network is not accessible and quotas are severely limited. >Configure billing account to remove these restrictions.


Many examples give the following instructions for setting up nodemailer to use your gmail account

```javascript
const transporter = nodemailer.createTransport({
service: 'gmail',
auth: {
    user: gmailEmail,
    pass: gmailPassword
}
});
```

You also have to change a setting in your gmail account to allow unsafe apps. Once you do that your function will send emails. 

It works! 

Wonderful. 

Then it stops working :(

If gmail detects suspicious activity with your gmail account it starts blocking and restricting access. Thats when you'll find that your functions can no longer send emails.

### When it stops working what do you do?
You have to send email securely using OAuth2. Unfortunately when you do a Google on how to do this you will quickly find yourself wading through loads of tutorials and stackoverflow answers and all of them say something different and all of them look really complicated. However someone has gone to the trouble of dong a step by guide. Its rather involved but the steps are precise and correct. Once you've done it you will magically be able to send emails from your firebase Node functions without any problems (using your gmail account) [>>>>>>Article is Here<<<<<](https://www.woolha.com/tutorials/node-js-send-email-using-gmail-with-nodemailer-oauth-2)


