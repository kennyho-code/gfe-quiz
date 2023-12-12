# What are `data-` attributes good for?

## Initial Thoughts

- The `data-{}` property allows you to insert a string that can be used to pass in data that is paired with the element or it can be used as an identififier....for instance `<div data-test-id="someTestId"` can be used in react to get the element by `getElementByTestId("someTestId)`.

## Research

https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes

- javascript can access assess like `div.dataset.{someField}
- css can also access it like

```
.someClass{
    content: attr(data-parent)
}
```

```
element[data-columns="3"]{
    ...
}
```

https://www.greatfrontend.com/questions/quiz/what-are-data-attributes-good-for

- generally not good practice...to pass whatever data because it exposes it in the dom...it can also affect DOM reconcillation
