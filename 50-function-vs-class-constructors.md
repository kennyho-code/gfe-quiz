# Whatare the differences between ES2015 function and class constructors

## Initial Thoughts

- Traditionally objects could only be made with functions like so...

```
function createObj(val1, val2) {
    return {
        prop1: val1,
        prop2: val2
    }
}

const someObject = createObj("1", "2");
```

But now es2015 created some syntactic sugar with classes liek so

```
class SomeObject{
    constructor(val1, val2){
        this.prop1: val1;
        this.prop2: val2;
    }
}

const someObject = new SomeObject("1", "2");

```

There are some differences under the hood.. While functions create objects, classes create instances....which is more memory efficient.

## Research

```
function Person(name){
    this.name = name;
}

class Person{
    constructor(name){
        this.name = name;
    }
}
```

Main difference is inheritance

```
function Student(name, studentId){
    Person.call(this, name);

    this.studentId = studentId;
}
Student.prototype = Object.create(Person.prototype);
Student.prototype.constructor = Student;


Class Student extends Person {
    constructor(name, studentId){
        super(name);
        this.studentId = studentId;
    }
}
```

Although class syntax is less verbose...we have to remember that it's wiring up the prototypes behind the scenes.
