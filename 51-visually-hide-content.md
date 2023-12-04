# What are the different ways to visually hide content (and make it available only for screen readers)?

# Initial thoughts

- Need to keep dom element nodes where it can display properties ...and strings...etc so the user knows what's available but also hidden..

# Research

- `display: none` or `visibility: hidden` ... hides elements on the screens so screen readers can't see it...
- aria-hidden to display elements but hide from screen readers
- use a css class like `visually-hidden`

```
.visually-hidden {
      position: absolute;
	position: absolute !important;
	width: 1px !important;
	height: 1px !important;
	padding: 0 !important;
	margin: -1px !important;
	overflow: hidden !important;
	clip: rect(0,0,0,0) !important;
	white-space: nowrap !important;
	border: 0 !important;
}

```

https://a11y-guidelines.orange.com/en/articles/accessible-hiding/#:~:text=The%20conventional%20way%20is%20to,by%20Assistive%20technologies%20(AT).

- small/zero size, `width: 1px, height: 1px` ... `width: 0, height: 0`..not reccomended
- absolute position: `position: absolute; left: -99999px`;
- text indentation: `text-indent: -9999px`

techniques in the wild

```
.sr-only {
  position: absolute;
  width: 1px;
  height: 1px;
  padding: 0;
  margin: -1px;
  overflow: hidden;
  clip: rect(0, 0, 0, 0);
  white-space: nowrap;
  border-width: 0;
}
```

```
.visually-hidden,
.visually-hidden-focusable:not(:focus):not(:focus-within) {
  position: absolute !important;
  width: 1px !important;
  height: 1px !important;
  padding: 0 !important;
  margin: -1px !important;
  overflow: hidden !important;
  clip: rect(0, 0, 0, 0) !important;
  white-space: nowrap !important;
  border: 0 !important;
}

```
