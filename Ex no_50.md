# EX 50 C function to delete a node from a Doubly Linked List at the beginning of the list.
## DATE:08/05/2025
## AIM: To write a C function to delete a node from a Doubly Linked List at the beginning of the list.

## Algorithm
1. Start
2. Check if list is empty: If head is NULL, no deletion can be performed.
3. Store the current head node in a temporary pointer for freeing later.
4. Move head to the next node in the list.
5. Update new head’s prev to NULL if the list is not empty after deletion.
6. Free the memory of the original head node.
7. End
  

## Program:
```
#include <stdio.h>
#include <stdlib.h>

// Node definition
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to delete node at the beginning
void deleteAtBeginning(struct Node** head) {
    // Step 1: Check if the list is empty
    if (*head == NULL) {
        printf("List is already empty.\n");
        return;
    }

    // Step 2: Save the current head node
    struct Node* temp = *head;

    // Step 3: Move head to the next node
    *head = (*head)->next;

    // Step 4: If the new head is not NULL, update its prev to NULL
    if (*head != NULL)
        (*head)->prev = NULL;

    // Step 5: Free the old head node
    free(temp);
    printf("Node deleted from beginning.\n");
}

// Utility: Function to insert at beginning for testing
void insertAtBeginning(struct Node** head, int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = *head;

    if (*head != NULL)
        (*head)->prev = newNode;

    *head = newNode;
}

// Utility: Function to print the list
void printList(struct Node* head) {
    struct Node* temp = head;
    printf("List: ");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}

/*
C function to delete a node from a Doubly Linked List at the beginning of the list.

Developed by: 
RegisterNumber:  
*/
```

## Output:
List: 10 20 30 

Node deleted from beginning.

List: 20 30 

Node deleted from beginning.

List: 30 

Node deleted from beginning.

List: 

List is already empty.


## Result:
Thus the program was executed and the output was verified successfully.
