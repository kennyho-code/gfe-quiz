## Question: Describe the difference between `<script>`, `<script async>` and `<script defer>`

### Link: https://www.greatfrontend.com/questions/quiz/describe-the-difference-between-script-async-and-script-defer

## Inital Thoughts

What is a script tag? Script tags allows for javascript to be injected in the browser. It can be injected in the head of the index.html file like so:

```
<html>
<head>
    <script src="./index.js">
</head>
...
```

When the the `index.html` gets loaded, it loads the head which usually contains javascript, css, and any important static files. Lets discuss the two keywords that can alter the loading of javascript:

- `async`
- `defer`

Async, like the keyword describes, means asynchrnous. This means the loading of any other files will still load regardless. Lets say if we had somethinkg like

```
<script src="./two.js">
<script async src="./one.js">
<script src="./three.js">
```

The browser loads in the html, checks `./two.js` loads the javascript **synchronously**, then goes onto the `async` `./one.js`, where it then does NOT block, won't need to load it's js, and quickly goes on to `./three.js`; which will load **synchronously**.

If the default behavior of `script` is already `synchronously`, then what does `defer` do? Is it explicit. MDN says that that it blocks any rendering via `DOMContentLoaded` event. This means that no rendering must happen until the `defer` script is loaded. https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#defer.

---

Additional notes:

- default is blocks html parsing
- async is non-blocking; useful for js tracking analytics
- defer used when scripts are dependent on each other where ordering is important
- needs to have `src` attribute
