## Apps that talk back

### by Rebecca Murphey

__Summary:__
At Bazaarvoice, the Firebird team works on a JavaScript application that collects and displays ratings and reviews. It's injected as a third-party script on hundreds of millions of pageviews every month. Every customer's app is built from a configuration unique to that customer, and each app has to work as a first-class citizen -- no iframes here -- in the sometimes-hostile world of the customer's page. With endless configuration variations and customers who have a penchant for loading three versions of jQuery on their page just for fun, it's inevitable that things will go wrong. When they do, we need to know about it quickly and fix it in a hurry. In this talk, we'll look at some of the things we're doing on the Firebird project to get our application to tell us how it's doing, from simple monitoring of our build server to client-side error reporting to cookie-based backdoors that developers and customers alike can use to troubleshoot production issues.

---

3rd party javascript works by exploiting a fundamental flaw of how the internet was built (ie. any website can execute any arbitrary js it loads)

reviews, even bad ones, lead to more sales

#### operation excellence:
* service monitoring
* error tracking
* performance metrics
* production debugging
* safety nets

developed classification of errors before sending to analytics system

dump all data into elasticsearch and feed into dashboard which allowed team to dive into errors and learn why custom had broken code before customer even realized anything was wrong

need visibility into application performance

batch requests up (10 at a time)

runs in unknown execution environment so "works on my machine" doesn't really fly

have a bookmarklet that sets a cookie that will set a flag for debug mode (because customers don't want console logging) that will display verbose logging & error details in console

* assertions
* git hooks (jshint, jscs, unit tests)
* error classification & reporting
* production monitoring
* production debugging
* build size monitoring
* performance
* instrumentation
* error alerting
* pass call-stack with errors
* performance monitoring
* performance budget


