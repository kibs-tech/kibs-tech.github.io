---
permalink: /blog/js
head-title: KibsTech Blog - A React and Better JS Journey

---
    
# KibsTech Blog - A React and Better JS Journey

This is not a collection of nicely written tutorials. It's a collection of notes and interesting observations that I make as I journey along the JavaScript Full Stack path.

**[How to do implement pagination in NextJS with Firestore](/blog/js/pagination-with-firestore-in-nextjs)**  
You're using NextJS and are generating lovely html pages. At some point you'll want to implement pagination [Read more](/blog/js/tut-tut-react-bootstrap) 

**[Careful: React Bootstrap Nav is bad for SEO](/blog/js/tut-tut-react-bootstrap)**  
Quickie: Bad React Bootstrap.

**[Nextjs and how to get query params in getServerSideProps](/blog/js/nextjs-query-param-getserversideprops)**  
Quickie: How to get the url query parameters in getServerSideProps

**[Mock out the API service layer using the Factory design pattern](/blog/js/mock-out-api-service-layer-using-the-factory-design-pattern)**  
Your React app is going to make api calls to some service that resides on a server somewhere. As a minimum in real world dev environments there will probably be a server for development, a server for testing and a server for live. Obviously that's just one simple hardware architecture example in the dev, test, build and deployment path. A well designed React app should isolate api calls into a service layer [Read more](/blog/js/mock-out-api-service-layer-using-the-factory-design-pattern)
  
 **[Various problems with Expo, React Native, Native Base](/blog/js/problems-with-expo-and-react-native)**  
 Error starting Expo:

`Could not get status from Metro bundler. connect ECONNREFUSED 127.0.0.1:1900`

[Read more](/blog/js/problems-with-expo-and-react-native)

**[onChange with Formik](/blog/js/formik)**  
You are using Formik and you want to add an onChange handler to a form field
Problem You can't. The formik form will stop working. Why is not important for this blog entry.
What googling reveals Google the problem and you'll find lots and lots of people quite upset that they can't 
implement their own onChange handler. There have been many requests for this to be supported and all of the requests have been closed. [Read more](/blog/js/formik)

**[The Joys of Hooks in React](/blog/js/hooks-in-react)**  
I'm not going to write a tutorial on how to use hooks. This is a blog not a set of tutorials and as with everything else programming related these days there are gazillions of tutorials out there.
Instead I'm just going to say Yahoooo!!!!
Well I'll also say that once you start using React Hooks you will suddenly find that your now &lsquo;legacy&rsquo; code base looks absolutely terrible. [Read more](/blog/js/hooks-in-react)

**[Sending email from Node functions in Firebase free tier](/blog/js/firebase-nodemailer-free-account)**  
To send emails from your Firebase functions you need to use Nodemailer and a gmail account. You cannot use the SMTP server for your domain. When nodemailer is configured to use a gmail address you may still get the following error but its just a warning and can be ignored. Billing account not configured. External network is not accessible and quotas are severely limited. &gt;Configure billing account to remove 
these restrictions [Read more](/blog/js/firebase-nodemailer-free-account" class="c-article__btn p-list-article__btn)

**[Problems installing react-snap](/blog/js/problems-installing-react-snap)**  
When installing react-snap there is an error:
Error: Chromium revision is not downloaded
The error information centers around issues with puppeteer.
Save yourself hours of googling and trying out all the different suggested fixes and work arounds and just install react-snapshot instead. 
It does the same thing [Read more](/blog/js/problems-installing-react-snap)
  
**[Function parameters with default and required values](/blog/js/function-parameters-with-default-and-required-values)**  
There were two main strategies for defining function parameters.
The first one is to explicitly list the parameters: [Read more](/blog/js/function-parameters-with-default-and-required-values)

**[How to ignore some Errors in a promise chain](/blog/js/promise-chain-ignore-some-errors)**  
Sometimes in a promise chain when you catch an error you may want to just log it and carry on. One way to do this is to throw custom Errors.
Consider the promise chain below. If A,B, or C throws an error the chain is effectively jumped out of and the final catch block is executed [Read more](/blog/js/promise-chain-ignore-some-errors)

**[Improved stacktrace when a promise is rejected](/blog/js/promise-stacktrace)**  
If you have a chain of promises and one of them throws an error which is caught by a final catch block then you'll find that the stacktrace is useless. [Read more](/blog/js/promise-stacktrace)
  
**[Uncaught Error in Event Handler](/blog/js/uncaught-error-in-event-handler)**  
Problem: There is an ErrorBoundary implemented yet the console is reporting an Uncaught Error. The loading spinner is also stuck spinning away. A stuck loading spinner is very very annoying to an end user. Why wasn't the error being caught by the ErrorBoundary? [Read more](/blog/js/uncaught-error-in-event-handler)
