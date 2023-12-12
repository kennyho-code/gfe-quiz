What are the difference between var, let, and const?
https://www.greatfrontend.com/questions/quiz/what-are-the-differences-between-variables-created-using-let-var-or-const

## Initial Thoughts

These are all types of keywords to initializing variables variables.
Using `var` was the "old" way of usving variables. But the more modern syntax, `let` and `const`
allows for the ability and inabilit to redeclare the variable. `let` allows for the continuation of
declaration. For ex:

```
let a = 1;
a = 2;
```

But `const` doesn't allow for the redeclaration.

```
const a = 1;
a = 2; // Uncaught TypeError: Assignment to constant variable.
```

using the old `var` keyword lets for reassignment

```
var a = 1;
a = 2;
```

## Research

mdn

`let` - The let declaration declares re-assignable, block-scoped local variables, optionally initializing each to a value.
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let

`const` - The const declaration declares block-scoped local variables. The value of a constant can't be changed through reassignment using the assignment operator, but if a constant is an object, its properties can be added, updated, or removed.
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/const

`let` and `const` was introducted in `es2015/es6`. `var` should really only be used in legacy cases.

- `let` and `const` can only be accessed `block` scope ... only within the curly braces
- `var` is hoisted, meaning that it can be accessed anywhere in the function ... it will log out `undefined` where `const` and `let` will throw a `ReferenceError` if not declared before it's used.
