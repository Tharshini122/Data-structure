#include <stdio.h>
#include <stdlib.h>

// Define the structure for a node
typedef struct Node {
    int data;
    struct Node* next;
} Node;

Node*createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = newNode; // For a circular list
    return newNode;
}

// Insert node at the front
void insertFront(Node** head, int data) {
    Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
    } else {
        Node* temp = *head;
        while (temp->next != *head) {
            temp = temp->next;
        }
        newNode->next = *head;
        temp->next = newNode;
        *head = newNode;
    }
}

// Insert node at the end
void insertEnd(Node** head, int data) {
    Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
    } else {
        Node* temp = *head;
        while (temp->next != *head) {
            temp = temp->next;
        }
        temp->next = newNode;
        newNode->next = *head;
    }
}

// Insert node at a specific position
void insertMiddle(Node** head, int data, int position) {
    Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        newNode->next = *head;
    } else {
        Node* temp = *head;
        int count = 0;
        while (count < position - 1 && temp->next != *head) {
            temp = temp->next;
            count++;
        }
        newNode->next = temp->next;
        temp->next = newNode;
    }
}

// Delete node from the front
void deleteFront(Node** head) {
    if (*head == NULL) {
        return;
    }
    Node* temp = *head;
    if (temp->next == *head) {
        free(temp);
        *head = NULL;
    } else {
        Node* last = *head;
        while (last->next != *head) {
            last = last->next;
        }
        *head = temp->next;
        last->next = *head;
        free(temp);
    }
}

// Delete node from the end
void deleteEnd(Node** head) {
    if (*head == NULL) {
        return;
    }
    Node* temp = *head;
    if (temp->next == *head) {
        free(temp);
        *head = NULL;
    } else {
        Node* prev = NULL;
        while (temp->next != *head) {
            prev = temp;
            temp = temp->next;
        }
        prev->next = *head;
        free(temp);
    }
}

// Delete node from a specific position
void deleteMiddle(Node** head, int position) {
    if (*head == NULL) {
        return;
    }
    Node* temp = *head;
    if (position == 0) {
        deleteFront(head);
    } else {
        Node* prev = NULL;
        int count = 0;
        while (count < position && temp->next != *head) {
            prev = temp;
            temp = temp->next;
            count++;
        }
        if (count == position) {
            prev->next = temp->next;
            free(temp);
        }
    }
}

// Display the circular list
void displayList(Node* head) {
    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }
    Node* temp = head;
    do {
        printf("%d ", temp->data);
        temp = temp->next;
    } while (temp != head);
    printf("\n");
}
int main() {
    Node* head = NULL;

    insertEnd(&head ,9);
    insertEnd(&head, 12);
    insertEnd(&head,15);
    insertFront(&head,3 );
    insertFront(&head,0);
    insertMiddle(&head, 6,2);

    printf("List after insertions:\n");
    displayList(head);

    deleteFront(&head);
    deleteEnd(&head);
    deleteMiddle(&head, 1);

    printf("List after deletions:\n");
    displayList(head);

    return 0;
}
