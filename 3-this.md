# Explain how `this` works in JavaScript

https://www.greatfrontend.com/questions/quiz/explain-how-this-works-in-javascript

## Initial Thoughts

`this` is a keyword in programming languages is a reference an instance's scope. Because classes contain many instantations, creations of objects, they all hold their own types of values. For instance:

```
class Dog:
    constructor(name){
        this.name
    }

const dog1 = new Dog("fido");
const dog2 = new Dog("spot");
```

Have their own objects that instantianted the name in using `this`, the scope for each object.

This is the popular notion of this.

## Research
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this

However Javascript has some different behavior than most languages.
In the browser, when using `this`, it refers to the window object. In node, in refers to the global environment. Functions bind to their scope within the it's object. While a function expression `const x = () =>`, doesn't declare it, and refers to the global scope (window or global).

When `this` is unbounded, it refers to the global scope. But when bounded to a function, it refers to the object that it's bounded to.

```
function unboundedFoo(){
    console.log(this);
}
foo() // Window {0: global, 1: Window, window: Window, self: Window, document: document, name: '', location: Location, …}

const obj = {
    foo: unboundedFoo
}
obj.foo() //{foo: ƒ}

```

We can bind unbounded functions to get scope by doing `unboundedFunc.bind(obj)`

```
unboundedFoo.bind(obj)() // {foo: ƒ}
```
