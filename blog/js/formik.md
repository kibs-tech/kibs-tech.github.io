---
date: 2020-01-08
permalink: /blog/js/formik
linktitle: onChange and Formik
title: onChange with Formik
weight: 10
---

## Task
You are using Formik and you want to add an onChange handler to a form field

## Problem
You can't. The formik form will stop working. Why is not important for this blog entry.

## What googling reveals
Google the problem and you'll find lots and lots of people quite upset that they can't implement their own onChange handler. There have been many requests for this to be supported and all of the requests have been closed. Instead you are redirected all over the place for possible solutions including using Formik Reducer Middleware!



## The Solution - its a secret yet so simple
Forget about implementing onChange. Turns out you don't need it.  This is because the values of the form fields are made available in the render prop so you can examine the form field values and do what ever you want with them. You can even detect a change yourself if wish but rendering denotes a change doesn't it so you may not need to.  If you use formik then the code snippet below should be a eureka moment for you ( Note: notice the {values} )

'''JavaScript
<Formik
    initialValues={}
    validationSchema={}                
>
    {({values}) => {

        return( 
                            
            <p>Hey these are the form values { JSON.stringify( values ) }
                            
            {values.country  && <p>I know that field country has a value so I can use it!</p>}
                            
        )
    }
    )}
</Formik>
'''                        

Its certainly a lot easier than using Formik Reducer Middleware !





