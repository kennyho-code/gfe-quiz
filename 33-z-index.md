# Describe `z-index` and how stacking context is formed 

## Initial thoughts
`z-index` is the 3rd dimension that is "coming towards the user". The greatest z-index by number has the greater the priority. I.e a z-index with 3 is greater than 2 ...etc; This is useful to get overlap of certain elements on top of another. 

## Research
- stacking context is an element that contains set of layers
- sibling elements can't sit between the context

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_positioned_layout/Understanding_z-index/Stacking_context

https://www.greatfrontend.com/questions/quiz/describe-z-index-and-how-stacking-context-is-formed