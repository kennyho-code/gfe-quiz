# What is the event loop?

## Initial Thoughts

Pure javascript, is ran through line by line from an `index.js` file. However this is synchrnous by nature. But since the internet is asynchronous in nature, requesting and responding from servers, there needs to be some sort of mechanism for javascript to model that behavior. The event loop is a cycle, which ticks, that takes events from the queues... either from promises, web browser functions, or node functions... it takes the events and puts them in the stack. Whatever task is put on the stack then gets executed. The event loop allows for more complex features such as async and node to live within the browser.

## Research

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Event_loop

all the console.logs gets called first, the callbacks via `setTimeout` get pushed on the queue, then
it's dequeued, put on the stack, and then calls the callback.

```
(() => {
  console.log("this is the start");

  setTimeout(() => {
    console.log("Callback 1: this is a msg from call back");
  }); // has a default time value of 0

  console.log("this is just a message");

  setTimeout(() => {
    console.log("Callback 2: this is a msg from call back");
  }, 0);

  console.log("this is the end");
})();

// "this is the start"
// "this is just a message"
// "this is the end"
// "Callback 1: this is a msg from call back"
// "Callback 2: this is a msg from call back"

```

- singled threated
- non-blocking
