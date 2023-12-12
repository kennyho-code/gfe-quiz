# Explain the differences between the usage of `foo` between `function foo() {}` and `var foo = function()`

## Initial thoughts

`function foo(){}` is a declared function while `var foo = function` is a variable foo that is initialized and declaration to an anonymous function; Both superficially can be called like `foo()`. both var and function decelarations are hoisted; howoever the variable would just be undefined, where as the function declaration wouldn't be.

This would work

```
foo()
function foo(){}
```

while this wouldn't

```
foo()
var foo = function(){}
```

https://www.greatfrontend.com/questions/quiz/explain-the-differences-on-the-usage-of-foo-between-function-foo-and-var-foo-function
