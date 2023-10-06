[**<-Back**](/README.md)

# Singly linked list

This is the simplest type of linked list,where each node only contains a data field and a link field to the next node in the list.

   <img src="../../assets/singlylinkedlist.png" width="700" height="180" />

## Some Problems on Singly Linked List

- **_Identical linked list :_** Two Linked List are identical when they have the same data and the arrangement of data is also the same. Write a function to check if the given two linked lists are identical.

  ```doc
      // Example
      Input a= 1->2->3->4, b = 1->2->3->4
      Output: Identical

      Input a= 1->7->3->4, b = 1->2->9->4
      Output: Not Identical
  ```

  **_To solve the problem follow the below idea_**

  ```doc
     To identify if two lists are identical, we need to traverse
     both list simultaneously, and while traversing we need to
     compare data.

  ```

- Traverse both the linked list simultaneously.
  - If the data of the node for on linked list is not
    equal to the node of the other one, then return false
- Return true, as both the linked list are identical
