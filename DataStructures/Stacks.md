# What?

A stack is an abstract data type that serves as a collection of elements, with two principal operations: push, which adds an element to the collection, and pop, which removes the most recently added element that was not yet removed.

A stack uses LIFO (last-in first-out) ordering.

# Why?

Unlike an array, a stack does not offer constant-time access to the ith item. However, it does allow constant­time adds and removes, as it doesn't require shifting elements around.

# When?

Recursive Algorithms - sometimes you need to push temporary data onto a stack as you recurse, but then remove them as you backtrack (for example, because the recursive check failed). A stack offers an intuitive way to do this.

A stack can also be used to implement a recursive algorithm iteratively.

