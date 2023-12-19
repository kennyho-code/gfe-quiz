# What is use-strict

## Initial Thoughts

- It's an identifier of wanting to use a "stricter" mode of javascript.... It was during the es6 migration ...and most default javascript should already use the "strict"... one of the rules in basic javascript that it allows you to call variables via hoisting even if they are not declaraed. strict mode will give an error if that happens.

## Research

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Strict_mode

- eliminates javascript silent errors by changing them to throw errors
- fixes mistakes that allows javascript to be optimized
- prohibits earlier syntax for future ecmascript syntax
- can use "use strict" by scope ... logbal..function

https://www.greatfrontend.com/questions/quiz/what-is-use-strict-what-are-the-advantages-and-disadvantages-to-using-it

- makes it impossible to create global variables
- should be using strict mode by default
