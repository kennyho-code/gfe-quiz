# Why is it generally a good idea to position CSS `<link>` elements between `<head></head>` and JS `<script>` elements just before `</body>`?

## Initial Thoughts

CSS and JS are static files. Meaning that are preprocesed and optimized and shipped to the server...usually in a folder i.e the `/public`. The `index.html` is usually the entry point in which these static files are loaded. The head is loaded before the body, and this is usually where CSS and JS are loaded. It's proper practice to put these files because these are considered "Dependencies" for what is loaded into the body.

## Research

`<link>``

- HTML and CSS creates CCSOM and DOM simultanelously. Both needed for FCP (first meaningful paint)
- `Link` in the bottom reduces FCP, decreases performance staistics, and "flashes of unstyled content" (FOUC).

`<script>`

- <scripts> block the rendering of the html so it's placed on the bottom? (isn't this oudated)
- if scripts needed to loaded first, use `defer` and put in the head
- creates the illusion of being faster, because html can load
- cached js in the head, will appear faster
- seems like using `scripts` with `defer` or if it already is type `module`..which automatically `defers` in the `head` is the most modern approach.

https://www.youtube.com/watch?v=cXwnJKflxas&ab_channel=WebDevSimplified
https://www.reddit.com/r/learnjavascript/comments/13xq312/is_using_script_defer_in_head_theoretically_same/

https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#defer

- defer runs after the html is parsed but before `DOMContentLoaded`
- fyi, `DomContentLoaded`, then `js files loads`, then react can be run