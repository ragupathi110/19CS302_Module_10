# EX 48 C functions to perform all basic operations in Doubly Linked List.
## DATE: 26/03/2026
## AIM:
To write a C functions to perform all basic operations in Doubly Linked List.

## Algorithm
   
1.Define a doubly linked list node with data, prev, and next pointers.

2.Create functions to insert at beginning, insert at end, delete a node, and display the list.

3.In insert functions, update both prev and next links correctly.

4.In delete, find the target node, then re-link neighbors before freeing it.

5.Use display() to print the list from head to tail.

## Program:
```
/*
C functions to perform all basic operations in Doubly Linked List.

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

struct Node* insertAtBeginning(struct Node* head, int value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->prev = NULL;
    newNode->next = head;

    if(head != NULL)
        head->prev = newNode;

    return newNode;
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

struct Node* deleteNode(struct Node* head, int value)
{
    struct Node* temp = head;

    while(temp != NULL && temp->data != value)
        temp = temp->next;

    if(temp == NULL)
    {
        printf("Node not found\n");
        return head;
    }

    if(temp->prev != NULL)
        temp->prev->next = temp->next;
    else
        head = temp->next;

    if(temp->next != NULL)
        temp->next->prev = temp->prev;

    free(temp);
    printf("Node with value %d deleted\n", value);
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
    head = insertAtBeginning(head, 5);
    head = insertAtEnd(head, 30);

    display(head);

    head = deleteNode(head, 20);
    display(head);

    return 0;
}


```

## Output:

![image](https://github.com/user-attachments/assets/b6263299-aa26-4b5e-a006-4ae2f6ab77e2)


## Result:
Thus the program was executed and the output was verified successfully.
