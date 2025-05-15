## EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

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

#include <stdio.h>
#define MAX 100

// Declare Global Variables
int stack[MAX];
int top = -1;

// Function to display the stack
void display() {
    if (top == -1) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack elements are:\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

// Function to push an element onto the stack
void push(int value) {
    if (top == MAX - 1) {
        printf("Stack Overflow.\n");
    } else {
        top++;
        stack[top] = value;
    }
}

// Function to pop an element from the stack
void pop() {
    if (top == -1) {
        printf("Stack Underflow.\n");
    } else {
        printf("Popped element is: %d\n", stack[top]);
        top--;
    }
}

int main() {
    int choice, value;

    do {
        printf("\n--- Stack Operations ---\n");
        printf("1. Push\n");
        printf("2. Pop\n");
        printf("3. Display\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter the value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("Exiting program.\n");
                break;
            default:
                printf("Invalid choice. Please enter 1-4.\n");
        }
    } while(choice != 4);

    return 0;
}


## Output:

![Screenshot 2025-04-27 161148](https://github.com/user-attachments/assets/182bdbc3-954e-4fe8-b596-043c643b789e)




## Result:
Thus, the program to display stack elements using an array is verified successfully.
 

## EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
## Aim:
To create a C program to push the given element in to a stack using array.
## Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
## Program:

#include <stdio.h>
#define MAX 100  // Define maximum size of stack

// Declare global variables
float stack[MAX];
int top = -1;

// Function to push an element onto the stack
void push(float value) {
    if (top == MAX - 1) {
        printf("Stack Overflow. Cannot push %.2f onto the stack.\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("%.2f pushed onto the stack.\n", value);
    }
}

int main() {
    int n, i;
    float value;

    printf("Enter the number of elements you want to push: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter value to push: ");
        scanf("%f", &value);
        push(value);
    }

    printf("\nElements in the stack:\n");
    for (i = top; i >= 0; i--) {
        printf("%.2f\n", stack[i]);
    }

    return 0;
}


## Output:


![Screenshot 2025-04-27 161308](https://github.com/user-attachments/assets/44b96801-c7f7-4bbb-b5f9-b24c82e5debb)




## Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
## EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
## Aim:
To write a C program to display queue elements using array

## Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
## Program:
#include <stdio.h>
#define MAX 100  // Maximum size of the queue

// Declare global variables
int queue[MAX];
int front = -1, rear = -1;

// Function to display the queue
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

// Function to enqueue (insert) an element into the queue
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow. Cannot insert %d.\n", value);
    } else {
        if (front == -1) {
            front = 0; // Set front to 0 when first element is inserted
        }
        rear++;
        queue[rear] = value;
        printf("%d inserted into the queue.\n", value);
    }
}

// Function to dequeue (remove) an element from the queue
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue Underflow.\n");
    } else {
        printf("%d removed from the queue.\n", queue[front]);
        front++;
    }
}

int main() {
    int choice, value;

    do {
        printf("\n--- Queue Operations ---\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Display Queue\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to insert: ");
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
                printf("Invalid choice. Please enter between 1-4.\n");
        }
    } while (choice != 4);

    return 0;
}


## Output:


![Screenshot 2025-04-27 161451](https://github.com/user-attachments/assets/070f0cef-7c65-493c-8241-c0c83b0ba633)


## Result:
Thus, the program to display queue elements using array is verified successfully.


 
## EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
## Aim:
To write a C program to insert elements in queue using array.

## Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

## Program:

#include <stdio.h>
#define MAX 100  // Maximum size of the queue

// Global variables
float queue[MAX];
int front = -1, rear = -1;

// Function to insert (enqueue) an element into the queue
void enqueue(float value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow. Cannot insert %.2f.\n", value);
    } else {
        if (front == -1) {
            front = 0; // Set front to 0 when first element is inserted
        }
        rear++;
        queue[rear] = value;
        printf("%.2f inserted into the queue.\n", value);
    }
}

int main() {
    int n, i;
    float value;

    printf("Enter the number of elements you want to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter value to insert: ");
        scanf("%f", &value);
        enqueue(value);
    }

    // Display the queue
    printf("\nElements in the queue:\n");
    for (i = front; i <= rear; i++) {
        printf("%.2f ", queue[i]);
    }
    printf("\n");

    return 0;
}


## Output:

![Screenshot 2025-04-27 161612](https://github.com/user-attachments/assets/c298dbe1-1fb0-4057-bf13-dfd8a58f49c2)


## Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
## EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

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

#include <stdio.h>
#define MAX 100  // Maximum size of the queue

// Global variables
int queue[MAX];
int front = -1, rear = -1;

// Function to delete (dequeue) an element from the queue
void dequeue() {
    if (front == -1 || front > rear) {
        printf("Queue is empty. Cannot delete any element.\n");
    } else {
        printf("Deleted element: %d\n", queue[front]);
        front++;  // Move front to the next element
        // Check if the queue becomes empty
        if (front > rear) {
            front = rear = -1;
        }
    }
}

// Function to insert elements into the queue for testing
void enqueue(int value) {
    if (rear == MAX - 1) {
        printf("Queue Overflow. Cannot insert %d.\n", value);
    } else {
        if (front == -1)
            front = 0;
        rear++;
        queue[rear] = value;
        printf("%d inserted into the queue.\n", value);
    }
}

// Function to display the queue elements
void display() {
    if (front == -1 || front > rear) {
        printf("Queue is empty.\n");
    } else {
        printf("Queue elements are:\n");
        for (int i = front; i <= rear; i++) {
            printf("%d ", queue[i]);
        }
        printf("\n");
    }
}

int main() {
    int choice, value;

    do {
        printf("\n--- Queue Operations ---\n");
        printf("1. Enqueue\n");
        printf("2. Dequeue\n");
        printf("3. Display Queue\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch(choice) {
            case 1:
                printf("Enter value to insert: ");
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
                printf("Invalid choice. Please enter between 1-4.\n");
        }
    } while (choice != 4);

    return 0;
}


## Output:

![Screenshot 2025-04-27 161755](https://github.com/user-attachments/assets/410eeb2c-3d04-4bff-a5c9-0c24c3c9546a)


## Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
