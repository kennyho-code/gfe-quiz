# What does box-sizing: border-box do?

https://www.greatfrontend.com/questions/quiz/what-does-box-sizing-border-box-do-what-are-its-advantages

## Initial Thoughts

Lets start with the box-model. It describes that every element in HTML and CSS is a box. The default box-sizing is `content-box`. It means the box does not take account of the padding, border, content. When switching over to `border-box`, it does account for the padding, border. A lot of "css resets" will include `border-box` as the default box-sizing. Because it's a more intuitive way when placing elements in respect to other elements on the page.

## Research

https://developer.mozilla.org/en-US/docs/Web/CSS/box-sizing

- no `margin` for either models
- `content-box` includes `content` only
- `border-box` includes `content`, `padding`, `border`

CSS Reset

```
* { box-sizing: border-box; }
```
