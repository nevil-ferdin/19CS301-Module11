# 19CS301-Module11
- **Name:** Nevil Joe Ferdin P 
- **Registration Number:** 212222050041
## ExNo: 11.1 Singly Linked List (Traversal, Search and Delete)
### Aim: 
To Write a function to traverse the linked list and display it in the following format.
### Algorithm:

STEP 1: Start.

STEP 2: Create a Node class.

STEP 3: Create a SinglyLinkedList class.

STEP 4: Define a method addNode(data).

STEP 5: Define a method display().

STEP 6: In the main program, create an object of SinglyLinkedList, read the number of nodes, add nodes using addNode, and call display().

STEP 7: End.

### Program:
```python
class Node:
    def __init__(self, data):
       self.data = data
       self.next = None
 
class SinglyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None
 
#Creating addNode() to add newly created nodes.
    def addNode(self, data):
        if self.tail is None:
            self.head = Node(data)
            self.tail = self.head
        else:
            self.tail.next = Node(data)
            self.tail = self.tail.next

 #Creating display() to print newly created nodes via traversing.
    def display(self):
        current=self.head
        while current is not None:
            print(current.data,end=" ")
            current=current.next
            
 
s = SinglyLinkedList()
n = int(input())
for i in range(n):
    data=input()
    s.addNode(data)
s.display()
```
### OUTPUT:

![image](https://github.com/user-attachments/assets/a61bf8f9-da12-411a-8c12-905abbd4a15a)

### Result: 
Thus, the given program is implemented and executed successfully .

## ExNo: 11.2 
### Aim: 
To Write a python program to insert an element at the starting of the singly linked list.

### Algorithm:

STEP 1: Start.

STEP 2: Define a Node class to hold data and a reference to the next node.

STEP 3: Define a CreateList class to manage the linked list with a head pointer.

STEP 4: In the addAtStart method, create a new node, link it to the current head, and update the head to this new node.

STEP 5: In the display method, traverse from the head and print each node's data; if the list is empty, print a message.

STEP 6: Create an object of the CreateList class and call addAtStart multiple times to add data to the front of the list.

STEP 7: Call the display method after each insertion to show the current state of the list and stop.

### Program:
```python
class Node:    
  def __init__(self,data):    
    self.data = data   
    self.next = None   
     
class CreateList:    
  def __init__(self):    
    self.head = None   
     
        
  def addAtStart(self,data):    
    new_node =Node(data)
    new_node.next=self.head
    self.head=new_node
     
  def display(self):    
    current = self.head    
    if self.head is None:    
      print("List is empty")  
      return
    else:    
        print("Adding nodes to the start of the list: ")   
        print(current.data) 
        while(current.next != None):    
            current = current.next  
            print(current.data)   
        
     

cl = CreateList()  
      
cl.addAtStart(1)    
cl.display()    
     
cl.addAtStart(2)    
cl.display()    
     
cl.addAtStart(3)    
cl.display()    
      
cl.addAtStart(4)    
cl.display()    
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/1be029f8-d994-4aaa-bb21-dc32ae811476)

### Result: 
Thus, the given program is implemented and executed successfully .

## ExNo: 11.3 
### Aim: 
To Write a python program to print the elements in forward and reverse direction in doubly linked list. 

### Algorithm:

STEP 1: Start.

STEP 2: Create a Node class with data, next, and prev attributes.

STEP 3: Create a DoublyLinkedList class with a head pointer.

STEP 4: Define a push method to insert a new node at the beginning of the list.

STEP 5: Define an append method to insert a new node at the end of the list.

STEP 6: Define a printList method to traverse and print the list forward and backward.

STEP 7: In the main program, create a DoublyLinkedList object, add nodes using push and append, then print the list.



### Program:
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
  
class DoublyLinkedList:
    def __init__(self):
        self.head = None
  
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        if self.head is not None:
            self.head.prev = new_node
        self.head = new_node
        
    def append(self, new_data):
        new_node = Node(new_data)
        if self.head is None:
            self.head = new_node
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node
        new_node.prev = last
        return
  
    def printList(self, node):
        print("\nTraversal in forward direction")
        last = None
        while node:
            print(node.data)
            last = node
            node = node.next

        print("\nTraversal in reverse direction")
        while last:
            print(last.data)
            last = last.prev
  
llist = DoublyLinkedList()
  
llist.append(6)
llist.push(7)
llist.push(1)
llist.append(4)
print("Created DLL is: ")
llist.printList(llist.head)

```
### OUTPUT:
![image](https://github.com/user-attachments/assets/227de075-f37d-4d0a-8d9b-417a47152de7)

### Result:
Thus, the given program is implemented and executed successfully .

## ExNo: 11.4 Doubly Linked List (Insertion and all operation)

### Aim: To Type a python function to insert words at the beginning and display the sentence in forward and reverse direction. 

### Algorithm:

STEP 1: Start.

STEP 2: Create a Node class with data, next, and prev attributes.

STEP 3: Create a DoublyLinkedList class with a head pointer.

STEP 4: Define a push method to add a new node at the beginning of the list.

STEP 5: Define a printList method to print the list forward and backward.

STEP 6: In the main program, read the number of words, use push to add each word at the start.

STEP 7: Call printList to display the list in forward and reverse order, then stop.

### Program:
```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
  
class DoublyLinkedList:
    def __init__(self):
        self.head = None
  
    def push(self, new_data):
        new_node=Node(new_data)
        new_node.next=self.head
        if self.head is not None:
            self.head.prev=new_node
        self.head=new_node
        
    def printList(self, node):
        print("\nTraversal in forward direction")
        while node:
          
            print(node.data, end=" ")
            last = node
            node = node.next
        print("\nTraversal in reverse direction")
        while last:
           
            print(last.data, end=" ")
            last = last.prev
            
llist = DoublyLinkedList()
  
x = int(input("Enter the number of words to display.\n"))
for i in range(x):
    a = input("Enter the data to push\n")
    llist.push(a)

llist.printList(llist.head)

```
### OUTPUT:
![image](https://github.com/user-attachments/assets/69ed985e-6b60-4d5f-815a-6f7f983bcead)

### Result: 
Thus, the given program is implemented and executed successfully .
