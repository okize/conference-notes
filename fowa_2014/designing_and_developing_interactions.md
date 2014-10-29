## Designing and developing interactions for the cross-platform web

###  Matt Keas

__Summary:__
Cross-platform web apps with custom UI controls are notoriously difficult, and unstable, on multiple devices. When your design team has edgy and delightful design ideas – yet you don’t know where to start – you may need to resort to “outside the box approaches.” What are some of these approaches, and how can we push the boundaries of interaction and experience, without technically drowning ourselves in “opportunity cost”? This talk will ebb and flow with context-aware design, a DIY code-ethic, and a “framework free” approach to building delightful interfaces with buttery smooth “do-it-and-get-out-of-the-way” animations.

---

IxD vs. IxDD - that elusive unicorn

custom UI's require intamte knowledge of

1. html/css quirks
2. layout and positioning
3. handling events
4. the order in which events fire
5. all the new html5 events

handing input by combining...

1. debounce
2. requestAnimationFrame()
3. late binding / ASAP unbinding
4. state-driven visual updates
5. scoped contexts (keymage)

pointer events - modeled after traditional mouse events

```
.avoid-clicks {
	pointer-events: none;
}
```

__small wins__

* limit what you animate, when you animate and how much you animate
* touchstart/mousedown events delay the compositor thread which draws o the screen
* ...

handing input - takeways

* HARD - custom event code
* HARDER - managing events contextually and working with bubbling/capturing
* HARDEST - making interactions intuitive, and maybe even habitual

* find your "what if's" and focus on those
* prototype, syart simple
* deep focus -> intuition -< creativity -> problem solving -> delightful UIs


cheap animations:

* size
* position
* rotation
* opacity

* context-aware, not just responsive
* DIY ethic
* strive for simplest animation control