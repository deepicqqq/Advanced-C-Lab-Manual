# REGISTER NO: 212223240024
# NAME: DEEPIKA P
# EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

# Aim:
To write a C program to display stack elements using an array.
# Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
# Program:
#include <stdio.h>
int stack[MAX];\
int top = -1;\
void display() {\
    if (top == -1) {\
        printf("Stack is empty.\n");\
    } else {\
        printf("Stack elements are:\n");\
        for (int i = top; i >= 0; i--) {\
            printf("%d\n", stack[i]);\
        }\
    }\
}

void push(int value) {\
    if (top == MAX - 1) {\
        printf("Stack Overflow.\n");\
    } else {\
        top++;\
        stack[top] = value;\
    }\
}

void pop() {\
    if (top == -1) {\
        printf("Stack Underflow.\n");\
    } else {\
        printf("Popped element is: %d\n", stack[top]);\
        top--;\
    }\
}

int main() {\
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


# Output:


![Screenshot 2025-04-27 161148](https://github.com/user-attachments/assets/7608ee3f-cbee-451c-a083-6a909005d6d3)


# Result:
Thus, the program to display stack elements using an array is verified successfully.
 

# EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
# Aim:
To create a C program to push the given element in to a stack using array.
# Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
# Program:

#include <stdio.h> 

float stack[MAX];\
int top = -1;

void push(float value) {\
    if (top == MAX - 1) {\
        printf("Stack Overflow. Cannot push %.2f onto the stack.\n", value);\
    } else {\
        top++;\
        stack[top] = value;\
        printf("%.2f pushed onto the stack.\n", value);\
    }\
}

int main() {
    int n, i;\
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


# Output:

![Screenshot 2025-04-27 161308](https://github.com/user-attachments/assets/1c4c9670-ca57-47e5-9fbb-57448f369d70)


# Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
# EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
# Aim:
To write a C program to display queue elements using array

# Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
# Program:

#include <stdio.h>
#define MAX 100 

int queue[MAX];
int front = -1, rear = -1;

void display() {\
    if (front == -1 || front > rear) {\
        printf("Queue is empty.\n");\
    } else {\
        printf("Queue elements are:\n");\
        for (int i = front; i <= rear; i++) {\
            printf("%d ", queue[i]);\
        }\
        printf("\n");\
    }\
}

void enqueue(int value) {\
    if (rear == MAX - 1) {\
        printf("Queue Overflow. Cannot insert %d.\n", value);\
    } else {\
        if (front == -1) {\
            front = 0; \
        }\
        rear++;\
        queue[rear] = value;\
        printf("%d inserted into the queue.\n", value);\
    }\
}

void dequeue() {\
    if (front == -1 || front > rear) {\
        printf("Queue Underflow.\n");\
    } else {\
        printf("%d removed from the queue.\n", queue[front]);\
        front++;\
    }\
}

int main() {\
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


# Output:

![Screenshot 2025-04-27 161451](https://github.com/user-attachments/assets/64ce4b88-99fe-4d8e-8633-6413f2d352d4)

# Result:
Thus, the program to display queue elements using array is verified successfully.


 
# EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
# Aim:
To write a C program to insert elements in queue using array.

# Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

# Program:

#include <stdio.h>
#define MAX 100  

float queue[MAX];\
int front = -1, rear = -1;

void enqueue(float value) {\
    if (rear == MAX - 1) {\
        printf("Queue Overflow. Cannot insert %.2f.\n", value);\
    } else {\
        if (front == -1) {\
            front = 0;\
        }\
        rear++;\
        queue[rear] = value;\
        printf("%.2f inserted into the queue.\n", value);\
    }\
}

int main() {\
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


# Output:

![Screenshot 2025-04-27 161612](https://github.com/user-attachments/assets/cc665aca-6b6b-47e1-a8d5-43b6d5300a87)


# Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
# EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY

# Aim:

To create a function in C that deletes an element from a queue implemented using an array.

# Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



# Program:

#include <stdio.h>
#define MAX 100  

int queue[MAX];\
int front = -1, rear = -1;

void dequeue() {\
    if (front == -1 || front > rear) {\
        printf("Queue is empty. Cannot delete any element.\n");\
    } else {\
        printf("Deleted element: %d\n", queue[front]);\
        front++;  // Move front to the next element\
        // Check if the queue becomes empty\
        if (front > rear) {\
            front = rear = -1;\
        }\
    }\
}

void enqueue(int value) {\
    if (rear == MAX - 1) {\
        printf("Queue Overflow. Cannot insert %d.\n", value);\
    } else {\
        if (front == -1)\
            front = 0;\
        rear++;\
        queue[rear] = value;\
        printf("%d inserted into the queue.\n", value);\
    }\
}

void display() {\
    if (front == -1 || front > rear) {\
        printf("Queue is empty.\n");\
    } else {\
        printf("Queue elements are:\n");\
        for (int i = front; i <= rear; i++) {\
            printf("%d ", queue[i]);\
        }\
        printf("\n");\
    }\
}

int main() {\
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


# Output:

![Screenshot 2025-04-27 161805](https://github.com/user-attachments/assets/bdb145b8-fa8e-4c0b-881a-f2b37048f005)


# Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
