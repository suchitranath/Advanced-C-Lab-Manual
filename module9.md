# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

## Aim:
To write a C program to display stack elements using an array.
## Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
## Program:
```
#include <stdio.h>
#define MAX 5 
int stack[MAX];
int top = -1;  
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements: ");
        for (int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
}
int main() {
    int choice, value, numValues;
    do {
        printf("\nStack Operations:\n");
        printf("1. Push Multiple Values\n");
        printf("2. Pop\n");
        printf("3. Display Stack\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1:
                if (top == MAX - 1) {
                    printf("Stack Overflow! Cannot push more elements.\n");
                } else {
                    printf("How many values do you want to push? ");
                    scanf("%d", &numValues);

                    if (top + numValues >= MAX) {
                        printf("Not enough space in the stack for %d values.\n", numValues);
                    } else {
                        for (int i = 0; i < numValues; i++) {
                            printf("Enter value %d to push: ", i + 1);
                            scanf("%d", &value);
                            top++;
                            stack[top] = value;
                        }
                        printf("%d values pushed onto the stack.\n", numValues);
                    }
                }
                break;

            case 2: 
                if (top == -1) {
                    printf("Stack Underflow! No element to pop.\n");
                } else {
                    printf("%d popped from the stack.\n", stack[top]);
                    top--;
                }
                break;

            case 3:
                display();
                break;

            case 4: 
                printf("Exiting the program.\n");
                break;

            default:
                printf("Invalid choice! Please try again.\n");
        }

    } while (choice != 4);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/ec1818c5-ba20-4f9c-8d71-bf4da23d5ae8)

## Result:
Thus, the program to display stack elements using an array is verified successfully.
 
# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:
```
#include <stdio.h>
#define MAX 5 
float stack[MAX];
int top = -1; 
void push(float element) {
    if (top == MAX - 1) {
        printf("Stack Overflow! Cannot push more elements.\n");
    } else {
        top++;
        stack[top] = element;
        printf("Element %.2f pushed onto the stack.\n", element);
    }
}
int main() {
    float element;
    printf("Enter a floating-point number to push onto the stack: ");
    scanf("%f", &element);
    push(element);  
    printf("Current stack contents: ");
    for (int i = 0; i <= top; i++) {
        printf("%.2f ", stack[i]);
    }
    printf("\n");
    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/4add49ff-d9d6-4bbb-adca-a451d348c5ca)

## Result:
Thus, the program to push the given element in to a stack using array is verified successfully

# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:
```
#include <stdio.h>
#define SIZE 5 
int queue[SIZE];
int front = -1, rear = -1;
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
void enqueue(int value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert more elements.\n");
    } else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%d enqueued to the queue.\n", value);
    }
}
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow! No element to dequeue.\n");
    } else {
        printf("%d dequeued from the queue.\n", queue[front]);
        front++;
    }
}
int main() {
    int choice, value;

    do {
        printf("\nQueue Operations:\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Display Queue\n");
        printf("4. Exit\n");
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
                break;
            default:
                printf("Invalid choice. Try again.\n");
        }
    } while (choice != 4);

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/56158af7-c9e6-43e6-a424-715b5bdc1308)


## Result:
Thus, the program to display queue elements using array is verified successfully.

# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:
```
#include <stdio.h>
#define SIZE 5  
float queue[SIZE];
int front = -1, rear = -1;
void enqueue(float value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert more elements.\n");
    } else {
        if (front == -1)  
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}
int main() {
    float value;
    char choice;

    do {
        printf("Enter a float value to insert into the queue: ");
        scanf("%f", &value);
        enqueue(value);

        printf("Do you want to insert another element? (y/n): ");
        scanf(" %c", &choice); 

    } while (choice == 'y' || choice == 'Y');
    if (front == -1) {
        printf("Queue is empty.\n");
    } else {
        printf("Current Queue: ");
        for (int i = front; i <= rear; i++) {
            printf("%.2f ", queue[i]);
        }
        printf("\n");
    }

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/8c03058e-6176-4707-ba2a-8f519c8e325d)

## Result:
Thus, the program to insert elements in queue using array is verified successfully.

# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY
## Aim:
To create a function in C that deletes an element from a queue implemented using an array.

## Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.

## Program:
```
#include <stdio.h>
#define SIZE 5
float queue[SIZE];
int front = -1, rear = -1;
void enqueue(float value) {
    if (rear == SIZE - 1) {
        printf("Queue Overflow! Cannot insert more elements.\n");
    } else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}
void dequeue() {
    if (front == -1) {
        printf("Queue is empty! Nothing to delete.\n");
        return;
    }
    printf("Deleted element: %.2f\n", queue[front]);
    front++;
    if (front > rear) {
        front = rear = -1;
        printf("Queue is now empty.\n");
    }
}
void displayQueue() {
    if (front == -1) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements: ");
        for (int i = front; i <= rear; i++) {
            printf("%.2f ", queue[i]);
        }
        printf("\n");
    }
}
int main() {
    enqueue(10.5);
    enqueue(20.3);
    enqueue(30.2);
    displayQueue();

    dequeue();
    displayQueue();

    dequeue();
    dequeue();
    dequeue();  // Attempt to delete from empty queue

    return 0;
}

```
## Output:
![image](https://github.com/user-attachments/assets/0804c93f-1f7c-4df0-8672-ab543bc859d6)

## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
