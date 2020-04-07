```python
class LinkedList:
    def __init__(self):
        self.head = None
    
    def print(self):
        element = self.head
        while element is not None:
            print(element.content)
            element = element.next
            
    def push_back(self, content):
        element = Element()
        element.content = content
        if self.head is None:
            self.head = element
        else:
            tail = self.head
            while tail.next:
                tail = tail.next
            tail.next = element
    
    def push_front(self, content):
        element = Element()
        element.content = content
        if self.head is None:
            self.head = element
        else:
            element.next = self.head
            self.head = element
    
    def remove(self, index):
        if index == 0:
            return self.pop()
        if index > self.size():
            return
        i = 0
        curr = self.head
        while i < index - 2:
            curr = curr.next
            i += 1
        curr.next = curr.next.next
            
    def pop(self):
        if self.head.next is not None:
            self.head = self.head.next
        else:
            self.head = None
            
    def peek(self):
        return self.head
    
    def size(self):
        i = 0
        element = self.head
        while element is not None:
            element = element.next
            i += 1
        return i

class Element:
    def __init__(self):
        self.content = None
        self.next = None
```


```python
my_list = LinkedList()
my_list.push_back("Hola soy el primero")
```
