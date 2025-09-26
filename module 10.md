EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Define node structure
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to search for an element in the linked list
int search(struct Node* head, char key) {
    struct Node* current = head;
    int position = 1;
    while (current != NULL) {
        if (current->data == key) {
            return position;  // Element found at this position
        }
        current = current->next;
        position++;
    }
    return -1;  // Element not found
}

int main() {
    // Creating linked list manually: A -> B -> C -> D -> NULL
    struct Node* head = createNode('A');
    head->next = createNode('B');
    head->next->next = createNode('C');
    head->next->next->next = createNode('D');

    char key;
    printf("Enter the character to search: ");
    scanf(" %c", &key);

    int result = search(head, key);

    if (result != -1)
        printf("Element '%c' found at position %d\n", key, result);
    else
        printf("Element '%c' not found in the linked list\n", key);

    // Free allocated memory (optional here but good practice)
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(tem
```

Output:

```
Enter the character to search: C
Element 'C' found at position 3
```


Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Define node structure
struct Node {
    char data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert node at the end of the linked list
void insertAtEnd(struct Node** head, char data) {
    struct Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
}

// Function to display the linked list
void display(struct Node* head) {
    if (head == NULL) {
        printf("Linked list is empty.\n");
        return;
    }
    printf("Linked list elements: ");
    while (head != NULL) {
        printf("%c -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    char data;
    int n, i;

    printf("How many nodes do you want to insert? ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter data for node %d: ", i + 1);
        scanf(" %c", &data);
        insertAtEnd(&head, data);
    }

    display(head);

    // Free allocated memory (good practice)
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```
Output:

```
 How many nodes do you want to insert? 3
Enter data for node 1: A
Enter data for node 2: B
Enter data for node 3: C
Linked list elements: A -> B -> C -> NULL
```

Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Define node structure for doubly linked list
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert node at the end of doubly linked list
void insertAtEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
}

// Function to traverse and print the doubly linked list
void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly linked list elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;
    int n, data, i;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter data for node %d: ", i + 1);
        scanf("%d", &data);
        insertAtEnd(&head, data);
    }

    traverse(head);

    // Free allocated memory (good practice)
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```
Output:

```
Enter number of nodes: 4
Enter data for node 1: 10
Enter data for node 2: 20
Enter data for node 3: 30
Enter data for node 4: 40
Doubly linked list elements: 10 20 30 40 
```

Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

```
#include <stdio.h>
#include <stdlib.h>

// Node structure for doubly linked list
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert node at the end of doubly linked list
void insertAtEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);

    if (*head == NULL) {
        *head = newNode;  // If list empty, new node is head
        return;
    }

    struct Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;  // Traverse to last node
    }
    temp->next = newNode;   // Link last node to new node
    newNode->prev = temp;   // Link new node back to last node
}

// Function to display doubly linked list
void display(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly linked list elements: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

int main() {
    struct Node* head = NULL;
    int n, data, i;

    printf("Enter the number of elements to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &data);
        insertAtEnd(&head, data);
    }

    display(head);

    // Free memory (good practice)
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```
Output:

```
Enter the number of elements to insert: 3
Enter element 1: 5
Enter element 2: 10
Enter element 3: 15
Doubly linked list elements: 5 10 15 
```

Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST

Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

```
#include <stdio.h>
#include <stdlib.h>

// Node structure for singly linked list
struct Node {
    int data;
    struct Node* next;
};

// Function to insert node at the end (for testing)
void insertAtEnd(struct Node** head, int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node* temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
}

// Function to delete a node with given data
void deleteElement(struct Node** head, int key) {
    if (*head == NULL) {
        printf("Linked list is empty. Nothing to delete.\n");
        return;
    }

    struct Node* temp = *head;
    struct Node* prev = NULL;

    // If head node holds the key to be deleted
    if (temp != NULL && temp->data == key) {
        *head = temp->next; // Change head
        free(temp);         // Free old head
        printf("Element %d deleted from the list.\n", key);
        return;
    }

    // Search for the key to be deleted
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // If element not found
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }

    // Unlink the node and free memory
    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted from the list.\n", key);
}

// Function to display the linked list
void displayList(struct Node* head) {
    if (head == NULL) {
        printf("Linked list is empty.\n");
        return;
    }
    printf("Linked list elements: ");
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    int n, i, val, key;

    printf("Enter number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter element %d: ", i + 1);
        scanf("%d", &val);
        insertAtEnd(&head, val);
    }

    displayList(head);

    printf("Enter element to delete: ");
    scanf("%d", &key);

    deleteElement(&head, key);

    displayList(head);

    // Free the list (optional cleanup)
    struct Node* temp;
    while (head != NULL) {
        temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```
Output:

```
Enter number of nodes: 4
Enter element 1: 10
Enter element 2: 20
Enter element 3: 30
Enter element 4: 40
Linked list elements: 10 -> 20 -> 30 -> 40 -> NULL
Enter element to delete: 20
Element 20 deleted from the list.
Linked list elements: 10 -> 30 -> 40 -> NULL
```

Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





