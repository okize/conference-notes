## Weighing performance against pain: SVG, canvas and webgl

### Dominikus Baur

__Summary:__
Data visualization developers have three main graphics technologies at their disposal: the convenient and slow(ish) SVG, the flexible but verbose Canvas and the highly performant but unwieldy WebGL. In this talk, Dominikus will present an overview of the differences between SVG, Canvas and WebGL, how to optimize performance for each of them and how to create data visualizations using the novel WebGL.

---

* pain / preformance: svg, canvas, webgl in order; as you get closer to GPU the implementation difficulty increases

#### Performance basics:

* know when to stop
* know your tools
* remove things
* shift things, when you can't remove
* are you smarter than browser engineers?
** think twice before trying to take over responsibilities from the browser

##### pro-tip
* remove node structure from dom, adjust properties then reattach, which will generally result in better performance

#### SVG

* text-based
* css support
* dom integration
** support for integrations
* slowest of three technologies
** static SVG: 10,000 elements at most
** animated SVG: 1,000 elements tops

#### canvas

* must keep track of objects
* canvas looks like an image even with multiple nested canvas objects
* more performant than SVG

#### webGL

* most performant
* painful to write for

#### Hybrid approaches

* mix & match each technology when it makes sense to do so
