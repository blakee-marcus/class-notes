# Difference between Stacks & Queues #

In JavaScript, both a stack and a queue are linear data structures that store a collection of elements. However, they differ in the order in which elements are removed from the collection.

A stack follows the Last In, First Out (LIFO) principle, meaning that the last element added to the stack will be the first one to be removed. This is similar to a stack of plates, where you would add a plate to the top of the stack and remove a plate from the top of the stack. In JavaScript, you can implement a stack using an array or a linked list, and common operations include push, pop, and peek.

A queue, on the other hand, follows the First In, First Out (FIFO) principle, meaning that the first element added to the queue will be the first one to be removed. This is similar to a line or a queue, where the first person in line is the first one to be served. In JavaScript, you can implement a queue using an array or a linked list, and common operations include enqueue, dequeue, and peek.

Here's a summary of the main differences between stack and queue:

* Stack follows LIFO principle while Queue follows FIFO principle.
* Stack mainly focuses on last element (Top) while Queue mainly focuses on first element (front).
* Stack contains a `peek()` method while Queue has a `front()` method
* Stack insert operation is called a `push()` method while Queue insert operation is called `enqueue()` method
* Stack delete operation is called a `pop()` method while Queue delete operation is called `dequeue()` method

| Stacks |	Queues |
| ------ | --------|
| Stacks are based on the LIFO principle, i.e., the element inserted at the last, is the first element to come out of the list.	| Queues are based on the FIFO principle, i.e., the element inserted at the first, is the first element to come out of the list.
Insertion and deletion in stacks takes place only from one end of the list called the top. | Insertion and deletion in queues takes place from the opposite ends of the list. The insertion takes place at the rear of the list and the deletion takes place from the front of the list.
Insert operation is called push operation. |	Insert operation is called enqueue operation.
Delete operation is called pop operation. |	Delete operation is called dequeue operation.
In stacks we maintain only one pointer to access the list, called the top, which always points to the last element present in the list.	| In queues we maintain two pointers to access the list. The front pointer always points to the first element inserted in the list and is still present, and the rear pointer always points to the last inserted element.
Stack is used in solving problems works on recursion. | Queue is used in solving problems having sequential processing.
Stack does not have any types. | Queue is of three types – 1. Circular Queue 2. Priority queue 3. double-ended queue.
Can be considered as a vertical collection visual. | Can be considered as a horizontal collection visual.

[Read More Here](https://www.geeksforgeeks.org/difference-between-stack-and-queue-data-structures/)

Stack and Queue are similar in some aspects, but they have different use cases. Stack is mainly used in situations where you need to maintain a history of elements, and you want the latest element to be the first one to be processed. Queue is mainly used in situations where you need to maintain a sequence of elements, and you want the first element to be the first one to be processed.