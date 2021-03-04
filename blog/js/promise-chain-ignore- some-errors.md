---
date: 2019-12-01
permalink: /blog/js/promise-chain-ignore-some-errors
linktitle: How to ignore some Errors in a promise chain
head-title: How to ignore some Errors in a promise chain
weight: 10
---

Sometimes in a promise chain when you catch an error you may want to just log it and carry on. One way to do this is to throw custom Errors.

Consider the promise chain below. If A,B, or C throws an error the chain is effectively jumped out of and the final catch block is executed


```javascript
import {promiseA,promiseB,promiseC} from 'some-lib'

const doSomethingA = () => promiseA 

const doSomethingB = () => promiseB

const doSomethingC = () => promiseC

doSomethingA()
.then(() =>
    doSomethingB()
)
.then(() =>                                     
    doSomethingC()
)                               
.catch(error => {  
})
```

Sometimes  if an error occurs that isn't critical it is suffice to just log it and then carry on. e.g. if doSomethingB fails, log it and carry on with doSomethingC. So can that be done?

The answer ois to create a create a custom error object so that when you catch an error you can inspect it to see what type of error it is and handle it appropriately.
  


```javascript
import {promiseA,promiseB,promiseC} from 'some-lib'

class SomethingBError extends Error {}

const doSomethingA = () => promiseA

const doSomethingB = () =>
{
  return promiseB
  .catch(error => {    
    throw new SomethingBError(error); 
  })
}

const doSomethingC = () => promiseC  


doSomethingA()
.then(() =>
    doSomethingB()
)
.catch(error => {
  if error instance of SomethingBError)
    //no big deal, just log it and continue
    console.error(error);    
  else
    //jump out of chain 
    throw error; 
})
.then(() =>                                    
    doSomethingC()
)                               
.catch(error => {
  //thrown error will be caught here
})
```





