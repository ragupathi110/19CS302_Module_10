# EX 47 C function to insert a node in a linked list.
## DATE: 26/03/2026
## AIM:
To write a C function to insert a node in a linked list.

## Algorithm
1.Define a Node structure with data and next.

2.Create a function insertAtBeginning() that allocates memory for a new node.

3.Set the new node’s data and point its next to the current head.

4.Update the head to the new node.

5.Return the updated head.

## Program:
```
/*
C function to insert a node in a linked list.

Developed by: Ragupathi Raj M
RegisterNumber:  212222060185
*/
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node* next;
};

struct Node* insert(struct Node* head, int value)
{
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;

    if(head == NULL)
    {
        head = newNode;
    }
    else
    {
        struct Node* temp = head;
        while(temp->next != NULL)
        {
            temp = temp->next;
        }
        temp->next = newNode;
    }
    return head;
}

void display(struct Node* head)
{
    struct Node* current = head;
    while(current != NULL)
    {
        printf("%d -> ", current->data);
        current = current->next;
    }
    printf("NULL\n");
}

int main()
{
    struct Node* head = NULL;

    head = insert(head, 100);
    head = insert(head, 200);
    head = insert(head, 300);

    display(head);

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/c0ef9202-c306-4173-aa94-e681095de07f)

## Result:
Thus the program was executed and the output was verified successfully.
