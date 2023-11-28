# How do you serve a page with content in multiple languages?

## Initial Thoughts

- Some browsers like google chrome can translate words on a website from one language to another. It's usually on the options near the domain input area. The HTML tag also has a language property of `lang`...But is there anything else?

# Research

- internationalization (i18n)...number of letters between i and n ... 18
- Http Request made to server uses `Accept-language`
- `<html lang="en>`
- link tags should use properties like `<link rel="alternate" hreflang="de" href="http:..de.example.com/page.html" />`

Rendering

- SSR - html markup with contain string placeholders will be fetched from configs or code or a translation service...server then generates html page with content in the laguage
- CSR - locale strings will be fetched and combined with JS based views.
