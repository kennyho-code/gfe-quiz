# How do you serve your pages for for feature-constrained browsers?

## Initial Thoughts

- Serving pages usually is provided by a server; Whether it's a service like cloudflare, github,.... there's a service that allows you to put your index.html on one of their servers. What's a feature-constrained browser? Maybe a browser that's on an older OS or has limited bandwidth in their internet? Progressive enhancement?...optimizations are only allowed/constrained by the current number of resources.

## Research

- graceful degradation
- progressive enhancement
- caniuse.com
- autoprefixer
  fe- ature detection using Modernizr
- CSS feature quiries via `@support`

https://www.greatfrontend.com/questions/quiz/how-do-you-serve-your-pages-for-feature-constrained-browsers-what-techniques-processes-do-you-use
