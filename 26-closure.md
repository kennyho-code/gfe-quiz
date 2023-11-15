# What is a closure, and how and why would you use one?

## Initial Thoughts

During compliation, during the lexxing step, breaking apart the text to make token words...scopes are assigned to each variable. You have global scopes, function scopes, and block scopes. From largest to smallest. When reaching for a variable in the smaller scope, it looks there first, then bubbles up until it reaches the global scope. If it can't be found, then there's a reference error.

A closure is a term that is used when scope is used within a function to persist memory. For instance

```
function outer(){
    const persistedMemory = "I'm a closure";
    return function(...args){
        console.log("here we can access persisted memory")
    }
}
```

In the example above, you can create a closure which persists memory when created a function;

```
const f1 = outer();
f1() // has access to persisted memory
```

better example

```
function add1(){
    let counter = 0;
    return function() {
        counter++;
        console.log(counter);
    }
}
const a = add1();
a() // 1
a() // 22
```

Closures also allow for priviate variables in objects like so

```
const x = {
    counter: 0,
    add1: function(){
        this.counter++;
        console.log(this.counter);
    }
}

```

## Research

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Closures

- function bundled around it's surround state -- lexical environment
  https://www.greatfrontend.com/questions/quiz/what-is-a-closure-and-how-why-would-you-use-one
