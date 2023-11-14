#Explain the difference between synchronous and asynchronous functions

## Initial Thoughts

Synchronous and asynchrous affects how the flow of code goes through line by line. Synhronously is the usualy way of of executing code,
a => b => c => d. Each step needs to be executed before it goes the next step. Asynchronous on the other hand, some steps don't need to be finished before the next step is initiated. Lets say a starts, it doesn't have to finish, and b can then start... so forth. The ending times depending on how long the step takes makes the order of the steps finished no guaranteed. Some common async operations are like promises, which can take a certain of time, then resolve or reject at the end. The `setTimeout` function starts, and then waits for certain period of time, and then executes what's witin the function. However, the code after setTimeout still executes. To make `setTimeout` synchronous, it needs to be put under a `Promise object`, where you can async `await`... so that function needs to finish before it goes to the next line.

```

setTimeout(() => {
    console.log('time out finished');

}, 1000)

console.log('hello world');

```

"hello world" will still log out before "time out finished"

```
function sleep(wait){
    return new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve('time out finished');
    }, 1000)
})
}

async function demo(){
    await sleep(1000);
    console.log('console.log("hello world)');
}

```

"time out finished" will run before "hello world"

https://developer.mozilla.org/en-US/docs/Glossary/Asynchronous

- synchronous is blocking

https://greatfrontend.com/questions/quiz/explain-the-difference-between-synchronous-and-asynchronous-functions
