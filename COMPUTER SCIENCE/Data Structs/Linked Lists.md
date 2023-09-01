## Definition

## Properties
- Insertion is easy -  just tack onto the front.
- Deletion is easy - once you find the element.
- Lookup is bad - have to rely on [[Linear Search]].
- Relatively difficult to sort - unless you're willing to compromise on super-fast insertion and instead sort as you construct.
- Relative small size-wise(not as small as [[Arrays]]).

# Singly-Linked Lists

[[Arrays]] suffer from a great inflexibility, imagine that we want a larger space than we previously thought ?

through a clever user of [[Pointers]], [[Dynamic Memory Allocation]] and [[Structs]], we can put the pieces together to develop a new kind of [[Data Struct]] that give us the ability to grow and shrink a collection of like values to fit our needs.

We call this combination of elements, when used in this way, a linked list.

A linked list [[Node]] is a special kind of struct with two members:
- Data or some [[Primitive Data Type]].
- A [[Pointers|pointer]] to another node of the same [[Defining Custom Data Types|type]].

In this way, a set of nodes together can be thought of as forming a chain of elements that we can follow from beginning to end.

In order to work with linked lists effectively, there are a number of operations that we need to understand:

1. Create a linked list when it doesn't already exist.
2. Search trough a linked list to find an element.
3. Insert a new [[Node]] into the linked list.
4. Delete a single element from a linked list.
5. Delete an entire linked list.



# Doubly-Linked Lists