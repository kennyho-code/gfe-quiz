# Describe pseudo-elements and discuss what they are used for.

## Initial thoughts

Elements are the units in which html is made, so pseudo elements are "fake" elements; meaning that they aren't elements, by could "act" like elements. This refers to targeting "pseudo-elements" in CSS.

## Research

- add more specific selector, part of the selected element

```
selector::pseudo-element{
    property:value
}
```

```
p::first-line{
    ...property: value
}
```

some examples of pseudo-elements

- `::after`
- `::backdrop`
- `::before`
- `::cue`
- `::cue-region`
- `::first-letter`
- `::first-line`
- `::file-selector-button`

different from `psuedo-classes` (`:hover`, `:focus`) as these depend on state
