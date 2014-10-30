## Accessibility in the browser

### Cassidy Williams

__Summary:__
Static, page-based sites are everyday being replaced by dynamic web applications that make heavy use of JavaScript and AJAX. Widgets and controls can now be built entirely with JavaScript, HTML, and CSS. Many users are at risk of being excluded from the growing responsiveness and usability of the web due to increasing accessibility gaps. There are now ways, with JavaScript (which is often thought of as quite inaccessible to those who use assistive technologies), to make dynamic web interfaces that are accessible to many kinds of users. In this talk, we'll discuss the Accessible Rich Internet Applications specification (ARIA), which enables dynamic, JavaScript-driven applications to work with a variety of desktop-based assistive technologies. By the end of this talk, the audience will understand the importance of the ARIA specification, and how easy it is to incorporate it in their own applications.

---

about 20% of the population has some kind of disability

* semantic web - semantics is the science of meaning
* WAI-ARIA spec - defines ways to make Web content and applications more accessible
* accessibility checklist for your project


__The Semantic Web__

* html5 tags
* the role attribute

__WAI-ARIA Specification__

4 rules for ARIA use:

* if you can use a native HTML element of attribute, then do so
* do not change native semantics, unless you really have to
* all interactive ARIA controls must be usable with the keyboard
* all interactive elements must have an accessible name 

---

__Accessibility checklist:__

visibility:

* use the visibility or display properties, or the hidden attribute
* don't override too many of the browser's default behaviors

color:

* there should be a certain amount of contrast in your color choices

focusability:

* everything on the page should be able soave focus
* if a control on the page isn't standard, the should have an appropriate ARIA role attached to them

state changes:

* standard controls have this taken care of
* custom controls need ARAI states handled manually (aria-checked, aria-pressed, etc)

__Developer tools:__

Fang's screen reader emulator
WAI-ARIA best practices
Color contrast checker
Tanaguru's Automated Accessibility Testing Service
