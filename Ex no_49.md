# EX 49 C function to search an element in the doubly linked list.
## DATE: 26/03/2026
## AIM:
To write a C function to search an element in the doubly linked list.

## Algorithm
   
1.Start the program and define a doubly linked list node with data, prev, and next.

2.Create a function search() that takes the head and target value as arguments.

3.Traverse the list using a temporary pointer from head to tail.

4.Compare each node's data with the target value.

5.If found, print its position; otherwise, indicate that it was not found.

## Program:
```
/*
C function to search an element in the doubly linked list.

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

void search(struct Node* head, int value)
{
    struct Node* temp = head;
    int position = 1;

    while(temp != NULL)
    {
        if(temp->data == value)
        {
            printf("Element %d found at position %d\n", value, position);
            return;
        }
        temp = temp->next;
        position++;
    }
    printf("Element %d not found in the list\n", value);
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

int main()
{
    struct Node* head = NULL;

    head = insertAtEnd(head, 10);
    head = insertAtEnd(head, 20);
    head = insertAtEnd(head, 30);

    search(head, 20);
    search(head, 40);

    return 0;
}


```

## Output:

![image](https://github.com/user-attachments/assets/4ee03749-6446-44e4-b756-6397496d1f61)


## Result:
Thus the program was executed and the output was verified successfully.
