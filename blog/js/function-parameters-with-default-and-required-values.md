---
date: 2019-12-06
permalink: /blog/js/function-parameters-with-default-and-required-values
linktitle: Function parameters with default and required values
title: Function parameters with default and required values 
weight: 10
---

There were two main strategies for defining function parameters. 

The first one is to explicitly list the parameters:

```
function printHello(name,country){
  console.log(`Hello ${name}, you live in ${country}`);
  //Hello Dave, you live in UK
}
```

The problem with this is that there is nothing to stop you mistakenly getting the order of the parameters wrong when calling the function. So you could do this:

```
printHello("UK","Dave");
//Hello UK, you live in Dave
```


Or you could leave arguments get undefined:

```
printHello("Dave");
//Hello Dave, you live in undefined
```


Another strategy is to use a single parameter object:
```
function printHello(config){
  console.log(`Hello ${config.name}, you live in ${config.country}`);
}

printHello({name:'dave',country:'country');
//Hello Dave, you live in UK
```
With the single parameter object we no longer have to worry about getting the order of the parameters correct. However if we want to do some safety checking and ensure that all required function parameters have been given a value and if not then either provide a default value or throw an error then that will result in quite a bit of code at the beginning of the function.  Now thanks to object destructuring and default values we can make this safety checking really clean and simple.

Below we destructure the single parameter object into its component fields and assign a default value of "UK" to the country field:

```
function printHello({name,country="UK"}){
  console.log(`Hello ${name}, you live in ${country}`);
}

printHello("Dave","Wales");
//Hello Dave, you live in Wales

printHello("Dave");
//Hello Dave, you live in UK
```
So that takes care of default values but what about missing arguments? Well the default value can be a function so we can exploit this to implement a required parameter strategy:

```
function missingArgument(){
  throw new Error("Missing argument");
}

function printHello({name=missingArgument(), country="UK"}){
  console.log(`Hello ${name}, you live in ${country}`);
}

printHello({name:"Dave",country:"Wales"});
//Hello Dave, you live in Wales

printHello({name:"Dave"});
//Hello Dave, you live in UK

printHello({country:"Wales"});
//throws an Error because name is missing
```

So there you have it, default parameter values and required parameters. Real clean. Real Nice!




