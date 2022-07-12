**Data Structure 2: Linked Lists**


---

## **Introduction**
#### Understanding Linked Lists

Oftentimes when you store data, it is categorized by continuous memory. Each piece of data is right next to the next item in memory which means you can tranverse all the data relatively fast. Stacks that we just learned about work this way. 

However there is another way to store sets of data, and that is randomly within memory. This is how linked lists organize their data. Each data is at a random place in memory with no garuntee that it is next to or even close to the next element of data. In order to keep track of our data and prevent it from getting lost we link each element (called a *node* in linked lists) to the next element in the sequence. So each node points to the next node within memory and so on.

<!-- Linked List image -->
<figure>
<img src="https://miro.medium.com/max/1280/0*SESFJYWU5a-3XM9m.gif">
<figcaption align= "center"> <a href=https://www.geeksforgeeks.org/data-structures/linked-list>Image source</a></figcaption>
</figure>

