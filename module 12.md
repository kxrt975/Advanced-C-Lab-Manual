## EXP NO:26 — C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST

### Aim
To write a C program to display stack elements using linked list.

### Algorithm
1. Define a structure Node with members `data` and `next`.  
2. Use a global pointer `top` to represent the stack top.  
3. Create a function `display()` to print all elements from `top` to `NULL`.  
4. Use a loop to traverse and print stack elements.  

### Program
~~~c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *top = NULL;

void push(int value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = top;
    top = newNode;
}

void display() {
    struct Node *temp = top;
    if (temp == NULL) {
        printf("Stack is empty\n");
        return;
    }
    printf("Stack elements are:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    push(10);
    push(20);
    push(30);
    display();
    return 0;
}
~~~

### Output
```
Stack elements are:
30 20 10
```

### Result
Thus, the program to display stack elements using linked list is verified successfully.

---

## EXP NO:27 — C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST

### Aim
To write a C program to pop an element from the given stack using linked list.

### Algorithm
1. Check if the stack is empty (`top == NULL`).  
2. If empty, display a message.  
3. Otherwise, delete the top node and move `top` to the next node.  
4. Display the popped element.  

### Program
~~~c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *top = NULL;

void push(int value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = top;
    top = newNode;
}

void pop() {
    if (top == NULL) {
        printf("Stack is empty\n");
        return;
    }
    struct Node *temp = top;
    printf("Popped element: %d\n", top->data);
    top = top->next;
    free(temp);
}

void display() {
    struct Node *temp = top;
    printf("Stack elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    push(10);
    push(20);
    push(30);
    display();
    pop();
    display();
    return 0;
}
~~~

### Output
```
Stack elements: 30 20 10
Popped element: 30
Stack elements: 20 10
```

### Result
Thus, the program to pop an element from the given stack using linked list is verified successfully.

---

## EXP NO:28 — C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST

### Aim
To write a C program to display queue elements using linked list.

### Algorithm
1. Define a structure Node with members `data`, `next`.  
2. Use global pointers `front` and `rear`.  
3. Traverse from `front` to `rear` and display all data values.  

### Program
~~~c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL, *rear = NULL;

void enqueue(int value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

void display() {
    struct Node *temp = front;
    if (temp == NULL) {
        printf("Queue is empty\n");
        return;
    }
    printf("Queue elements are:\n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}
~~~

### Output
```
Queue elements are:
10 20 30
```

### Result
Thus, the program to display queue elements using linked list is verified successfully.

---

## EXP NO:29 — C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

### Aim
To write a C program to insert elements in queue using linked list.

### Algorithm
1. Create a new node with data.  
2. If queue is empty, set both `front` and `rear` to new node.  
3. Otherwise, link `rear->next` to new node and update `rear`.  

### Program
~~~c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL, *rear = NULL;

void enqueue(int value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
    printf("%d inserted into queue\n", value);
}

void display() {
    struct Node *temp = front;
    printf("Queue: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    enqueue(5);
    enqueue(15);
    enqueue(25);
    display();
    return 0;
}
~~~

### Output
```
5 inserted into queue
15 inserted into queue
25 inserted into queue
Queue: 5 15 25
```

### Result
Thus, the program to insert elements in queue using linked list is verified successfully.

---

## EXP NO:30 — C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST

### Aim
To write a C function to find the peek (front element) of a queue implemented using linked list.

### Algorithm
1. Check if `front` is NULL.  
2. If yes, print “Queue is empty.”  
3. Otherwise, return `front->data`.  

### Program
~~~c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node *front = NULL, *rear = NULL;

void enqueue(int value) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (rear == NULL) {
        front = rear = newNode;
    } else {
        rear->next = newNode;
        rear = newNode;
    }
}

int peek() {
    if (front == NULL) {
        printf("Queue is empty\n");
        return -1;
    }
    return front->data;
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    printf("Front element is: %d\n", peek());
    return 0;
}
~~~

### Output
```
Front element is: 10
```

### Result
Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
