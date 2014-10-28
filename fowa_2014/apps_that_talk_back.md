## Apps that talk back

### by Rebecca Murphey


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


