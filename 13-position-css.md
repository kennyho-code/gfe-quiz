What's the differene between a `relative`, `fixed`, `absolute`, and `static` - ally positioned element?

## Initial Thoughts

`Position` is a css property that changes the behavior of where the element is placed. `relative` position is where it's relative to the parent element. `fixed`, positioned does not change it's position. For instance, like a nav-bar that is always showing at the top. `absolute` disregards any positioning in it's parent element and only to the viewport. `static` is the default position?

## Research

https://developer.mozilla.org/en-US/docs/Web/CSS/position

- how the element is positiioned in the document
- `static` => normal flow of the document, `top`, `right`, `bottom`, `left` and `z-index` have no effect
- `relative` => relative to it's normal position. `top`, `right`, `bottom, `left` have effect.
- `absolute` => removed from normal flow. `top`, `right`, `bottom, `left` have effect against the neareste positioned ancestor. If none, then it's the document body.'
- `fixed` => removed from normal flow. `top`, `right`, `bottom, `left`... it's positioned is fixed to the it's containg block.
- `sticky` => treated as a relative position, until it reaches a point/threshold, and then becomes a fixed position.
