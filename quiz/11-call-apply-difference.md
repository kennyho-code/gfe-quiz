# What is the difference between `call` and `apply`?

## Inital Thoughts
How are they similiar? They are prototype functions on the Function object. For instance we can do func1.call(...) and func1.apply(...)

What are the differences. Their parameters are different after the first argument. Both first arguments take in their `thisArg`... meaning the `this` object it is applied to..which mean they can "bind" to data in the scope that is passed via the argument. The 2nd arguments for `call` take in a list of arguments ... via (...args)... meaning that there it could be `arg1, arg2, arg3`. `apply` takes in an array of arguments like so: `[arg1, arg2, arg3]`.

## Research
`apply`
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply

`call`
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call