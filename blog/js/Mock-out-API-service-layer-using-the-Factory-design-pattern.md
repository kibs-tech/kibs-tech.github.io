---
date: 2020-01-16
linktitle: Mock out the API service layer using the Factory design pattern 
title:  Mock out the API service layer using the Factory design pattern 
weight: 10
---

Your React app is going to make api calls to some service that resides on a server somewhere. As a  minimum in real world dev environments there will probably be a server for development, a server for testing and a server for live. Obviously that's just one simple hardware architecture example in the dev, test, build and deployment path.

A well designed React app should isolate api calls into a service layer. The service layer can then be swapped out if need be so that if, for example, a service provider is changed you just need to change the code in the service layer to support the new service provider. 

In the days before dependency injection we used to use Factories. This is not something you see very often these days. In fact if you google mocking API services you get told about harnessing the power of test environments that use mock data etc etc etc. However for small scale projects the Factory pattern is an excellent, simple and easy way of serving up multiple service layer implementations.

## Example
We'll use the following as an example of a really simple order service that makes an API call (to a nosql database but thats irrelevant)

```JavaScript
//order-service.js

const getOrders = (customerID) => orderAPI.collection('orders').doc(customerID).get();

const orderService = {
    getOrders
}

export default orderService
```

A React component that uses the service might look like this:

```JavaScript
//order-list.js

import orderService from './order-service.js'

const orderListComponent = (props)={
    const {customerID} = props;
    const [orders, setOrders] = useState();

    useEffect(){
        const orders= orderService.getOrders(customerID)
        setOrders(orders)
    }

    return (
        orders.map( item => <p>{JSON.stringify(item)}</p>)
    )

}
```
Now let's setup some mock data:

```JavaScript
//orders.json

{
    "orders":[
        "bananas",
        "plums",
        "pairs"
    ]
}
```

and create a service that serves up this mock data (instead of making an api call)

```JavaScript
//mock-order-service.js

import './orders' 
//the above imports the orders.json file and deserialises it making it available 
//in a variable called 'orders' - nice!

const getOrders = (customerID) => orders; //just return the mock data

const mockOrderService = {
    getOrders
}

export default mockOrderService
```

Note that the signature of mockOrderService is identical to orderService.

Now we create a ServiceFactory which will return either a mockerOrderService or  orderService depending on how the application has been configured. 


```JavaScript
//service-factory.js

//import both versions of the order service:
import mockOrderService from 'mock-order-service'
import orderService from 'order-service'


//determine whether the application has been configured to use mock api:
const isDev=()=> process.env.NODE_ENV === 'development';
const isMockAPI=() => isDev() && process.env.REACT_APP_MOCK_API;


//now provide a function to 'get' the  order service
const getOrderService = () =>{
    if (isMockAPI){
        return mockOrderService
    }
    else {
        return orderService
    }
}

//construct the factory object:
const serviceFactory = {
    getOrderService
}

//and export it:
export default serviceFactory;
```

Now the orderList component is changed to use the serviceFactory to obtain the order service

```JavaScript
//order-list.js

//these two lines are whats different:
import serviceFactory from './service-factory.js'
const orderService = serviceFactory.getOrderService();
//hopefully you can see that orderService will now either be the mockOrderService 
//or the real orderService depending on the app configuration

const orderListComponent = (props)={
    const {customerID} = props;
    const [orders, setOrders] = useState();

    useEffect(){
        const orders= orderService.getOrders(customerID)
        setOrders(orders)
    }

    return (
        orders.map(item = > <p>JSON.stringify(item)</p>)
    )

}
```

And there you have it. Simple! If you start off using the factory pattern you'll be able to work locally and also be totally independent of a requirement to have a fully implemented and available api service running somewhere remotely. 

