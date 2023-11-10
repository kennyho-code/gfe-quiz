# Whats the difference between `==` and `===`?

## Inital Thoughts

`==` is a loose comparison while `===` is a strict comparison. Loose comparisons have similar values that "equal" to each other. While Strict must be exactly the same. For instance, objects that are similar, but not the same... meaning that they have the same keys values, loose comparisons will be true while strict comparisons would be false. It's false because objects have variables that point to their address in memory. There's a concept of "truthiness" and "falsiness". Truthiness and falseiness loosely compare similar values to be true and false if they aren't similar.

## Research

- `==` does type conversion, then compares
- `===` does not do type conversion, then compares, special handling for `NaN` and `-0` and `+0`
- `Object.is()` does no type conversion, no special handling for `NaN` and `-0` and `+0
- SameValueZero: number equality but `-0` and `+0` are equal, used in prototpyes like `Array.prototype.includes()`, Map and Set comparisons

Equality Table:
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness#comparing_equality_methods

https://www.greatfrontend.com/questions/quiz/what-is-the-difference-between-double-equal-and-triple-equal
