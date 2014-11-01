# Rendering without the lumps
### Jake Archibald

Graphics perf - new developer challenge

dev tools frames panel

     Parse HTML - jquery.html() - doesn't have it's style calculated

creates a tree of renderObjects
Layout/Reflow - same thing
     layout change triggered when browser resized

display: none, no rendering impact to the page so it doesn't appear in the render tree

paints cause by visual changes…

within 100ms of user interaction tends to feel instant

layout thrashing - do your reads before your writes!!

fixed css backgrounds cause crazy repaints…

fixes 300ms delay in mobile clicks:
     https://github.com/ftlabs/fastclick

WTFPS? what the frames per second

polyfill for jquery animations
     https://github.com/gnarf/jquery-requestAnimationFrame

composite layers - show composited layer borders

translateZ - moves animations to GPU

instead of top/left animations, use transforms

anything that is on top of a layer becomes a layer itself

look at WebGL to understand the GPU




