# Explain what a single page app is and how to make one SEO-friendly

## Inital thoughtss
A single page app (SPA) is a app with one page. Typically frameworks like React does everything in a `index.html` where it can have a div via `root` and inject a root component named `App` where it bootstraps whole app. Usually javascript simulates routing to "multiple pages" via a library like `react-router` but it's using the window history api in the browser and javascript to mimic "new pages". 

Since everything is loaded via javascript, it is dynamic, meaning it is not static. So when you need SEO, (Search Engine Optimization), there is a web crawler that that goes to website and looks for html where it can parse through to find properties of the site that's relevant for search engines. The dynamic web app doesn't have any static so there is no data to be crawled. 

But there are some other techniques make these SPAs "SEO" friendly. One is creating static pages when you build the app which allows for static content. Other ways are to use meta data where the web crawler can get data. 

## Research
- SSR (Server Side Rendering), asking the server for HTML
- Client Side Rendering, Modern SPAs, generate html via JS
- https://prerender.io/ to get SEO