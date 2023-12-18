# What is progressive rendering?

## Inital thoughts

- Progressive is do things incrementally rather than doing it whole sale... Rendering shows dom elements...or visual elements to the canvas.
- Because rendering can be computationally heavily...in respect to the application, the internet, or the performance of the user's computer...these things have to be accounted for a good user experience. If any of these properties lack, then it cause a bad user experience. It's said that a bad user experience...is worse than no experience. Because a user can do something else rather than at a loading screen that is really slow.
- There's an aspect of being "lazy" where computionally heavy things are only loaded when needed. Or maybe there's a special type of animation that is only worth while if there are enough resources.
- Not every feature is needed ..or at all, so the application needs to accout for it.
- React can do his by susepsnse.. or using imports when the dependency is needed (code-splitting)
- https://react.dev/blog/2022/03/29/react-v18#new-suspense-features

## Research

- lazy loading images with `<img loading="lazy">`
  - loading images when scroll position is at the image
- rendering above the fold....use minmum amount of css/content/scripts ..to load the content that users see
- Async HTML fragments
- Next.Js ... with server components...and SSR..is helping things to render more quickly
