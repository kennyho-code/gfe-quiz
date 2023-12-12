# What language constructs do you use iterating over object properties and array items?

## Initial Thoughts

- Javascript objects are "containers" that contain "properties" as keys in which they pair up with a "value". When using an object, a pointer is created from a variable declaration to the object's address in heap memory.

```
const a = {}

```

Create a variable a that has a reference to the `{}` object in heap memory.
We can create objects like so

```
{
    ....add initial properties and values
}

Object.create(null)

class foo{
    constructor(){
        ...initial properties with values
    }
}

```

Arrays are also objects

```
typeof [] === "object"

```

## To tell a difference between an plain javascript object and an array, the static function `Array.isArray` is used.

Both of these datastructures can be iterating over

For objects, since it it isn't iterable... helper functions like Object.entries(someObject) need to be used.

```
const o = {a: 1, b:2}
for(let [key, value] of Object.entries(o)){
}
```

`Object.entries(o)` turns it into a an array of arays like so `[[p1, v1], [p2, v2]]`.

Because it turns to an array, there are different ways of iterating

standard way

```
for(let i = 0; i < array.length; i ++){
    let item = array[i]
}

```

`of`

```
for(let item of array){
}
```

`forEach`

```
array.forEach((item) => {})
```

Because of the callback in `forEach`, it is slower:
https://stackoverflow.com/questions/43821759/why-array-foreach-is-slower-than-for-loop-in-javascript

## Resarch

`in` can be used to get properties in objects

```
const o = {a: 1, b: 2}
for(let key in o){
    let val = o[key]
}

```

`while`

```
i = 0;
while(i < array.length){
    let item = array[i];
    i++;
}

```

- Get enumerable properties https://developer.mozilla.org/en-US/docs/Web/JavaScript/Enumerability_and_ownership_of_properties
- use `Object.hasOwn` to check for property in object, or `Object.prototype.hasOwnProperty.call(object.key)`

```
Object.keys(obj).forEach((property) => {

    let val = obj[property]
})
```

```
Object.getOwnPropertyNames(obj).forEach((property) => {
    let val = obj[property];
})
```

- `for-of` used for `iterable protocol`: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols#the_iterable_protocol, used in `String`, `Array`, `Map`, `Set`...etc.

```
const arr = ['a', 'b', 'c']
for(let [index, elem] of arr.entries()){
}
```
