# Why you would use a `srcset` attribute in an image tag?

## Initial thoughts?...

## Research

- Problems with images via resolution on different screen sizes
- `srcset` and `sizes` allow for ..allowing a combination of different img sizes and resolutions..

```
<img
  srcset="elva-fairy-480w.jpg 480w, elva-fairy-800w.jpg 800w"
  sizes="(max-width: 600px) 480px,
         800px"
  src="elva-fairy-800w.jpg"
  alt="Elva dressed as a fairy" />

```

- These are responsive images
  https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images
- https://www.greatfrontend.com/questions/quiz/why-you-would-use-a-srcset-attribute-in-an-image-tag

- NextJs has an `Image` component https://nextjs.org/docs/pages/api-reference/components/image#responsive-images
