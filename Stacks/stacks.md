**Data Structure 1: Stackss**


---

## **Introduction**
#### Understanding Stacks

Stacks are a unique data structure that is often called "Last In, First Out" (LIFO). This data structure can be implemented using a list and "LIFO" means that the last thing put into it, is the first thing that has to be removed. You can imagine something similar to a gun magazine, in order to retrieve the first bullet put in, you have to pull out every single bullet before that one.

<!-- Stack image -->
<figure>
<img src="https://miro.medium.com/max/1280/0*SESFJYWU5a-3XM9m.gif">
<figcaption align= "center"> <a href=https://medium.com/@1991dharapatel/javascript-stacks-and-queues-136fabab8359>Image source</a></figcaption>
</figure>

#### Understanding Stack operations

Stacks are relavively simple in the operations you can do to them. You can add things to the list, remove things from the list, determine the size of the list, and return a boolean value if the list is empty.

The way that we add and remove from a stack is using push and pop commands. The push command adds to the end of the list and the pop command removes from the end of the list. Much like with our magazine example above, there is no removing from the middle or bottom of the list.

```python
# Push

stack = []
for letter in text:
  stack.append(letter)
  
# Pop
  print(stack.pop())
```

the last two operations we can perform on are stack are determinging the size of the list and if the list is empty, these two operations are very commonly used together.

```python
  # Size/Empty
  def size_empty(stack)
    length = len(stack)   # This line determines the size of the stack.
    return if length == 0: # This line returns true if the size is empty.
```

#### Big O Efficiency & Limitations

Stacks although limited in their capacity stacks are very efficient at what they do. Since pushing and popping are only operations you can do to the end of the list, all the operations listed above have a O(1) efficiency.

Lets take our gun magazine example from above. What would happen to the first bullet if we loaded and unloaded a 10-round magazine? a 100-round magazine? A 500-round magazine? If we look at each bullet as if it's a data point, you would see that the more items we put on the stack the more that first data point has to sit around. That's one of the weaknesses of a stack data structure. A "Last in, First out" data structure could have that first data point sitting around for a long time depending on how much you are adding to the stack.

Another limitation is that you can't edit anything in the middle or beginning of the stack. If you want to access a piece of data in the middle of your stack, you have to remove all data that was placed after, until you get to the data you are trying to edit.

#### Strengths & Real World Applications

Although limited in it's capacity, what a stack is really good at is keeping track of where you are. In fact, you might not know it, but you use a stack almost every time you program and encounter a bug.

<!-- Stack image -->
<figure>
<img src="https://i.stack.imgur.com/Kq1GU.png">
</figure>

When you encounter an error, the debugger shows you the last functions or lines of code that your program hit before it encountered the error. This ouput comes directly from your computer as it automatically pushes and pops from the function stack.

The stack also has uses outside of programming! The popular card game "Magic the Gathering" applies a physical stack when you want to interact with your opponents cards. 

#### Coding example

Lets take the magic example from above and create a theoretical game. For additional context, P1 is a MonoR player and P2 is a dirty Simic player at 6hp.

```python
class GameStack:
  def __init__(self):
    self.stack = []
    
  def add_card(self,card):
    self.stack.append(card)
  
  def remove_card(self):
    return self.stack.pop()
    
  def length(self):
    return len(self.stack)
  
game = GameStack()
game.add_card("Shock") #P1
game.add_card("Shock") #P1
game.add_card("Counter Spell") #P2
game.add_card("Lightning Bolt") #P1
game.add_card("Spell Pierce") #P2
game.add_card("Heartfire") #P1
# print(game) ["Shock", "Shock", "Counter Spell", "Lightning Bolt", "Spell Pierece", "Heartfire"]
game.remove_card()
# print(game) ["Shock", "Shock", "Counter Spell", "Lightning Bolt", "Spell Pierece"]
```

#### Problem set

Now it's your turn. Write code that shows the top 3 cards of Player 1's graveyard. You can use the cards above (in stack order) as that players current graveyard.
