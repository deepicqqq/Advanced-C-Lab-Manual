## NAME: DEEPIKA P
## REGISTER NO: 212223240024

## EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
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
#include <stdio.h>
#include <stdlib.h>\
struct Node {\
    int data;\
    struct Node* next;\
};\
struct Node* head = NULL;\
void push(int value) {\
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));\
    newNode->data = value;\
    newNode->next = head;\
    head = newNode;\
}\
void display() {\
    struct Node* p = head;\
    if (p == NULL) {\
        printf("Stack is empty.\n");\
        return;\
    }\
    printf("Stack elements are:\n");\
    while (p != NULL) {\
        printf("%d\n", p->data);\
        p = p->next;\
    }\
}\
int main() {\
    push(10);\
    push(20);\
    push(30);\
    display();

    return 0;
}


## Output:
![image](https://github.com/user-attachments/assets/f4ca3f1d-5491-4011-a66e-bcdb65ff4476)


## Result:
Thus, the program to display stack elements using linked list is verified successfully. 



## EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
## Aim:
To write a C program to pop an element from the given stack using liked list.

## Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
## Program:
#include <stdio.h>
#include <stdlib.h>
struct Node {\
    int data;\
    struct Node* next;\
};\
struct Node* head = NULL;\
void push(int value) {\
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));\
    newNode->data = value;\
    newNode->next = head;\
    head = newNode;\
}\
void pop() {\
    if (head == NULL) {\
        printf("Stack is empty.\n");\
        return;\
    }\
    struct Node* temp = head;\
    head = head->next;\
    free(temp);
    
    printf("Element popped successfully.\n");
}
void display() {\
    struct Node* p = head;\
    if (p == NULL) {\
        printf("Stack is empty.\n");\
        return;\
    }\
    printf("Stack elements are:\n");\
    while (p != NULL) {\
        printf("%d\n", p->data);\
        p = p->next;\
    }\
}
int main() {\
    push(10);\
    push(20);\
    push(30);
    
    // Displaying the stack
    display();
    
    // Popping an element
    pop();
    
    // Displaying the stack after popping
    display();
    
    return 0;
}


## Output:

![Screenshot 2025-05-14 215941](https://github.com/user-attachments/assets/4ea2db9a-e3af-44c2-9453-7789f10de130)




## Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
## EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
## Aim:
To write a C program to display queue elements using linked list.
## Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
## Program:

#include <stdio.h>
#include <stdlib.h>\
struct Node {\
    int data;\
    struct Node* next;\
};\
struct Queue {\
    struct Node* front;\
    struct Node* rear;\
};\
void initializeQueue(struct Queue* q) {\
    q->front = q->rear = NULL;\
}\
void enqueue(struct Queue* q, int value) {\
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));\
    newNode->data = value;\
    newNode->next = NULL;\
    if (q->rear == NULL) {\
        q->front = q->rear = newNode;\
        return;\
    }\
    q->rear->next = newNode;\
    q->rear = newNode;\
}

void display(struct Queue* q) {\
    if (q->front == NULL) {\
        printf("Queue is empty.\n");\
        return;\
    }

    printf("Queue elements are:\n");
    struct Node* temp = q->front;
    while (temp != NULL) {
        printf("%d\n", temp->data);
        temp = temp->next;
    }
}

int main() {
    struct Queue q;\
    initializeQueue(&q);

    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    display(&q);
    
    return 0;
}


## Output:

![Screenshot 2025-05-14 220432](https://github.com/user-attachments/assets/93dff0a1-710b-4ce4-8510-5e853603a347)


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

#include <stdio.h>
#include <stdlib.h>\
struct Node {\
    int data;\
    struct Node* next;\
};

struct Queue {\
    struct Node* front;\
    struct Node* rear;\
};

void initializeQueue(struct Queue* q) {\
    q->front = q->rear = NULL;\
}

void enqueue(struct Queue* q, int value) {\
    // Step 1: Allocate memory for new node\
    struct Node* p = (struct Node*)malloc(sizeof(struct Node));\
    p->data = value;\
    p->next = NULL;

    // Step 2 & 3: Check if queue is empty
    if (q->rear == NULL) {
        q->front = q->rear = p;
    } else {
        // Step 4 & 5
        q->rear->next = p;
        q->rear = p;
    }
    printf("Inserted %d into the queue.\n", value);
}\
void display(struct Queue* q) {\
    struct Node* temp = q->front;\
    if (temp == NULL) {
        printf("Queue is empty.\n");\
        return;\
    }
    printf("Queue elements are:\n");\
    while (temp != NULL) {\
        printf("%d\n", temp->data);\
        temp = temp->next;\
    }\
}

int main() {
    struct Queue q;
    initializeQueue(&q);

    // Inserting elements into the queue
    enqueue(&q, 10);
    enqueue(&q, 20);
    enqueue(&q, 30);

    // Displaying the queue
    display(&q);

    return 0;
}


## Output:

![image](https://github.com/user-attachments/assets/970bbcaa-2fcb-4f9e-a7ff-66d48da257e1)


## Result:
Thus, the program to insert elements inqueue using linked list is verified successfully.

## EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.

## Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

## Algorithm:

Check if the queue is empty: o If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
Access the front element: o If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).
## Program:
#include <stdio.h>
#include <stdlib.h>\

struct Node {\
    int data;\
    struct Node* next;\
};

struct Queue {\
    struct Node* front;\
    struct Node* rear;\
};

void initializeQueue(struct Queue* q) {\
    q->front = q->rear = NULL;\
}

void enqueue(struct Queue* q, int value) {\
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));\
    newNode->data = value;\
    newNode->next = NULL;

    if (q->rear == NULL) {
        q->front = q->rear = newNode;
    } else {
        q->rear->next = newNode;
        q->rear = newNode;
    }
}

void peek(struct Queue* q) {\
    if (q->front == NULL) {\
        printf("Queue is empty. Nothing to peek.\n");\
    } else {\
        printf("Peek (front element) of the queue is: %d\n", q->front->data)\
    }\
}


int main() {\
    struct Queue q;\
    initializeQueue(&q);\
    enqueue(&q, 100);\
    enqueue(&q, 200);\
    enqueue(&q, 300);

    // Peeking the front element
    peek(&q);

    return 0;
}



## Output:

![image](https://github.com/user-attachments/assets/fe7db271-c4df-49cc-8514-28d94a2685dc)


## Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.

