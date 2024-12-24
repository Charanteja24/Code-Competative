#include <stdio.h>
#include <stdlib.h>

typedef struct Node {
    int data;
    struct Node* next;
} Node;

Node* createNode(int data) {
    Node* newNode = (Node*)malloc(sizeof(Node));
    if (!newNode) {
        printf("Memory allocation failed!\n");
        exit(1);
    }
    newNode->data = data;
    newNode->next = NULL;
    return newNode;
}

int isEmpty(Node* top) {
    return top == NULL;
}

void push(Node** top, int data) {
    Node* newNode = createNode(data);
    newNode->next = *top; 
    *top = newNode;      
    printf("%d pushed onto the stack.\n", data);
}

int pop(Node** top) {
    if (isEmpty(*top)) {
        printf("Stack Underflow! Cannot pop from the stack.\n");
        return -1;
    }
    Node* temp = *top;
    int poppedData = temp->data;
    *top = (*top)->next;
    free(temp);        
    return poppedData;
}

int peek(Node* top) {
    if (isEmpty(top)) {
        printf("Stack is empty! Cannot peek.\n");
        return -1; 
    }
    return top->data;
}

void freeStack(Node** top) {
    while (!isEmpty(*top)) {
        pop(top);
    }
}

int main() {
    Node* top = NULL; 

    push(&top, 10);
    push(&top, 20);
    push(&top, 30);

    printf("Top element is: %d\n", peek(top));

    printf("Popped element is: %d\n", pop(&top));
    printf("Popped element is: %d\n", pop(&top));

    if (isEmpty(top)) {
        printf("Stack is empty.\n");
    } else {
        printf("Stack is not empty.\n");
    }

    freeStack(&top); 
    return 0;
}
