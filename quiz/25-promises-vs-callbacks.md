# What are the pros and cons of using Promises instead of callbacks?

## Initial Thoughts

Promises are objects that allow for asynchronous code. It takes a function with the parameters of (resolve, reject).

```
const p = new Promise((resolve, reject) => {
  // do something
  resolve("some result")

  // if something is bad you can reject
  reject("some error")
})

you can make it synchrnous by using async await

async function demo(){
    await p;
}
```

we avoid callback hell

This is callback hell.

```
some1Callback.then((result) =>
    anotherCallback(result).then((result2) =>
        yetAnotherCallback((result3) => {
            finally we do something.
        })
    )
)

```

## Research

https://www.greatfrontend.com/questions/quiz/what-are-the-pros-and-cons-of-using-promises-instead-of-callbacks

Pros for promises

- avoid callback hell
- more readable than `.then`
- Parallel async code with `Promise.all()`
- avoid
  - call the callback to oearly
  - call the callback too late
  - callback too few or too many times
  - fail to pass along necessary environment/parameters
  - swallow any errors/excpetions that may happen

Cons for promises

- slighly more complex code
- older browsers don't support promises (es2015) needs polyfill
