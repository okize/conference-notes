## Front-End Ops

### Alex Sexton

__Summary:__
Alex coined the term "Front-End Ops" in his Smashing Mag article last year and the community around it has been growing steadily since. Front-End Ops refers to all the work outside of the core of a front-end app. It is performance monitoring and bug tracking; it's build tools and error tracking; and it's developer happiness and maintainability. All these ideas make for quite a bit of work outside of the core application development. This talk will go over techniques to integrate these smoothly into your projects, and help you benefit from having a solid foundation to hold up your apps.

---

__naming things:__

* front-end operations - the collection of things you can do to make serving webpages easier

* regressive enhancement - when you make things worse in old IE in order to get them to upgrade (blur all the text)

* polyfill (from polly-filla wall spackle) -> prollyfill - a pollyfill for a not yet standardized API

serving webpages is really hard, which is why we have conferences (we don't have conferences for easy problems)

Mature FEOps benefits the people who don't have time to think about this stuff

Front-end Ops Engineers are the bridge between an application's intent and an application's reality

Front-end engineers are collectively insane

__Why now?__ Application logic is being deferred to the client side

Our tooling hasn't caught up to our eagerness to write complex client-side apps

* life-cycle measuring
* measurement over time

__Performance__ is the foundation on which user experience is built

* speed of the app
* speed of tools
* speed of development (developer happiness)

__Speed of the app__

* forget everything you know because it's wrong (measure everything)
* it's probably the network, so...
* read Ilya's book - high performance browser networking
* measure; speed index
* measure twice

__Measurement__

get measurements per device; measurements per country; measurements per connection type (wifi, LTE, etc)

consider graphing load time bell curves of desktop vs mobile separately

make a dashboard:

* speed index over time (draw lines where commits happen)
* page weight over time (gzipped/ungzipped; broken down by filetype)
* requests over time (internal vs. 3rd party)
* errors
* build time over time

__Speed of tools__

* The time between making a change, and seeing it in your app must approach 0

__Speed of development__

* take the time to make source maps work
* here should be one easy command to get everything to work
* turn on livereload
* implement life-cycle logging
* set up a calendar reminder to update your dependencies
* have a rigorous code Style Guide that everyone follows and that robots yell about

__Abstraction team__

* living stye guide (see Lonely Planet)
* make your own bootstrap (your own component library)
* go crazy testing your components
	* change state classes into actual classes
* indirection




