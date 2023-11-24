#Difference between: `function Person(){}`, `var person = Person()`, and `var person new Person()`?

## Initial Thoughts

- `function Person(){}` is a function with the namespace of `Person`
- `var person = Person()`, invokes the `Person()` function and is assigned to the `person` variable
- `var person = new Person()`, new creates a empty contextual object, and `Person()` invokes the `Person` function, then it is assigned to the `person` variable.

## Research
https://www.greatfrontend.com/questions/quiz/difference-between-function-person-var-person-person-and-var-person-new-person
- `new Person()` creates a `Person` person object which inherits from the `Person.prototype`...alternative is `Object.create(Person.prototype)`
