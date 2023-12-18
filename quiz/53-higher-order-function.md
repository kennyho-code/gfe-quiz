# What is a higher order function?

## Initial Thoughts

- Javascript is a built in paradigm with functional like features. To be functional means that functions are first class citizens... Meaning that they can be passed around ...add functionality to it...assigned to a variable...very much like primitives. So within this scope, what is a higher order function. Because functions can be passed down in arguments...and can be composed, functions can be made of functions ...so forth. A higher order function is a function that take in another function as an argument..and return a function. F of g of x.

## Research

- First-class function

```
function f(g){
    g();
}

function hello(){
    console.log("hello");
}

f(hello); // "hello"

```

https://www.greatfrontend.com/questions/quiz/what-is-the-definition-of-a-higher-order-function

primitive js hoc functions

- `map`, `forEach`, `reduce`

imperative

```
for(let ...){
    ...
}

declarative
```

items.map((item) => ...)

items.forEach((item) => ...)
...
