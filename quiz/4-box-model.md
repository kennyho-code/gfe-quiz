Explain your understanding of the box model and you would tell the browser in CSS to render your layout in different box models.

https://www.greatfrontend.com/questions/quiz/explain-your-understanding-of-the-box-model-and-how-you-would-tell-the-browser-in-css-to-render-your-layout-in-different-box-models

## Initial Thoughts

What is the box model? HTML is laid out in boxes, where elements of divs are used. They can be analogous of boxes. The box model includes the margin, how far an element is from it's respective element that is near it ("relative"). Padding, how much space is inside the element to the respective element inside. Because the default box-sizing just calculates the size of the element, and not it's padding and margin, there is usually a "reset" to include the padding and margin.

How the default box model looks? `content-box`
margin | padding | content
padding and margin is not including in the sizing.

How the reset looks like: `border-box`
|margin + padding + content

## Research

https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model
In CSS, everything has a box around it... the atomic model...is that every element has a box around it.

What makes up the box:

- content box: inline-size, block-size, width, and height
- padding-box: padding property
- border-box: border property
- margin-box: margin property

Two types of box models:

- Standard: content-box (padding, margin, border, not included - but added to the content)
- Alternative: border-box (includes padding, border, margin)

if width not specified, then it will expand the viewport with

Box can be displayed in respect externally with display `block`, Properties are pushed away the box. Width takes 100%. Some elements display default is `inline` while most are `block`. Inline
goes within the flow, usually horizontally. Block goes vertically.

https://www.samanthaming.com/pictorials/css-inline-vs-inlineblock-vs-block/
block - width and height are rspected, goes vertically
inline - width and height are not respected, goes horizontally
inline-block - width and height are respected, goes horizontally

Elements inside of a box can be displayed using `flex` or `grid`. `flex` focuses on the main axis and cross axies. (The direction of the axis is dependent on which `flex-direction` is used). Grid layouts focuses on putting elements in columns and rows.
