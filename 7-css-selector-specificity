# What is CSS selector specificity and how does it work?

## Initial Thoughts

CSS is know as Cascading Style Sheets. By it's name, styles that are created are cascaded down the tree. CSS can select elements in different ways such as id's and classes. The selectory specificity model helps resolve to which selector has **priority**.

## Research

https://developer.mozilla.org/en-US/docs/Web/CSS/Specificity#selector_weight_categories

### What is CSS selector specificity?

CSS specificity priortizies which css declaration is most relevant to an element.

### How Do we calculate weights?

Weight = (ID, Class, Type)

Categories:

- ID = 1-0-0
  - #example
- class = 0-1-0
  - .myClass
  - attribute selectors [type="radio"]
  - pseudo-classes :hover
- type = 0-0-1
  - p, h1, div, etc.
  - pseudo-elements ::before, ::placeholder
- no value

  - combinators +, >, ~, "
  - nesting

```
[type="password"],
input:focus,
:root #myApp input:required {
  color: blue;
}
```

- `[type="password]`

  - attribute selector 0-1-0

- `input:focus`

  - input is a type, 0-0-1
  - :focus, is a pseudo-class, 0-1-0
  - equals to 0-1-1

- `:root #myApp input:required`
  - `:root` is pseudoclass => 0-1-0
  - `#myApp` is id => 1-0-0
  - `input` is type => 0-0-1
  - `:required` is pseudoclass => 0-1-0
  - total => 1-2-1

3 column comparison

- the left most has most priority
- then values to the next right increases priority

In line styles have priority over CSS

use `!important` sparingly; it overrides precendent styles.

https://www.greatfrontend.com/questions/quiz/what-is-css-selector-specificity-and-how-does-it-work
(a, b, c, d)

- a => inline styles
- b => ids
- c => classes
- d => elements
