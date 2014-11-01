# Multi-device Web Design & Beyond
### Luke Wroblewski

consumer internet vs. enterprise applications
     very, very high bar because there's lots of alternatives

last fall ~45 new devices came out… difficult to test on all these different devices

trickle out effect in US… leading indicator market for worldwide trends

7" tablet starting to take over tablet market

how do you draw the line between what's mobile and what isn't? physical screen size? resolution? makes phone calls?

we're dealing with a size continuum

76% of active sessions are 3-5" screen devices

android 75% of smartphones shipped; only represented 5.5% of online shop ing

android gets less engagement because people who get those phones are just trading in and getting their new phone and don't know what it does

all HP/Asus computers will have pseudo-touch w/ Leap motion

touch & cursor/keyboard run the gamut

Multi-Device Design:
1. Support a Continuum of Screens
2. Account for High Resolution
3. Optimize for Touch
4. Support Cursor & Keyboard

you only need one web design: a multi-device design

1. How do we explain/sell to clients
2. Advertising?
3. Multi input interfaces?
4. Prototyping & testing
5. Me have Web site, what me do? (specifically workflows)
6. Perform ance techniques
7. Navigation & organization on multiple devices
8. Responsive images, videos, tables, maps, etc. (if UGC esp)
9. Breakpoints: how to manage, where to set?
10. Cross device experiences
11. Visual design distinctions between OS & Web
12. Dealing with high solution screens/images
13. How to create a touch-optimized interface (better to lead with touch)
14. Opt-out responsive design
15. Enhance from mobile out


Mobile Navigation


bottom tab bar pattern

     up to 5 sub-views (or "more" tab)
     fixing controls to the bottom of the screen SUCKS and should be avoided
          - android suggests NOT using
     prefer the footer-anchor pattern

toggle menu pattern / top navigation overlay

off-canvas menu
     line/hamburger icon


Design Considerations
content first - don't just show a bunch of links 7 navigation; content front & center; display immediate value when user launches app

could also have an icon/link up at the top (minimal navigation) which launches you to the bottom of the page where the navigation is

most people are interacting with the bottom-half of the screen

maintain context
pivot & explore


Responsive Navigation Patterns

Comfortable touch zones… bottom area only consistent place where different devices can be comfortable with touch interaction

existing conventions vs ergonomics of software



Methodology

start with mobile
enhance upward


Work mobile first
design/development start form most constrained context and then move towards a fully enhanced experience


1. growth = opportunity
2. constraints - focus
3. capabilities - innovation

http://blog.cloudfour.com/responsive-design-for-apps-part-1/

privilege the smallest screen

opera mini has 200M active users

basic -> css styles -> enhanced
defaults / media query support / screen size /

if('querySelector' in document && 'localStorage' in window && 'addEventListener' in window) {}

essential: fluid width -> can mean 'stretch' or 'reveal'


Default Viewport Width

dynamic viewport = different devices use different scaled-down views

apple web site has vertical media queries to deal with portrait/landscape


How do we explain/sell to clients



Support a continuum of screen sizes

fluid grids, flexible images, media queries

conversion is bad on mobile because mobile is a desktop site shoved into mobile device

benefit to responsive design:
     one deployment, one url, one code base

minor break point = tweak point

content-based break point

convert pixel values to em-based media queries

vexing viewports

multi-device layout patterns
1. mostly fluid
2. column drop
3. layout shifter
4. tiny tweaks
5. off canvas

the mobile stack
we can rearrange the content… meh.
off-canvas multi-device layout patterns


High-resolution screens

1. css background images
2. javascript replace (both downloaded)
3. compress & serve one
4. give people choice

media queries in SVG




Perf


takes a lot amount of time and disciple to make a responsive site performant

Perception
1. instant feedback
2. minimize spinners
3. perform actions optimistically
4. move bits while no one is watching
5. adaptive preloading

manage perception of speed by putting in transitions and stuff

opportunistic/optimistic rendering…

http://www.imgix.com/
http://designshack.net/articles/css/focal-point-intelligent-cropping-of-responsive-images/
http://bradfrostweb.com/blog/post/adaptive-maps/

perceived perf
client-side enhancements
server-side components

http://www.lukew.com/ff/entry.asp?1392

http://ress.io/
http://www.moovweb.com/



we have a web site, what to do??

mobilizing web sites


responsive retro-fitting

extend mobile site

start fresh


Native VS. Mobile
rich vs. reach


custom url scheme for opening links in native apps


18 inch use interface
2 foot user interface
10 foot user interface

design based on distance from device



