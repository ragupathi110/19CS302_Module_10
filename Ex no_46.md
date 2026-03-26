# EX 46 C function to traverse the linked list and display it in the following format.
## DATE: 26/03/2026
## AIM:
To write a C function to traverse the linked list and display it in the following format.

## Algorithm
  
1. Start. 
2. Define a variables. 
3. Write a functions to traverse the linked list and display it in the following format. 
4. Read the value using scanf. 
5. Ask the user to make an input. 
6. Print out the answer. 
7. End.
## Program:
```
/*
C function to traverse the linked list and display it in the following format.

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
    struct Node* head = (struct Node*)malloc(sizeof(struct Node));
    struct Node* second = (struct Node*)malloc(sizeof(struct Node));
    struct Node* third = (struct Node*)malloc(sizeof(struct Node));

    head->data = 10;
    head->next = second;

    second->data = 20;
    second->next = third;

    third->data = 30;
    third->next = NULL;

    display(head);

    return 0;
}
```
## Output:
![image](https://github.com/user-attachments/assets/d089e533-d8cf-4f6e-8c00-0c2ea766872e)

## Result:
Thus the program was executed and the output was verified successfully.
