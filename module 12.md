# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display stack elements using linked list.

## Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
    struct Node* next;  
};

struct Node* head = NULL;
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head; 
    head = newNode;        
}

void display() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node* p = head;  
    printf("Stack elements: \n");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;  
    }

    printf("\n");
}

int main() {
    int n, value;
    printf("Enter the number of elements to push onto the stack: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%d", &value);
        push(value);
    }
    display();
    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/04288fea-3ab1-4f2b-aed8-a7e4228751c3)

## Result:
Thus, the program to display stack elements using linked list is verified successfully. 

# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;           
    struct Node* next; 
};

struct Node* head = NULL;
void push(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = head; 
    head = newNode;       
}
void pop() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    int poppedValue = head->data;
    struct Node* temp = head;
    head = head->next;
    free(temp);
    printf("Popped element: %d\n", poppedValue);
}
void display() {
    if (head == NULL) {
        printf("Stack is empty.\n");
        return;
    }
    struct Node* p = head;  
    printf("Stack elements: \n");
    while (p != NULL) {
        printf("%d ", p->data);
        p = p->next;  
    }
    printf("\n");
}

int main() {
    int n, value, choice;
    printf("Enter the number of elements to push onto the stack: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%d", &value);
        push(value);
    }
    display();
    printf("Do you want to pop an element? (1 for Yes, 0 for No): ");
    scanf("%d", &choice);

    if (choice == 1) {
        pop();  
        display();  
    }

    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/0467bb6a-4185-4bfc-8c8c-42fd8c1db65b)

## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
    struct Node* next; 
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL; 
    if (rear == NULL) {
        front = rear = newNode;
        return;
    }
    rear->next = newNode;
    rear = newNode;
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements: \n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next; 
    }
    printf("\n");
}
int main() {
    int n, value;
    printf("Enter the number of elements to enqueue: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }
    display();
    return 0;
}

```

## Output:

![image](https://github.com/user-attachments/assets/46c3edf0-252e-438b-95a3-0309e8f684a7)


## Result:
Thus, the program to display queue elements using linked list is verified successfully.

# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

## Aim:
To write a C program to insert elements in queue using linked list

## Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;           
    struct Node* next; 
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL; 
    if (rear == NULL) {
        front = rear = newNode;
        return;
    }
    rear->next = newNode;
    rear = newNode;
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements: \n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next; 
    }
    printf("\n");
}
int main() {
    int n, value;
    printf("Enter the number of elements to enqueue: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);
    }
    display();
    int n2, value2;
    printf("Enter the number of elements to insert into the queue: ");
    scanf("%d", &n2);
    for (int i = 0; i < n2; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%d", &value2);
        enqueue(value2);  
    }
    display();
    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/aa835339-48ef-4dd3-8fee-7ec04c14b37a)


## Result:
Thus, the program to insert elements in queue using linked list is verified successfully.

# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.
## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

## Program:
```
#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;          
    struct Node* next; 
};

struct Node* front = NULL;
struct Node* rear = NULL;

void enqueue(int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;  
    if (rear == NULL) {
        front = rear = newNode;
        return;
    }
    rear->next = newNode;  
    rear = newNode;        
}
int peek() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return -1; 
    }
    return front->data;
}

void display() {
    if (front == NULL) {
        printf("Queue is empty.\n");
        return;
    }
    struct Node* temp = front;
    printf("Queue elements: \n");
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next; 
    }
    printf("\n");
}

int main() {
    int n, value;
    printf("Enter the number of elements to insert into the queue: ");
    scanf("%d", &n);
    for (int i = 0; i < n; i++) {
        printf("Enter value %d: ", i + 1);
        scanf("%d", &value);
        enqueue(value);  
    }
    display();
    int peekElement = peek();
    if (peekElement != -1) {
        printf("Peek element (front of the queue): %d\n", peekElement);
    }
    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/249271d2-bdb6-47af-8af9-d13424d684bf)


## Result:
Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


