## Have you played around with the new flex and grid specs?

## Initial thoughts?

Flex and grid are css properties of display. The default display is usually block. Flex and grid both use the concept of parent have the display property and the children are then affected. The main difference between these two is that flex children elements flow in a single axis while grid is on 2 axis.
https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_flexible_box_layout/Basic_concepts_of_flexbox

Doing flex like so...

```
.someClass {
    display: flex;
    flex-direction: row; # goes horizontall but you can also stack elements via column
    justify-content: ....# behavior along the main axis
    align-items: behavior along the cross -axis
}
```

https://developer.mozilla.org/en-US/docs/Web/CSS/grid

Doing grid like so

```
.someParent{
    display: grid
    grid-template-columns: 1fr 1fr 1fr; # 3 columns (how many columns)
    grid-template-rows: 1fr 1fr 1fr; # 3 rows (how many rows)
}

```

...using grid template areas... this allows you to use names in the `grid-template-areas` and assign them to the children elements.

```
.someParent{
    display: grid;
    grid-template-areas:
        "header header"
        "nav main"
        "nav footer";
grid-template-rows: 50px 1fr 30px;
  grid-template-columns: 150px 1fr;
}

nav {
    grid-area: nav;
}

main {
    grid-area: main
}
```

https://developer.mozilla.org/en-US/docs/Web/CSS/grid-template-areas
