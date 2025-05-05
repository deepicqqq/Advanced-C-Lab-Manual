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
