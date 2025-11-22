## EXP NO: 11 — C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY

### Aim:

To write a C program to display stack elements using an array.

### Algorithm:

Start

Include necessary header files.

Declare global variables for stack, top, and size.

Define the display function to print the stack elements.

In the main function:

– Initialize stack and top.

– Perform stack operations (push, pop, etc.).

– Call the display function to show stack contents.

End.

### Program:

~~~c
#include <stdio.h>
#define SIZE 5

int stack[SIZE];
int top = -1;

void push(int value) {
    if (top == SIZE - 1)
        printf("Stack Overflow\n");
    else
        stack[++top] = value;
}

void display() {
    if (top == -1)
        printf("Stack is empty\n");
    else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--)
            printf("%d\n", stack[i]);
    }
}

int main() {
    push(10);
    push(20);
    push(30);
    display();
    return 0;
}
~~~

### Output:

~~~
Stack elements are:
30
20
10
~~~
### Result:

Thus, the program to display stack elements using an array is verified successfully.

## EXP NO: 12 — C PROGRAM TO PUSH THE GIVEN ELEMENT INTO A STACK USING ARRAY

### Aim:

To create a C program to push the given element into a stack using an array.

### Algorithm:

Start

Declare global variables for stack, size, and top.

Define a push() function to insert an element into the stack.

Check for overflow before inserting.

In main(), call the push() function with user input.

Display the stack after pushing elements.

End.

### Program:

~~~c
#include <stdio.h>
#define SIZE 5

float stack[SIZE];
int top = -1;

void push(float value) {
    if (top == SIZE - 1)
        printf("Stack Overflow\n");
    else {
        top++;
        stack[top] = value;
        printf("Inserted %.2f into stack\n", value);
    }
}

int main() {
    push(5.5);
    push(10.2);
    push(15.8);
    return 0;
}
~~~

### Output:

~~~
Inserted 5.50 into stack
Inserted 10.20 into stack
Inserted 15.80 into stack
~~~

### Result:

Thus, the program to push the given element into a stack using an array is verified successfully.

## EXP NO: 13 — C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY

### Aim:

To write a C program to display queue elements using an array.

### Algorithm:

Start

Declare global variables for queue, front, and rear.

Define a display() function to print queue elements.

In main(), initialize queue and perform operations.

Call display() to show queue contents.

End.

### Program:

~~~c
#include <stdio.h>
#define SIZE 5

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        queue[++rear] = value;
    }
}

void display() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    return 0;
}
~~~

### Output:

~~~
Queue elements are:
10 20 30
~~~

### Result:

Thus, the program to display queue elements using an array is verified successfully.

## EXP NO: 14 — C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY

### Aim:

To write a C program to insert elements in queue using an array.

### Algorithm:

Start

Declare global variables for queue, size, front, and rear.

Define the enqueue() function to insert an element into the queue.

Check for overflow before inserting.

In main(), call the enqueue() function with sample values.

Display the inserted queue elements.

End.

### Program:

~~~c
#include <stdio.h>
#define SIZE 5

float queue[SIZE];
int front = -1, rear = -1;

void enqueue(float value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        queue[++rear] = value;
        printf("Inserted %.2f into queue\n", value);
    }
}

int main() {
    enqueue(1.5);
    enqueue(2.5);
    enqueue(3.5);
    return 0;
}
~~~

### Output:

~~~
Inserted 1.50 into queue
Inserted 2.50 into queue
Inserted 3.50 into queue
~~~

### Result:

Thus, the program to insert elements in queue using array is verified successfully.

## EXP NO: 15 — C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

### Aim:

To create a function in C that deletes an element from a queue implemented using an array.

### Algorithm:

Start

Check if the queue is empty:

– If front == -1, print “Queue is empty”.

If not empty:

– Delete the element at the front.

– Increment front to point to the next element.

If after deletion front > rear, reset both to -1.

End.

### Program:

~~~c
#include <stdio.h>
#define SIZE 5

int queue[SIZE];
int front = -1, rear = -1;

void enqueue(int value) {
    if (rear == SIZE - 1)
        printf("Queue Overflow\n");
    else {
        if (front == -1)
            front = 0;
        queue[++rear] = value;
    }
}

void dequeue() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("Deleted element: %d\n", queue[front]);
        front++;
        if (front > rear)
            front = rear = -1;
    }
}

void display() {
    if (front == -1)
        printf("Queue is empty\n");
    else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++)
            printf("%d ", queue[i]);
        printf("\n");
    }
}

int main() {
    enqueue(10);
    enqueue(20);
    enqueue(30);
    display();
    dequeue();
    display();
    return 0;
}
~~~

### Output:

~~~
Queue elements are:
10 20 30
Deleted element: 10
Queue elements are:
20 30
~~~

### Result:

Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
