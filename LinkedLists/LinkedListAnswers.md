    ```python
    def circular_list(self):
        self.tail.next = self.head
        self.head.prev = self.tail
    
    def reverse(self):
        current = self.tail
        while current is not None:
            yield current.data
            current = current.prev
            
   ```
