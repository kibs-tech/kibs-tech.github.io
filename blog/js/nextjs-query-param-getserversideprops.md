---
date: 2020-01-08
permalink: /blog/js/nextjs-query-param-getserversideprops
head-title:  Nextjs how to get query params in getServerSideProps
weight: 10
---

# Nextjs how to get query params in getServerSideProps 

This is a quickie!

Given this url:

`myurl.com?color=red`

The following prints out red to the console

```JavaScript
getServerSideProps(context){
	console.log(context.query.color)
}
```


