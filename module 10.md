# EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
## Aim:
To write a C program to search a given element in the given linked list.

## Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory error\n");
        return NULL;
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

int search(struct Node* head, int key) {
    struct Node* current = head;
    int position = 1;
    while (current != NULL) {
        if (current->data == key) {
            return position;
        }
        current = current->next;
        position++;
    }
    return -1; 
}

void printList(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = createNode(10);
    head->next = createNode(20);
    head->next->next = createNode(30);
    head->next->next->next = createNode(40);
    head->next->next->next->next = createNode(50);

    printList(head);

    int key;
    printf("Enter the element to search: ");
    scanf("%d", &key);

    int result = search(head, key);
    if (result != -1)
        printf("Element %d found at position %d.\n", key, result);
    else
        printf("Element %d not found in the list.\n", key);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/9466b72f-89b3-4f12-9a07-dd5352222dc8)

## Result:
Thus, the program to search a given element in the given linked list is verified successfully.


# EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
## Aim:
To write a C program to insert a node in a linked list.
## Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node* next;
};

void insert(struct Node** head, char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory error\n");
        return;
    }
    newNode->data = value;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
    } else {
        struct Node* temp = *head;
        while (temp->next != NULL) {
            temp = temp->next;
        }
        temp->next = newNode;
    }
}

void printList(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%c -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL; 

    int n, i;
    char ch;
    printf("Enter the number of nodes to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter character data for node %d: ", i + 1);
        scanf(" %c", &ch); 
        insert(&head, ch);
    }

    printList(head);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/d8f7894f-9ac1-45f1-ae54-ff098b3ed8ea)

 
## Result:
Thus, the program to insert a node in a linked list is verified successfully.

# EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
## Aim:
To write a C program to traverse a doubly linked list.

## Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation error\n");
        return NULL;
    }
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List (Forward Traversal):\n");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = createNode(10);
    struct Node* second = createNode(20);
    struct Node* third = createNode(30);

    head->next = second;
    second->prev = head;
    second->next = third;
    third->prev = second;

    traverse(head);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/a0b263db-a7b3-469f-a6be-7d36f66b73fd)

## Result:
Thus, the program to traverse a doubly linked list is verified successfully. 

# EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation error\n");
        return NULL;
    }
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

void insertEnd(struct Node** head, int data) {
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

void printList(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List:\n");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL; 
    int n, i, value;

    printf("Enter the number of nodes to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter value for node %d: ", i + 1);
        scanf("%d", &value);
        insertEnd(&head, value);
    }

    printList(head);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/ea243dcd-fc6d-444a-962a-566921bbb8a1)


## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.

# EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST
## Aim:
To write a C function that deletes a given element from a linked list.

## Algorithm:
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


## Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node* next;
};

void deleteElement(struct Node** head, int key) {
    struct Node* temp = *head;
    struct Node* prev = NULL;

    if (*head == NULL) {
        printf("The list is empty.\n");
        return;
    }

    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        printf("Element %d deleted from the list.\n", key);
        return;
    }

    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }

    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted from the list.\n", key);
}

struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    if (!newNode) {
        printf("Memory allocation error.\n");
        exit(1);
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

void insertEnd(struct Node** head, int data) {
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

void printList(struct Node* head) {
    struct Node* temp = head;
    printf("Linked List: ");
    while (temp != NULL) {
        printf("%d -> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

int main() {
    struct Node* head = NULL;
    int n, i, value, key;

    printf("Enter the number of nodes: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter value for node %d: ", i + 1);
        scanf("%d", &value);
        insertEnd(&head, value);
    }

    printf("\nThe created linked list is:\n");
    printList(head);

    printf("\nEnter the element to delete: ");
    scanf("%d", &key);

    deleteElement(&head, key);

    printf("\nThe linked list after deletion is:\n");
    printList(head);

    return 0;
}

```

## Output:
![image](https://github.com/user-attachments/assets/0be4cf4f-9288-4a12-81af-00eeed5b7c63)

## Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





