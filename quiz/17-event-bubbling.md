# Describe event bubbling

https://www.greatfrontend.com/questions/quiz/describe-event-bubbling

## Initial Thoughts

What is an event. An event is when an action is made. When that happens, it usually is "listened", in which action can be taken on the event.

## Research

https://developer.mozilla.org/en-US/docs/Web/API/Event

- can be triggered by user action or programatically `HTMLElement.click()`
- can also define the devent via the `Event` interface, and send the event with `EventTarget.dispatchEvent()`;
- When there are lots of events, ordering is created with "event bubbling and capturing"
- when an event listens on a child and it's ancestors

```

<body>
    <div id="container">
        <button>click me!</button>
    </div>
</body>


function hanleClick(e)

...

document.body.addEventListener('click', handleClick);
container.addEventListener('click', handleClick);
button.addEventListener('click', handleClick);

```

the event listeners trigger form the inner most so the outer most.

1. button
2. container
3. body

to stop event bubbling use `event.stopPropagation()`;
https://www.greatfrontend.com/questions/quiz/describe-event-bubbling
