# What advantage is there for using the arrow syntax in a constructor?

## Initial Thoughts

- arrow function syntax is, `() => {}`, which equates to a function that has no `this` keybinding...somebenefits is that it has has a shorter syntax....you can easily pass it through inline via in `map`...etc. Really anything with a callback parameter.

## Research

https://www.greatfrontend.com/questions/quiz/what-advantage-is-there-for-using-the-arrow-syntax-for-a-method-in-a-constructor

- `function` is `this` "aware", so it able to change the "context" with `.bind(newContext)`, `.call(newContext, ...args)`, or `apply(nextContext, [...args])`
- when using those functions with an arrow function...the context won't change so it's just lexically scoped.
