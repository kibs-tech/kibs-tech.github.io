---
date: 2019-11-26
permalink: /blog/js/promise-stacktrace
linktitle: Improved stacktrace when a promise is rejected
title: Improved stacktrace when a promise is rejected
weight: 10
---

If you have a chain of promises and one of them throws an error which is caught by a final catch block then you'll find that the stacktrace is useless. 

```javascript
import {promiseA,promiseB,promiseC} from 'some-lib'

const doSomethingA = () => promiseA;

const doSomethingB = () => promiseB;

const doSomethingC = () => promiseC;

doSomethingA()
.then(() =>
  doSomethingB()
)
.then(() =>                                    
  doSomethingC()
)                               
.catch(error => {
  //the error stacktrace will not show 
  //where in the above chain the error
  //occurred. It will be useless for 
  //debugging
  console.error(error);
})
```

The concept of stack traces originates from synchronous code. Using asynchronous code makes tracing somewhat difficult, since the corresponding calls are now indirect and all context of the caller is lost.

To get round this some people advocate using 3rd party promise libraries, like [bluebird](http://bluebirdjs.com/docs/getting-started.html), which implement tracing across several promise invocations. 

A simpler approach which uses native JavaScript promises is to catch an error at the point when it happens in the chain and then throw a new error instead

```javascript
import {promiseA,promiseB,promiseC} from 'some-lib'

const doSomethingA = () =>{    
  return promiseA
  .catch(error => {
    //the stacktrace will now have this line:
    throw new Error(error); 
  })
}

const doSomethingB = () => {
  return promiseB
  .catch(error => {
    //the stacktrace will now have this line:
    throw new Error(error); 
  })
}

const doSomethingC = () => {
  return promiseC
  .catch(error => {
    //the stacktrace will now have this line 
    throw new Error(error);     
  })
}

doSomethingA()
.then(() =>
    doSomethingB()
)
.then(() =>                                     
    doSomethingC()
)                               
.catch(error => {
  //Yey we have a nice meaningful stacktrace
  console.error(error)
})
```



