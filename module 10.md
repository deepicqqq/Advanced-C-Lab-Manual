## EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
## Aim:
To write a C program to search a given element in the given linked list.

## Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
## Program:
#include <stdio.h>
#include <stdlib.h>
struct Node {\
    int data;\
    struct Node* next;\
};
struct Node* createNode(int data) {\
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));\
    newNode->data = data;\
    newNode->next = NULL;\
    return newNode;\
}
void insertEnd(struct Node** head, int data) {\
    struct Node* newNode = createNode(data);\
    if (*head == NULL) {\
        *head = newNode;\
        return;\
    }
    struct Node* temp = *head;\
    while (temp->next != NULL) {\
        temp = temp->next;\
    }\
    temp->next = newNode;\
}

// Step 4: Function to search an element
int search(struct Node* head, int key) {
    int position = 1;
    while (head != NULL) {
        if (head->data == key)
            return position;
        head = head->next;
        position++;
    }
    return -1; // not found
}

// Step 5: Main function
int main() {
    struct Node* head = NULL;

    // Insert some sample data
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);
    insertEnd(&head, 50);

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


## Output:

![Screenshot 2025-05-05 144752](https://github.com/user-attachments/assets/a2216750-d4d6-4c19-8537-081726b0f54a)



## Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
## EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
## Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
## Program:
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the node structure
struct Node {
    char data;
    struct Node* next;
};

// Step 2: Function to create a new node
struct Node* createNode(char data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Step 3: Function to insert node at end
void insertEnd(struct Node** head, char data) {
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

// Step 4: Function to display the linked list
void displayList(struct Node* head) {
    printf("Linked List: ");
    while (head != NULL) {
        printf("%c -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Step 5: Main function
int main() {
    struct Node* head = NULL;
    char ch;
    int n, i;

    printf("Enter the number of characters to insert: ");
    scanf("%d", &n);

    for (i = 0; i < n; i++) {
        printf("Enter character %d: ", i + 1);
        scanf(" %c", &ch);  // space before %c to skip newline
        insertEnd(&head, ch);
    }

    displayList(head);

    return 0;
}


## Output:

![Screenshot 2025-05-05 144652](https://github.com/user-attachments/assets/17c86f87-a18a-427a-9983-10c73f527cce)

 
## Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
## EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
## Aim:
To write a C program to traverse a doubly linked list.

## Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
## Program:

#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the structure for a doubly linked list node
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Function to insert node at the end
void insertEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL)
        temp = temp->next;
    
    temp->next = newNode;
    newNode->prev = temp;
}

// Step 2-4: Function to traverse and display the doubly linked list
void traverse(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Step 5: Main function
int main() {
    struct Node* head = NULL;
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);
    insertEnd(&head, 50);

    traverse(head);
    return 0;
}


## Output:

![Screenshot 2025-05-05 144959](https://github.com/user-attachments/assets/f25fbf33-282d-41f0-898a-d0b43104b0a2)


## Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



## EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
## Aim:
To write a C program to insert an element in doubly linked list

## Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
## Program:

#include <stdio.h>
#include <stdlib.h>

// Step 1: Define the node structure
struct Node {
    int data;
    struct Node* prev;
    struct Node* next;
};

// Step 2: Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;
    return newNode;
}

// Step 3-5: Function to insert node at the end
void insertEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node* temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

// Function to display the doubly linked list
void displayList(struct Node* head) {
    struct Node* temp = head;
    printf("Doubly Linked List: ");
    while (temp != NULL) {
        printf("%d <-> ", temp->data);
        temp = temp->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Insert elements
    insertEnd(&head, 5);
    insertEnd(&head, 15);
    insertEnd(&head, 25);
    insertEnd(&head, 35);

    displayList(head);

    return 0;
}


## Output:
![Screenshot 2025-05-05 145056](https://github.com/user-attachments/assets/98ae5830-d6b9-45ac-94ee-f5e9032beba1)




## Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




## EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




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
#include <stdio.h>
#include <stdlib.h>

// Step 1: Define node structure
struct Node {
    int data;
    struct Node* next;
};

// Function to create a new node
struct Node* createNode(int data) {
    struct Node* newNode = (struct Node*) malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

// Function to insert at end
void insertEnd(struct Node** head, int data) {
    struct Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL)
        temp = temp->next;
    temp->next = newNode;
}

// Step 2-6: Function to delete a given element
void deleteElement(struct Node** head, int key) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }

    struct Node* temp = *head;
    struct Node* prev = NULL;

    // Step 3: If head needs to be deleted
    if (temp != NULL && temp->data == key) {
        *head = temp->next;
        free(temp);
        printf("Element %d deleted from the list.\n", key);
        return;
    }

    // Step 4: Traverse to find the node to delete
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    // Step 5: If element not found
    if (temp == NULL) {
        printf("Element %d not found in the list.\n", key);
        return;
    }

    prev->next = temp->next;
    free(temp);
    printf("Element %d deleted from the list.\n", key);
}

// Function to display list
void displayList(struct Node* head) {
    printf("Linked List: ");
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }
    printf("NULL\n");
}

// Main function
int main() {
    struct Node* head = NULL;

    // Inserting some elements
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    insertEnd(&head, 40);

    printf("Before deletion:\n");
    displayList(head);

    // Deleting an element
    int key;
    printf("Enter element to delete: ");
    scanf("%d", &key);
    deleteElement(&head, key);

    printf("After deletion:\n");
    displayList(head);

    return 0;
}



## Output:


![Screenshot 2025-05-05 145224](https://github.com/user-attachments/assets/cb460d3e-81ec-43ac-ba1e-7fd3a87b3e78)


## Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





