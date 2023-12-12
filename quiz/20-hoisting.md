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

- hoisting includes functions as well

temporal deadzone in block scopes... x used in the block, gives a ReferenceError

```
const x = 1;
{
  console.log(x); // ReferenceError
  const x = 2;
}
```

## Research

https://www.greatfrontend.com/questions/quiz/explain-hoisting

- actually let and const are hoisted by in `type 2` of hoisting, they are not initialized, so they are in the temporal deadzone
- can use hoisted functions

```
// Function Declaration
console.log(foo); // [Function: foo]
foo(); // 'FOOOOO'
function foo() {
  console.log('FOOOOO');
}
console.log(foo); // [Function: foo]
```
