#Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?

## Initial Thoughts

- Global scope means that the highest level of exposure ....that means using the `window` object .. to put some sort of or any variables... So once it's in global scope, then uses can then have entry way to the memory that is inside. This can cause a risk for security. Also if possible, principle of least priviledge should be kept in mind ...as things that aren't needed by some user..souldn't be exposed.
- The global namespace can also be polluted. IFFE..are also used...for closure to not use global scope.
