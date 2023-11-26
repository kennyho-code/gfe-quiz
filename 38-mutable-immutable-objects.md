# Explain the difference between immmutable and mutable objects

## Initial Thoughts

- What is an object? An object is a "namespace" that is notated by `{}` in javascript you can add properties as "keys" and pair with a value. `{property1: 'val1', property2: 'value2'...}`
- Mutable means "changable" and immutable means unchangable. Typically objects are mutable as you can always add or change propertyes and values in objects. But there are ways to make objects "immutable" by doing `Object.freeze()` ... which doesn't allow the develoepr to change properties or values.

## Research

- Javascript has immutable objects like `Math` and `Date`;

ways to simulate immutability

```
Object.defineProperty(myObject, 'number', {
    value: 42,
    writable: false, //config here
    configurable: false, // config here
})
```

does not allow properties to be added but configurable is still `true`
``
let myObject = {
a: 2,
}

Object.preventExtensions(myObject)

```

Seal - like `preventExtensions` but can't add or change existing properties
`Object.seal()`

Freeze
`Object.freeze()`
- does not allow any mutability at all

https://www.greatfrontend.com/questions/quiz/explain-the-difference-between-mutable-and-immutable-objects
```
