# What's the difference between a cookie, `sessionStorage`, and `localStorage`?

https://www.greatfrontend.com/questions/quiz/describe-the-difference-between-a-cookie-sessionstorage-and-localstorage

## Inital Thoughts

What is a cookie? Cookies are "set" from a response, that comes from a request. For instance if we authenticate with a HttpRequest, and if there's a successful response, then a cookie is set within the browser. The cookie is special in that it persists until the user deletes it or if if it expires. The cookie is secure that it only is viable if it's in a certain domain. For instance a cookie can be used for ` a.google.com`` and  `b.google.com`.

Other types of storage isn't as secure, but allows for more flexibility. They don't have to adhere to the domain and can be set by the user. So non-secure, such as app state can be used. There are two difference types of storage. `sessionStorage` and `localStorage`.

`sessionStorage` allows to persist during the session. Meaning that memory only persists when the user is on the website via the tab. So if the user x's out of the browser or the tab, then the memory is gone.

`localStorage` stays within the browser until the user deletes it. So even if the user x's out of the tab, or the browser, the memory is still there. This might be useful for alerts, banners.

## Research

Cookies
https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies

- HTTP cookie (web cookie, browser cookie)
- sent from a server using `set-cookie` HTTP header
- purposes
  - session management
  - personalization
  - tracking
- worsen performance because they are sent with every HTTP request and web storage apis
  are reccoomended instead
- HTTP Response header

```
Set-Cookie: <cookie-name>=<cookie-value>
```

- Session cookis when the browser defiens session
- Permenant cookies defined by `Expires` attribute or `Max-Age` attribute
- Secure cookies only can be sent with `HTTPS`;
- HttpOnly cookies can be set via `Document.cookie`

Cookies are sent via `domain` and `path`

- `domain` like `google.com`
- 'path' `/some-path`

https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API
Local storage

- allows for key value store
- avaiable in the `window` object but read only
- persist across sessions

Sesson storage

- data is stored until the browser is tab is closed
- storage is larger than a cookie 5MB
- duplicating a tab, copies the sessionStorage

...session storage good for more optimized data, local storage when a user wants to come back,
cookie for allowing more connection from the server and client
