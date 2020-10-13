---
date: 2019-11-23
linktitle: Uncaught Error in Event Handler
title: Uncaught Error in Event Handler
weight: 10
---

### Problem:
There is an ErrorBoundary implemented yet the console is reporting an Uncaught Error. The loading spinner is also stuck spinning away. A stuck loading spinner is very very annoying to an end user.

Why wasn't the error being caught by the ErrorBoundary?

This is what [Reactjs.org](https://reactjs.org/docs/error-boundaries.html) says about Error Boundaries:

>Error boundaries do not catch errors inside event handlers. React doesn't need error boundaries to >recover from errors in event handlers. Unlike the render method and lifecycle methods, the event >handlers don't happen during rendering. So if they throw, React still knows what to display on the >screen.

### Solution:
Wrap all event handlers in a try-catch block so that the error can be caught and the loading spinner switched off. Like this:


```javascript
onSubmit = event => {
    try {
		this.setState({ loading: true, error: null });
		
		// submit the form
 	}
	catch (error) {
            this.setState({ loading: false, error });
    }
}
```
