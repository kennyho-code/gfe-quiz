# Is there any reason to use translate() instead of absolute positioning, or vice-versa? And why?

## Initial Thoughts
What is transalate, it's a CSS property that allows you to move an object in the and y axis. What's absolute positioning; When using absolute positiong, it finds the the nearest ancestor that is positon relative. And then it positions itself relative to that ancestor.

## Research
- translate() is a possible value for the CSS `transform` property
- still occupies the same space in the document, but have to recalculated like the position property
- transform or opacity does not retrigger repaints but does trigger compositions
- absolute position triggers `reflow`
- `transform` causes the browser to create a a GPU layer
- absolute position uses CPU
- translate() results in shorter paint times for smoother animations

https://developer.mozilla.org/en-US/docs/Web/CSS/transform
https://www.greatfrontend.com/questions/quiz/is-there-any-reason-youd-want-to-use-translate-instead-of-absolute-positioning-or-vice-versa-and-why