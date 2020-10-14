---
permalink: /blog/js
title: A React and Better JS Journey
---
    
  
 
 <article>
<header><h2><a href="/blog/js/mock-out-api-service-layer-using-the-factory-design-pattern">
Mock out the API service layer using the Factory design pattern</a></h2></header>
    
Your React app is going to make api calls to some service that resides on a server somewhere. As a minimum in real world dev environments there will probably be a server for development, a server for testing and a server for live. Obviously that's just one simple hardware architecture example in the dev, test, build and deployment path.
A well designed React app should isolate api calls into a 
service layer<br/>
<a href="/blog/js/mock-out-api-service-layer-using-the-factory-design-pattern">
Read more</a>
</article>
  
  

***
  
    
  
## [onChange with Formik](/blog/js/formik)
   
You are using Formik and you want to add an onChange handler to a form field
Problem You can't. The formik form will stop working. Why is not important for this blog entry.
What googling reveals Google the problem and you'll find lots and lots of people quite upset that they can't 
implement their own onChange handler. There have been many requests for this to be supported and all of the requests have 
been closed.<br/>
<a href="/blog/js/formik">
Read more</a>


***  
    
  
## [The Joys of Hooks in React](/blog/js/hooks-in-react)  
I'm not going to write a tutorial on how to use hooks. This is a blog not a set of tutorials and as with everything else programming related these days there are gazillions of tutorials out there.
Instead I'm just going to say Yahoooo!!!!
Well I'll also say that once you start using React Hooks you will suddenly find that your now &lsquo;legacy&rsquo; code base looks absolutely terrible.
Do not look at it<br/>
[Read more](/blog/js/hooks-in-react)



***  
    
  <article class="c-article p-list-article">
  <header>
    <h2 class="c-title c-article__title"><a href="/blog/js/firebase-nodemailer-free-account/">Sending email from Node functions in Firebase free tier</a></h2>

      <time datetime="2019-12-17T00:00:00Z">
      
      </time>
    
  </header>
  <div class="c-article__summary">
    To send emails from your Firebase functions you need to use Nodemailer and a gmail account. You cannot use the SMTP server for your domain.
When nodemailer is configured to use a gmail address you may still get the following error but its just a warning and can be ignored
 Billing account not configured. External network is not accessible and quotas are severely limited. &gt;Configure billing account to remove 
these restrictions 
  </div>
  
  <a href="/blog/js/firebase-nodemailer-free-account/" class="c-article__btn p-list-article__btn">Read more</a>
  
</article>

***
  
    
  <article class="c-article p-list-article">
  <header>
    <h2 class="c-title c-article__title"><a href="/blog/js/problems-installing-react-snap/">Problems installing react-snap</a></h2>
    
      <time datetime="2019-12-08T00:00:00Z">
        
      </time>
   
  </header>
  <div class="c-article__summary">
    When installing react-snap there is an error:
Error: Chromium revision is not downloaded
The error information centers around issues with puppeteer.
Save yourself hours of googling and trying out all the different suggested fixes and work arounds and just install react-snapshot instead. 
It does the same thing
  </div>
 

 <a href="/blog/js/problems-installing-react-snap/">Read more</a>
    
</article>

***
  
    
  <article class="c-article p-list-article">
  <header>
    <h2 class="c-title c-article__title"><a href="/blog/js/function-parameters-with-default-and-required-values-/">Function parameters with default and required values</a></h2>
    
      <time datetime="2019-12-06T00:00:00Z">
        
      </time>
    
  </header>
  <div class="c-article__summary">
    There were two main strategies for defining function parameters.
The first one is to explicitly list the parameters:

  </div>
  
  <a href="/blog/js/function-parameters-with-default-and-required-values-/" class="c-article__btn p-list-article__btn">Read more</a>
  
</article>


  ***
    
  <article class="c-article p-list-article">
  <header>
    <h2 class="c-title c-article__title"><a href="/blog/js/promise-chain-ignore-some-errors/">How to ignore some Errors in a promise chain</a></h2>
    
      <time datetime="2019-12-01T00:00:00Z">
        
      </time>
    
  </header>
  <div class="c-article__summary">
    Sometimes in a promise chain when you catch an error you may want to just log it and carry on. One way to do this is to throw custom Errors.
Consider the promise chain below. If A,B, or C throws an error the chain is effectively jumped out of and the final catch block is executed ....
  </div>
  
  <a href="/blog/js/promise-chain-ignore-some-errors/" class="c-article__btn p-list-article__btn">Read more</a>
  
</article>


  ***
    
  <article class="c-article p-list-article">
  <header>
    <h2 class="c-title c-article__title"><a href="/blog/js/promise-stacktrace/">Improved stacktrace when a promise is rejected</a></h2>
    
      <time datetime="2019-11-26T00:00:00Z">
        
      </time>
    
  </header>
  <div class="c-article__summary">
    If you have a chain of promises and one of them throws an error which is caught by a final catch block then you'll find that the stacktrace is useless.

  </div>
  
  <a href="/blog/js/promise-stacktrace/" class="c-article__btn p-list-article__btn">Read more</a>
  
</article>


  ***
    
  <article class="c-article p-list-article">
  <header>
    <h2 class="c-title c-article__title"><a href="/blog/js/uncaught-error-in-event-handler/">Uncaught Error in Event Handler</a></h2>
    
      <time datetime="2019-11-23T00:00:00Z">
        
      </time>
    
  </header>
  <div class="c-article__summary">
    Problem: There is an ErrorBoundary implemented yet the console is reporting an Uncaught Error. The loading spinner is also stuck spinning away. A stuck loading spinner is very very annoying to an end user.
Why wasn't the error being caught by the ErrorBoundary?
This is what Reactjs.org says about Error Boundaries:
 Error boundaries do not catch errors inside event handlers. React doesn't need error boundaries to &gt;recover from errors in event handlers.
  </div>
  
  <a href="/blog/js/uncaught-error-in-event-handler/" class="c-article__btn p-list-article__btn">Read more</a>
  
</article>



