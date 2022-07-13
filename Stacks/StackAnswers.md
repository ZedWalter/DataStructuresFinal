```python
  class Graveyard:
  def __init__(self):
    self.stack = []
    
  def add_card(self,card):
    self.stack.append(card)
  
  def remove_card(self):
    return self.stack.pop()

  def show_graveyard(self):
    for cards in range(1,4):
      print(self.remove_card())
    
graveyard = Graveyard()
graveyard.add_card("Heartfire")
graveyard.add_card("Lightning Bolt")
graveyard.add_card("Shock")
graveyard.add_card("Shock")
graveyard.show_graveyard() # Shock, Shock, Lightning Bolt
```
