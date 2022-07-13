**Data Structure 2: Linked Lists**


---

## **Introduction**
#### Understanding Linked Lists

Oftentimes when you store data, it is categorized by continuous memory. Each piece of data is right next to the next item in memory which means you can tranverse all the data relatively fast. Stacks that we just learned about work this way. 

However there is another way to store sets of data, and that is randomly within memory. This is how linked lists organize their data. Each data is at a random place in memory with no garuntee that it is next to or even close to the next element of data. In order to keep track of our data and prevent it from getting lost we link each element (called a *node* in linked lists) to the next element in the sequence. So each node points to the next node within memory and so on untill you reach the end of your list.

<!-- Linked List image -->
<figure>
<img src="https://i2.wp.com/algorithms.tutorialhorizon.com/files/2016/03/Doubly-Linked-List.png">
<figcaption align= "center"> <a href=https://algorithms.tutorialhorizon.com/doubly-linked-list-complete-implementation>Image source</a></figcaption>
</figure>

 The first node is called the head and by knowing where the head is, you can traverse your entire list by following the pointers. Most lists are also doubly linked, as you can see above, this allows you to traverse both forward and backwards from a node.

### Understanding Linked List Operations

The power of linked lists comes in understanding their operations. Just like other lists, you can add, remove, find the length and return a bool if the list is empty.
Because each node has a pointer to the nodes before and after it, inserting and removing do come with additional requirements. However, unlike other types of lists, when you edit your list, each node only effects the nodes with pointers to it. This means that you don't have to worry about expanding your list capacity or maintaining your contiguous memory. This ultimately means that editing especially at the front of your list is more efficient then other types of lists.

*We'll go over examples of each operation in our example down below.*

### BIG O Efficiency & Limitations

Due to the randomness of their memory allocation linked lists excel at some things other lists don't. Mainly when altering the first "node" or data point, linked lists are capable of doing it in O(1) time where others take O(n). Altering data at the end is also O(1) sharing efficiency with other lists, and altering data in the middle of the list is O(n). Notably it only has O(n) efficiency due to having to traverse the list to find the node you want to alter. Changing out the pointers of the node only take O(1) unlike other lists that have to move all the contiguous data points down which takes O(n).
