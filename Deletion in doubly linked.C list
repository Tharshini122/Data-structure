#include <stdio.h>
#include <stdlib.h>
 struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
} Node;
Node* createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = NULL;
    newNode->prev = NULL;
    return newNode;
}
void append(Node** head, int data) {
    Node* newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    Node* temp = *head;
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
}
void deleteFront(Node** head) {
    if (*head== NULL) 
    {
    return;
    }
    Node* temp = *head;
    *head = (*head)->next;
    if (*head!= NULL) {
        (*head)->prev = NULL;
    }
    free(temp);
}

void deleteEnd(Node** head) {
    if (*head == NULL) return;
    Node* temp = *head;
    if (temp->next == NULL) {
        *head = NULL;
        free(temp);
        return;
    }
    while (temp->next != NULL) {
        temp = temp->next;
    }
    temp->prev->next = NULL;
    free(temp);
}
void deleteAtPosition(Node** head, int position) {
    if (*head == NULL || position < 0) return;
    Node* temp = *head;
    if (position == 0) {
        deleteFront(head);
        return;
    }
    for (int i = 0; temp != NULL && i < position; i++) {
        temp = temp->next;
    }
    if (temp == NULL) return;
    if (temp->prev != NULL) {
        temp->prev->next = temp->next;
    }
    if (temp->next != NULL) {
        temp->next->prev = temp->prev;
    }
    free(temp);
}
void displayList(Node* head) {
    Node* temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
    printf("\n");
}
int main() {
    Node* head = NULL;

    // Adding elements to the list
    append(&head, 10);
    append(&head, 20);
    append(&head, 30);
    append(&head, 40);

    printf("Original List: ");
    displayList(head);

    deleteFront(&head);
    printf("After deleting front: ");
    displayList(head);

    deleteEnd(&head);
    printf("After deleting end: ");
    displayList(head);

    deleteAtPosition(&head, 1);
    printf("After deleting at position 1: ");
    displayList(head);

    return 0;
}
