#include <stdio.h>
#include <stdlib.h>
struct Node {
    int data;
    struct Node *next;
    struct Node *prev;
} Node;


Node* createNode(int data) {
    Node *newNode = (Node*)malloc(sizeof(Node));
    newNode->data = data;
    newNode->next = newNode;
    newNode->prev = newNode;
    return newNode;
}


void displayList(Node *head) {
    if (head == NULL) {
        printf("List is empty.\n");
        return;
    }
    Node *temp = head;
    do {
        printf("%d ", temp->data);
        temp = temp->next;
    } while (temp != head);
    printf("\n");
}

void insertAtFront(Node **head, int data) {
    Node *newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    Node *tail = (*head)->prev;
    newNode->next = *head;
    newNode->prev = tail;
    tail->next = newNode;
    (*head)->prev = newNode;
    *head = newnewNode;
}
void insertAtEnd(Node **head, int data) {
    Node *newNode = createNode(data);
    if (*head == NULL) {
        *head = newNode;
        return;
    }
    Node *tail = (*head)->prev;
    newNode->next = *head;
    newNode->prev = tail;
    tail->next = newNode;
    (*head)->prev = newNode;
}

void insertAtMiddle(Node **head, int data, int position) {
    if (*head == NULL) {
        printf("List is empty. Insert at the end.\n");
        insertAtEnd(head, data);
        return;
    }
    Node *newNode = createNode(data);
    Node *temp = *head;
    int count = 1;
    while (count < position - 1 && temp->next != *head) {
        temp = temp->next;
        count++;
    }
    newNode->next = temp->next;
    newNode->prev = temp;
    temp->next->prev = newNode;
    temp->next = newNode;
}


void deleteAtFront(Node **head) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }
    Node *temp = *head;
    if (*head == (*head)->next) {
        free(*head);
        *head = NULL;
    } else {
        Node *tail = (*head)->prev;
        *head = (*head)->next;
        (*head)->prev = tail;
        tail->next = *head;
        free(temp);
    }
}


void deleteAtEnd(Node **head) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }
    Node *temp = (*head)->prev;
    if (*head == temp) {
        free(*head);
        *head = NULL;
    } else {
        Node *newTail = temp->prev;
        newTail->next = *head;
        (*head)->prev = newTail;
        free(temp);
    }
}

void deleteAtMiddle(Node **head, int position) {
    if (*head == NULL) {
        printf("List is empty.\n");
        return;
    }
    Node *temp = *head;
    int count = 1;
    while (count < position && temp->next != *head) {
        temp = temp->next;
        count++;
    }
    if (temp == *head) {
        printf("Position is out of range.\n");
        return;
    }
    temp->prev->next = temp->next;
    temp->next->prev = temp->prev;
    if (temp == *head) {
        *head = temp->next;
    }
    free(temp);
}

int main() {
    Node *head = NULL;

    insertAtEnd(&head, 10);
    insertAtEnd(&head, 20);
    insertAtEnd(&head, 30);
    insertAtEnd(&head, 40);

    printf("List after insertions at end: ");
    displayList(head);

    insertAtFront(&head, 5);
    insertAtMiddle(&head, 15, 3);

    printf("List after insertions at front and middle: ");
    displayList(head);

    deleteAtFront(&head);
    deleteAtEnd(&head);
    deleteAtMiddle(&head, 2);

    printf("List after deletions: ");
    displayList(head);

    return 0;
}
