# EX 50 C function to delete a node from a Doubly Linked List at the beginning of the list.
## DATE: 26/03/2026
## AIM:
To write a C function to delete a node from a Doubly Linked List at the beginning of the list.

## Algorithm
1.Start the program and define a doubly linked list node with data, prev, and next.

2.Create a function deleteAtBeginning() to remove the first node.

3.Check if the list is empty; if not, store the second node as new head.

4.Update the new head’s prev pointer to NULL and free the old head.

5.Return the updated head pointer.

## Program:
```
/*
C function to delete a node from a Doubly Linked List at the beginning of the list.

Developed by: Ragupathi Raj M
RegisterNumber:  212222060185
*/

#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node* prev;
    struct Node* next;
};

struct Node* deleteAtBeginning(struct Node* head)
{
    if(head == NULL)
    {
        printf("List is already empty\n");
        return NULL;
    }

    struct Node* temp = head;
    head = head->next;

    if(head != NULL)
        head->prev = NULL;

    printf("Deleted node with value %d\n", temp->data);
    free(temp);
    return head;
}

struct Node* insertAtEnd(struct Node* head, int value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if(head == NULL)
    {
        newNode->prev = NULL;
        return newNode;
    }

    struct Node* temp = head;
    while(temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;

    return head;
}

void display(struct Node* head)
{
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while(temp != NULL)
    {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main()
{
    struct Node* head = NULL;

    head = insertAtEnd(head, 10);
    head = insertAtEnd(head, 20);
    head = insertAtEnd(head, 30);

    display(head);

    head = deleteAtBeginning(head);

    display(head);

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/0b19d979-10d4-468d-ab70-05dc55cc5595)


## Result:
Thus the program was executed and the output was verified successfully.
