# Linked list
## What is a linked List. 
- A linked list is similar to a regular list. One of the main differences is how the data is stored. In a regular list a block of memory is allocated
to the list. When the list runs outs of memory it goes back to the memorya and allocates more. In a linked list there are many elemets. These elements are called nodes. 
Each node contains the data and pointers to where the next section of memory is.
## Diagram explaining Linked Lists

- linked list
![Linked List](Linked_List.jpg)
- double linked list
- ![Linked List](double_linked_list.jpg)

## linked list Commands
| Operation               | Description                    | Python Syntax               | Big O Performance |
| ------------------------| ------------------------------ | ----------------------------| ----------------- |
| insert_head(value)      |  Add value before head of stack| my_deque.appendleft(value)  | O(1)              |
| insert_tail(value)      | Add value after tail           | my_deque.append(value)      | O(1)              |
|insert(,value)           | Adds value after node n        | my_deque.insert(n,value)    | O(n)              |
|remove_head()            |Removes the head of the list    | value = my_deque.pop()      | O(1)              |
|remove_tail(index)       |Removes the tail of the list    | value = my_deque.pop()      | O(1)              |
|remove(i)                |Removes node "i"                | del my_deque[i]             | O(n)              |
|size()                   |Return size of list             | length = len(my_deque)      | O(1)              |
|empty()                  | if len(...                     |                             |                   |



o	Example of Linked List
o	Problem to solve


