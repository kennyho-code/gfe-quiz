# Have you ever used a grid system, and if so, what do you prefer?

## Initial Thoughts

- Grid system...because html is made of divs..rectangles.. Grid systems are naturally put in place to organize sections of the website. Previous grid systems made use of floats, then flex, and now even CSS has their own grid functionality
- Some CSS libraries have their grid system like Bootstrap... but it's easy to just make your own like so

```
.parent{
    display: grid
    grid-template-rows: repeat(numRows, 1fr)
    grid-template-columns: repeat(numRows, 1fr)
}
```

The children inside of the parent containter will now be organized in template rows and columns.

## Research

https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Grids
grid-template-areas can also be used

```
.container {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar content"
    "footer footer";
  grid-template-columns: 1fr 3fr;
  gap: 20px;
}

header {
  grid-area: header;
}

article {
  grid-area: content;
}

aside {
  grid-area: sidebar;
}

footer {
  grid-area: footer;
}


```
