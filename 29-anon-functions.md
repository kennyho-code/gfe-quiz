# What's a typical use for anonymous functions?

## Initial thoughts

What's the opposite of anonymous functions, "named functions".

```
function namedFunction(){

}

```

named functions are hoisted, allows for a name during a stack trace

There are named function expressions which are not hoisted.

```
const x = () => {

}
```

Anonmous functions can appear like

```
function() {

}
```

or

```
() => {}
```

Anonymous functions are usually used within scope that needs to be passed in line .

```

filter((element) => { what is true or false about the element?} )
```

or in `React`

```
<button onClick(() => console.log("clicked")) />

```

Anonymous functions are concise and great when using it inline code.

## Research

```
(function () {
    // used within a scope

})();
```

https://www.greatfrontend.com/questions/quiz/whats-a-typical-use-case-for-anonymous-functions
