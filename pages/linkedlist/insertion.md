[**<-Back**](/README.md)

# Insertion in Linked List

Given a Linked List, the task is to insert a new node in this given Linked List at the following positions:

- [**At the font of the linked List.**](#insertFirst)
- [**At the end ot the Linked List.**](#insertend)
- [**After a given node.**](#aftergiven)

<h2 id="insertFirst"> 1 -> Insert a Node at the Font of Linked List</h2>

    To inset a node at the start of a Linked List, we need to :
    - Make the first node of Linked List linked to the new node
    - Remove the head from the original first node of Linked List,
    - Make the new node as the head of the Linked List,

   <img src="../../assets/Linkedlist_insert_at_start.png" width="700" height="180" />

### Example Javascript

```javascript
// Using Class
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }

  insertFirst(data) {
    const newNode = new Node(data);
    newNode.next = this.head;
    this.head = newNode;
  }

  print() {
    let current = this.head;
    while (current) {
      console.log(current.data);
      current = current.next;
    }
  }
}

const Linked = new LinkedList();

Linked.insertFirst(20);
Linked.insertFirst(200);
Linked.insertFirst(2000);
Linked.insertFirst(20000);
Linked.print();

/*
 * Output
 * 20000
 * 2000
 * 200
 * 20
 * /
```

<h2 id="insertend"> 2 -> Insert a Node at the End of Linked List</h2>

    To insert a node end of the linked list, we need to :
    - Go to last node of the linked list
    - Change the next pointer of last node from Null to the new node
    - Make the next pointer of new as NULL to show the end of Linked list

   <img src="../../assets/Linkedlist_insert_last.png" width="700" height="180" />

## Example Javascript

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}
class LinkedList {
  constructor() {
    this.head = null;
  }

  insertEnd(data) {
    const newNode = new Node(data);

    if (this.head === null) {
      this.head = newNode;
      return;
    }

    let current = this.head;
    while (current.next) {
      current = current.next;
    }
    current.next = newNode;
  }

  print() {
    let current = this.head;
    while (current) {
      console.log(current.data);
      current = current.next;
    }
  }
}

const Linked = new LinkedList();
Linked.insertEnd(80);
Linked.insertEnd(800);
Linked.insertEnd(8000);
Linked.insertEnd(80000);
Linked.insertEnd(800000);
Linked.print();

/**
 * Output
 * 80
 * 800
 * 8000
 * 80000
 * 800000
 */
```

<h2 id="aftergiven"> 3 -> Insert a Node after a Given Node in Linked List</h2>

    To insert a node after a given node in a linked list, we need to:
    - Check if the node exists or not,
      1. if it do not exists,
        - terminate the process.
      2. if the given node exists,
        - Make the element to be inserted as a new node,
        - Change the next pointer of given node to the new node.
        - Now shift the original next pointer of given node to the next pointer of new node

   <img src="../../assets/Linkedlist_insert_middle.png" width="700" height="180" />

## Example Javascript

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}
class LinkedList {
  constructor() {
    this.head = null;
  }

  insertEnd(data) {
    const newNode = new Node(data);

    if (this.head === null) {
      this.head = newNode;
      return;
    }

    let current = this.head;
    while (current.next) {
      current = current.next;
    }
    current.next = newNode;
  }

  insertAfter(targetData, newData) {
    const newNode = new Node(newData);

    let current = this.head;
    while (current) {
      if (current.data === targetData) {
        newNode.next = current.next;
        current.next = newNode;
        return;
      }
      current = current.next;
    }
    console.error(
      `Node with targetData '${targetData}' not found in the linked list.`
    );
  }

  print() {
    let current = this.head;
    while (current) {
      console.log(current.data);
      current = current.next;
    }
  }
}

const Linked = new LinkedList();
Linked.insertEnd(10);
Linked.insertEnd(100);
Linked.insertEnd(1000);
Linked.insertEnd(10000);
Linked.insertEnd(100000);
Linked.insertAfter(100, 200);
Linked.insertAfter(200, 300);
Linked.print();
/**
 * Output
 * 10
 * 100
 * 200
 * 300
 * 1000
 * 10000
 * 100000
 */

Linked.insertAfter(2000, 3000);
Linked.print();
/**
 * Output
 * Node with targetData '2000' not found in the linked list.
 * 10
 * 100
 * 200
 * 300
 * 1000
 * 10000
 * 100000
 */
```
