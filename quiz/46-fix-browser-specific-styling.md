# How would you approach fixing browser-specific styling issues?

## Initial Thoughts

- Would install the browser, check where the style deviates (finding the bug). Then check if the style (CSS) is available for that browser on MDN. If available, and worthwhile do some browser testing with integrating testing like playwright. Use a polyfill for the browser. Or just take away the featuer if it isn't critical....In general there needs to be "progressive enhancement"...only delivering features with user's resources. Determine if you have "Targeted browsers" in which the app supports.

## Research

- https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Cross_browser_testing/Introduction
- use separate stylesheets for browser
- use bootstrap library
- `autoprefixer` to add vendor prefixes
- React CSS or normalize.css
- PostCSS

.... a tool to compile the CSS so it gives optimizes CSS for most browsers?
