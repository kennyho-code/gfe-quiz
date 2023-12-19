# What's the difference between an attribute and property?

## Initial thoughts

propertyes are keys in javascript objects ... like doing

```
{"a": "hello"}
```

There is an "a" property...with a "hello" value.

## Research

- Css property as in .... color is a style property

```
div {
    color: black;
}

```

- html attribute ..

```
<div class="">
```

...there is an class attribute to the div element.

https://www.greatfrontend.com/questions/quiz/whats-the-difference-between-an-attribute-and-a-property

- attributes defined in the html markup
- properties are defined in the dom..

```
const input = document.querySelector('input');
console.log(input.getAttribute('value')); // Hello
console.log(input.value); // Hello
```

```
console.log(input.getAttribute('value')); // Hello
console.log(input.value); // Hello World!
```
