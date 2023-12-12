# Explain how a browser determines what elements match a CSS selector;

## Initial Thoughts

There are two major components that are needed for this phenomona. The HTML and CSS have to present. Both make the DOM
and the CCSSOM and then combine them to make the render tree. Then the "styling" has to be identified to which elements on the HTML
it identifies. So there are identifies like style, classes, elements that have their own priority via the cascade algorithm.
(style, classes, elements)...when an identifier is made with these combination of elements, they it counts them up in buckets. In the order from left to right, then the number of each identifier and the priority is calculated...then it specifies to the element in the html.

## Research

https://www.greatfrontend.com/questions/quiz/explain-how-a-browser-determines-what-elements-match-a-css-selector

- Browser looks from right to left, `p span`, broser finds all `span`, then it traverses to the `p` elements, then traversal stops
- shorter the chain, the faster
