Explain how prototypical inheritance works

## Initial Thoughts

Typical object orientd languages have inheritance by inheriting properies by their pairents. So this means in the constructor, a `super()` is called which takes all the
inheritance from all the ancestors.

```
class Animal...
 reproduce()
 eat
 sleep

class Mammal...
 ...construct from Animal
 hasHair
 makeMilk

class Dog...
 ...construct from Mammal that constructs from Animal
 bark
 wagTail
```

## Research

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain

This is done during compilation; where there could be a long chain of inheritance of ancestor properties.

Javascript does prototypical inheritance by looking through the `prototypical chain`... How do we set the ancestor... but when an object calls from inheritance,
it goes up through the chain, until it finds the property to the nearest ancestor.

What are the pros and cons? what are the mechanics of this?

flexibility, mutation at run time...

We can go through the chain like so

```
const o = {
  a: 1,
  b: 2,
  __proto__: {
    c: 3,
    a: 1,
    sayHello: function () {
      console.log("hello");
    },
    __proto__: {
      d: 5,
    },
  },
};
```

Getting `o.a`, it goes to the first layer. Getting `o.c` to the second prototype. The function `sayHello` also get's inherited. Getting `o.d` will go through to the third prototype. If we get `o.f`, it should give null, because the an object that doesn't have a object prototype is `undefined`.

We can add prototype dynamically like

```
function Person(name, age) {
  this.name = name;
  this.age = age;
}

Person.prototype.sayHello = function () {
  console.log(`hello from ${this.name}`);
};
```

It isn't memory optimized to keep creating objects say, so it can be constructed like so.

```
const people = [new Person("bob", 20), new Person("alice", 30)];
people[0].sayHello();
people[1].sayHello();
```

It can also use class notation

```
class Animal {
  eat() {
    console.log("eating");
  }
}

class Dog extends Animal {
  bark() {
    console.log("barking");
  }
}

const dog = new Dog();
dog.eat();

```

https://stackoverflow.com/a/19640910

Prototypes inheritace uses objecsts, instead of classes to inherit. Can create objects ex-nilhio. Out of thin air.
