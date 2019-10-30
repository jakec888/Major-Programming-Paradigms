# Linked Lists

A data structure that represents a sequence of nodes

# Why?

Linked lists offer some important advantages over other linear data structures. Unlike arrays, they are a dynamic data structure, resizable at run-time. Also, the insertion and deletion operations are efficient and easily implemented.

# What?

A linked list is a linear collection of data elements, whose order is not given by their physical placement in memory. Instead, each element points to the next. It is a data structure consisting of a collection of nodes which together represent a sequence.

# When?

1. you need constant-time insertions/deletions from the list (such as in real-time computing where time predictability is absolutely critical)

2. you don't know how many items will be in the list. With arrays, you may need to re-declare and copy memory if the array grows too big

3. you don't need random access to any elements

4. you want to be able to insert items in the middle of the list (such as a priority queue)
