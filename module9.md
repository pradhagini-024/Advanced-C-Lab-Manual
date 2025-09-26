EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:
```
#include <stdio.h>
#define MAX 100

int stack[MAX];
int top = -1;

// Function to display stack elements
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements (top to bottom):\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

// Function to push an element onto the stack
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow\n");
    } else {
        top++;
        stack[top] = value;
        printf("%d pushed onto the stack.\n", value);
    }
}

// Function to pop an element from the stack
void pop() {
    if (top == -1) {
        printf("Stack Underflow\n");
    } else {
        printf("%d popped from the stack.\n", stack[top]);
        top--;
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n--- Stack Menu ---\n");
        printf("1. Push\n2. Pop\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }

    return 0;
}
```

Output:

```
--- Stack Menu ---
1. Push
2. Pop
3. Display
4. Exit
Enter your choice: 1
Enter value to push: 10
10 pushed onto the stack.

--- Stack Menu ---
Enter your choice: 1
Enter value to push: 20
20 pushed onto the stack.

--- Stack Menu ---
Enter your choice: 3
Stack elements (top to bottom):
20
10

--- Stack Menu ---
Enter your choice: 2
20 popped from the stack.

--- Stack Menu ---
Enter your choice: 3
Stack elements (top to bottom):
10

--- Stack Menu ---
Enter your choice: 4
Exiting program.
```

Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
#include <stdio.h>
#define MAX 100

// Global declarations
float stack[MAX];
int top = -1;
int size;

// Function to push an element into the stack
void push(float value) {
    if (top >= size - 1) {
        printf("Stack Overflow! Cannot push %.2f\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed into the stack.\n", value);
    }
}

int main() {
    float value;
    int n, i;

    printf("Enter the size of the stack: ");
    scanf("%d", &size);

    printf("Enter the number of elements to push: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        push(value);
    }

    return 0;
}
```
Output:

```
Enter the size of the stack: 3
Enter the number of elements to push: 4
Enter element 1: 10.5
10.50 pushed into the stack.
Enter element 2: 20.25
20.25 pushed into the stack.
Enter element 3: 30.75
30.75 pushed into the stack.
Enter element 4: 40.0
Stack Overflow! Cannot push 40.00
```

Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:

```
#include <stdio.h>
#define MAX 100

// Global variables
int queue[MAX];
int front = -1, rear = -1;

// Function to insert element into the queue
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = value;
        printf("%d enqueued into the queue.\n", value);
    }
}

// Function to display the elements of the queue
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

// Function to remove element from the queue
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow\n");
    } else {
        printf("%d dequeued from the queue.\n", queue[front]);
        front++;
    }
}

int main() {
    int choice, value;

    while (1) {
        printf("\n--- Queue Menu ---\n");
        printf("1. Enqueue\n2. Dequeue\n3. Display\n4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to enqueue: ");
                scanf("%d", &value);
                enqueue(value);
                break;
            case 2:
                dequeue();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting program.\n");
                return 0;
            default:
                printf("Invalid choice. Try again.\n");
        }
    }

    return 0;
}
```

Output:

```
--- Queue Menu ---
1. Enqueue
2. Dequeue
3. Display
4. Exit
Enter your choice: 1
Enter value to enqueue: 10
10 enqueued into the queue.

--- Queue Menu ---
Enter your choice: 1
Enter value to enqueue: 20
20 enqueued into the queue.

--- Queue Menu ---
Enter your choice: 3
Queue elements: 10 20

--- Queue Menu ---
Enter your choice: 2
10 dequeued from the queue.

--- Queue Menu ---
Enter your choice: 3
Queue elements: 20

--- Queue Menu ---
Enter your choice: 4
Exiting program.
```
Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:

```
#include <stdio.h>
#define MAX 100

// Global variables
float queue[MAX];
int front = -1, rear = -1, size;

// Function to insert element into the queue
void enqueue(float value) {
    if (rear == size - 1) {
        printf("Queue Overflow! Cannot insert %.2f\n", value);
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}

int main() {
    int n, i;
    float value;

    printf("Enter the size of the queue: ");
    scanf("%d", &size);

    printf("Enter number of elements to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%f", &value);
        enqueue(value);
    }

    return 0;
}
```

Output:

```
Enter the size of the queue: 3
Enter number of elements to insert: 4
Enter element 1: 10.5
10.50 inserted into the queue.
Enter element 2: 20.75
20.75 inserted into the queue.
Enter element 3: 30.25
30.25 inserted into the queue.
Enter element 4: 40.0
Queue Overflow! Cannot insert 40.00
```

Result:
Thus, the program to insert elements in queue using array is verified successfully.


EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:

```
#include <stdio.h>
#define MAX 100

int queue[MAX];
int front = -1, rear = -1;

// Function to delete an element from the queue
void dequeue() {
    if (front == -1) {
        printf("Queue is empty. Nothing to delete.\n");
    } else {
        printf("Deleted element: %d\n", queue[front]);
        front++;
        if (front > rear) {
            // Reset queue when empty
            front = rear = -1;
        }
    }
}

// Function to insert elements (enqueue) to test dequeue
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow\n");
    } else {
        if (front == -1) front = 0;
        rear++;
        queue[rear] = value;
        printf("%d inserted into the queue.\n", value);
    }
}

int main() {
    // Example usage:
    enqueue(10);
    enqueue(20);
    enqueue(30);

    dequeue();  // Deletes 10
    dequeue();  // Deletes 20
    dequeue();  // Deletes 30
    dequeue();  // Queue empty now

    return 0;
}
```
Output:

```
10 inserted into the queue.
20 inserted into the queue.
30 inserted into the queue.
Deleted element: 10
Deleted element: 20
Deleted element: 30
Queue is empty. Nothing to delete.
```


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
