# Describe Block Formatting Context (BFC) how it works?

## Initial Thoughts

none...

### Research
https://www.greatfrontend.com/questions/quiz/describe-block-formatting-context-bfc-and-how-it-works
https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context#Make_float_content_and_alongside_content_the_same_height
- part of a visual CSS rendering of a web page
- where the layout of block boxes in which **floats** interact with other elements
- created with
    - root element with `html`
    - floats, where `float` isn't `none`
    - `position` is `absolute` or `fixed`
    - display is `flex`, `grid`,`table`...
    - `overflow` is not `visible`
- can use BFC to avoid `margin-collapse`

"mini-layout" in your layout..
https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/
