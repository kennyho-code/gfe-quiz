# What is the CSS `display` property and can you give a few examples of use?

## Inital Thoughts

The flow, or the type of display, how the "boxes" in the CSS is dependent on what display property is set. The default value is the block model. Where most elements are layed on on top of each other. But there are some "inline" elements like span that lay out horizontally in respect to the elements.

Flex is another display option, that allows for elements to be positioned on a single axis. Grid allows for elements to be positioned on two axis. Inline allows for properties to be spaced horizontally regardless of it's width or height. Inline-block is displayed horizontally but respects width and height. There is also the table display, that isn't used as much because flex and grid have superseded it.

In all, displays allow elements to be displayed in different ways. It usually involves the parent container to set the display property and the children elements behave in respect to what is set.

## Research

https://developer.mozilla.org/en-US/docs/Web/CSS/display

https://www.greatfrontend.com/questions/quiz/what-is-the-css-display-property-and-can-you-give-a-few-examples-of-its-use

Types of displays:

- `none` => does not display
- `block` => element conseumes block direction, usually horizontal
- `inline` => elements can be laid beside each other
- `inline-block`=> elements can be laid beside each other, but respects width and height
- `flex` => use flexbox model to position elements on a single axis
- `grid` => uses grid layout to position elements on two axis
- `table` => behaves like table element
- `table-row` => behaves like table-row
- `table-cell` => beleaves like table-cell
- `list-item` => behaves like list-item
