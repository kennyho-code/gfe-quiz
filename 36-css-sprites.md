# Explain CSS sprites, and how you woudl implement on a page or site

## Initial Thoughts

A sprite created in CSS. What is a sprite? it's like an image. So CSS created image on a webpage?

## Research

https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images/Implementing_image_sprites_in_CSS

- using multiple images in the same image
- more bandwidth efficient as you don't have to request for different images
- using `background-image` with the image
- http2 doesn't have trouble downloading multiple images.

https://www.greatfrontend.com/questions/quiz/explain-css-sprites-and-how-you-would-implement-them-on-a-page-or-site

```
.icon {
  background-image: url('https://example.com/images/spritesheet.png');
  width: 24px;
  height: 24px;
}

.icon-cart {
  background-position: 0 0;
}

.icon-arrow {
  background-position: -24px 0;
}

```

```
<span class="icon icon-cart"></span>

<span class="icon icon-arrow"></span>
```
