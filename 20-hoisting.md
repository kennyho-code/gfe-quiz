# Explain hoisting

## Initial Thoughts

Hoisting -- it's formal definition is to bring up but in programming, it means bringing up variable declaratiosn to the top of the scope. For instance

```
console.log(var1); // undefined
var var1;
```

Using pre-es2015 syntax would "hoist" up var1 in compiliation, and when it's run, it would be undefined.

ES2015 keywords like `let` and `const` do not hoist, so there will be an error doing

```
console.log(var1) // ReferenceError: Cannot access 'var1' before initialization
let var1;
```
