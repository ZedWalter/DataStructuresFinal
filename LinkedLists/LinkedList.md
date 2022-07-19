**Data Structure 2: Linked Lists**

[Home](../welcome.md)
---

## **Introduction**

Oftentimes when you store data, it is categorized by continuous memory. Each piece of data is right next to the next item in memory which means you can transverse all the data relatively fast. Stacks that we just learned about work this way. 

However, there is another way to store sets of data, and that is randomly within memory. This is how linked lists organize their data. Each data is at a random place in memory with no guarantee that it is next to or even close to the next element of data. In order to keep track of our data and prevent it from getting lost we link each element (called a *node* in linked lists) to the next element in the sequence. So each node points to the next node within memory and so on until you reach the end of your list.

<!-- Linked List image -->
<figure>
<img src="https://i2.wp.com/algorithms.tutorialhorizon.com/files/2016/03/Doubly-Linked-List.png">
<figcaption align= "center"> <a href=https://algorithms.tutorialhorizon.com/doubly-linked-list-complete-implementation>Image source</a></figcaption>
</figure>


 The first node is called the head and by knowing where the head is, you can traverse your entire list by following the pointers. Most lists are also doubly linked, as you can see above, this allows you to traverse both forward and backwards from a node.

### Understanding Linked List Operations

The power of linked lists comes in understanding their operations. Just like other lists, you can add, remove, find the length and return a bool if the list is empty.
Because each node has a pointer to the nodes before and after it, inserting and removing do come with additional requirements. However, unlike other types of lists, when you edit your list, each node only effects the nodes with pointers to it. This means that you don't have to worry about expanding your list capacity or maintaining your contiguous memory. This ultimately means that editing especially at the front of your list is more efficient than other types of lists.

*We'll go over examples of each operation in our example down below.*

### BIG O Efficiency & Limitations

Due to the randomness of their memory allocation linked lists excel at some things other lists don't. Mainly when altering the first "node" or data point, linked lists are capable of doing it in O(1) time where others take O(n). Altering data at the end is also O(1) sharing efficiency with other lists, and altering data in the middle of the list is O(n). Notably it only has O(n) efficiency due to having to traverse the list to find the node you want to alter. Changing out the pointers of the node only take O(1) unlike other lists that have to move all the contiguous data points down which takes O(n).

The main disadvantage in using linked list is their additional complexity when altering data. Also, because each node also has pointers attached to it, each node contains more data than just the data wanting to be stored. So, although it doesn't take a one large individual chunk of storage, overall for the same amount of data, the storage amount is larger for linked list then for other types of lists. Traversing linked lists do take slightly more time then lists where data is contiguous which also leads to the last limitation of linked lists, there is no random access for them. Because of their dynamic memory you cannot access the data at a random point which you may want to do for certain applications.

### Strengths

Although not without its limitations above, linked lists do have a few things going for it. They are very efficient when inserting and deleting data. Perhaps their biggest strength is that they have no memory waste. They effectively utilize memory and have dynamic memory allocation meaning they expand and subtract in constant time leaving nothing wasted.

### Coding Example

``` python

class LinkedList:
    class Node:
        def __init__(self, data):
            self.data = data
            self.next = None
            self.prev = None

    def __init__(self):
        self.head = None
        self.tail = None

    #This is Head insertion
    def insert_head(self, value):
        new_node = LinkedList.Node(value)  
        if self.head is None:
            self.head = new_node
            self.tail = new_node
        else:
            new_node.next = self.head 
            self.head.prev = new_node 
            self.head = new_node      

    #This is Tail insertion
    def insert_tail(self, value):
        new_node = LinkedList.Node(value)
        if self.tail is None:
            self.head = new_node
            self.tail = new_node
        else:
            new_node.prev = self.tail
            self.tail.next = new_node
            self.tail = new_node
    
    #Remove the Head
    def remove_head(self):
        if self.head == self.tail:
            self.head = None
            self.tail = None
        elif self.head is not None:
            self.head.next.prev = None 
            self.head = self.head.next

    #Remove the Tail
    def remove_tail(self):
        if self.tail == self.head:
            self.tail = None
            self.head = None
        else:
            self.tail.prev.next = None
            self.tail = self.tail.prev
            
    #Insert in the Middle
    def insert_after(self, value, new_value):
        curr = self.head
        while curr is not None:
            if curr.data == value:
                if curr == self.tail:
                    self.insert_tail(new_value)
                else:
                    new_node = LinkedList.Node(new_value)
                    new_node.prev = curr      
                    new_node.next = curr.next  
                    curr.next.prev = new_node 
                    curr.next = new_node       
                return 
            curr = curr.next 

    #Remove from the Middle
    def remove(self, value):
        current = self.head
        while current is not None:
            if current.data == value:
                if current == self.head:
                    self.remove_head()
                elif current == self.tail:
                    self.remove_tail()
                else:
                    current.prev.next = current.next
                    current.next.prev = current.prev
                return #Exit function when done
            current = current.next #Loop to next node

    def replace(self, old_value, new_value):
        current = self.head
        while current is not None:
            if current.data == old_value:
                current.data = new_value
            current = current.next
        return

    #Move through the list forward
    def __iter__(self):
        curr = self.head 
        while curr is not None:
            yield curr.data 
            curr = curr.next 

    def __str__(self):
        output = "linkedlist["
        first = True
        for value in self:
            if first:
                first = False
            else:
                output += ", "
            output += str(value)
        output += "]"
        return output
```

## Problem set

Now it's your turn. Imagine you are playing a game of Uno, write a function to turn the linked list into a circular linked list. After you have that implemented, imagine someone plays a reverse card. Write a function to reverse traverse through the list!

[Solution](LinkedListAnswers.md)
