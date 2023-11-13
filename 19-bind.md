#Explain Function.prototype.bind

## Initial Thoughts
Function is an object, and it's prototype has a key of bind. What bind contains is a function that allows an external this, `thisArg` to be used in it's scope. Bind is called with `someFunc.bind(thisArg, arg1, arg2, args...)`, and it also allows to bind arguments to the function as seen with arg1, arg2, args...; Once everything is binded with the `thisArg` and it's arguments, the function can then be invoked with `()`. 

## Research
```
this.x = 9; // global

const module = {
    x: 81,
    getX() {
        return this.x;
    }
}

console.log(module.getX()); // 81 gets from module scope

const retrieveX = module.getX;
console.log(retrieveX()) // gets from global scope


const boundGetX = retrieveX.bind(module);
console.log(boundGetX()); // 81 gets from module scope

```

