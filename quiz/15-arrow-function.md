# Can you offer a use for the new arrow => funciton syntax?

## Initial Thoughts

Functions are usually created with the `function(){}` syntax. But ES2015 allows to use the arrow syntax like so `const = () => {}`. The main difference is how `this` behaves.

`this` in the the `function` syntax refers to the scope of which the object is called on...

```
{
    foo: function() {
        console.log(this);
    }
}

```

Where as

```
{
    foo: () => {
        console.log(this);
    }
}
```

Does noes refer to the scope of which the object is called on, but rather the scope of which the function is defined. This will log the global object.

## Research

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions

Arrow Functions
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions

- arrow function is called expression
- doesn't have it's own bindings to `this`, `arguments`, or `super`
- more readability, especially within functional style, it's shorter syntax allows to be more expressive.
- const, this is helpful when accessing global this... especialy in the browser that injects window libraries into the global scope
  https://www.greatfrontend.com/questions/quiz/can-you-offer-a-use-case-for-the-new-arrow-greater-function-syntax-how-does-this-new-syntax-differ-from-other-functions
