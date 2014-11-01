# Deep CSS Secrets
### Lea Verou

1. shadow on top/bottom of scrollable list with hidden areas (overflow hidden)
     background-attachment: scroll/fixed/local
     (not supported in Firefox; IE9+)
     requires solid background

2. use calc instead of margin: auto
     section{ padding: 1em calc(100% - 350px; ) }
     not supported in Opera;

3. sequenced css transitions
     supports a delay (2nd time value)
     transition: 1s width, 1s 1s height;
     can extend box-shadow to create overlay

4. zebra-striping on block text (not table rows or lists)
     modern browsers; IE10+

5. images cropped to shape
     css transforms; ie9+

6. rotate an image in a circle without it also rotating

7. css filters
     support in chrome; sort of in FF2.6

8. have an overlay text box that blurs the image behind it
     messy background positioning

9. hyphens: auto to get hyphenated justification
     not supported in Chrome

10. animate png sprite with transitions
     not just bezier-funcitons, also have steps
     good for alpha transparency
     supported ie10+



