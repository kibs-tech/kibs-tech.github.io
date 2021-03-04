---
date: 2021-03-04
permalink: /blog/js/pagination-with-firestore-in-nextjs
head-title: How to do implement pagination in NextJS with Firestore
weight: 10
---

# How to do implement pagination in NextJS with Firestore

You're using NextJS and are generating lovely html pages. At some point you'll want to implement pagination and to see lovely links like this embedded into your lovely html pages:

`
<< Prev [1] [2] [3] [4] Next >>
`

You're using Firestore so how can you do that?

You can't!

Firestore only supports scrolling. Thats fine in an SPA or mobile app but no good in an SEO friendly website with lovely html pages.

So what do you do?

Well I've seen people suggest implementing a pagination cloud function and using the offset query property available in the Admin SDK. However the firestore team advise against this as behind the scenes firestore retrieves all the documents before the offset is reached so its highly inefficient and very bad for your wallet.

So what do you do?

## If you sort on or order the fields of the documents

You have to use scrolling

## A proper solution (with static ordering)

This solution only works if the order you retrieve the documents in does not change.

Maintain a field in your pageable documents which auto increments. Firestore doesn't support such a field so you have to implement it yourself (see some code below). Once each document has such a  field its relatively easy to work out how to page through the documents.

![Auto increment field in firestore document](/assets/images/blog/pagination.png)

## Quick solution or if you are using variable ordering

Forget about html links and SEO and keep the pagination component a pure client side React component which implements scrolling. For SEO purposes generate statically generated pages which mimic the pagination and link to them somewhere discrete on your website and put in your site map. Such pages are not for public viewing really but they can easily be made to look good.