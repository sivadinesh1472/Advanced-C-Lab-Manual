

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

    
    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    struct Stack {
        struct Node* top;
    };
    
    void initStack(struct Stack* stack) {
        stack->top = NULL;
    }
    int isEmpty(struct Stack* stack) {
        return stack->top == NULL;
    }
    
    void push(struct Stack* stack, int value) {
        struct Node* newNode = malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = stack->top;
        stack->top = newNode;
    }
    
    int pop(struct Stack* stack) {
        if (isEmpty(stack)) {
            printf("Stack underflow\n");
            return -1;  
        }
        struct Node* temp = stack->top;
        int poppedValue = temp->data;
        stack->top = temp->next;
        free(temp);
        return poppedValue;
    }
    
    void display(struct Stack* stack) {
        if (isEmpty(stack)) {
            printf("Stack is empty\n");
            return;
        }
        struct Node* current = stack->top;
        printf("Stack elements: ");
        while (current) {
            printf("%d ", current->data);
            current = current->next;
        }
        printf("\n");
    }
    
    int main() {
        struct Stack stack;
        initStack(&stack);
    
        push(&stack, 10);
        push(&stack, 20);
        push(&stack, 30);
        push(&stack, 40);
        
        display(&stack); 
    
        printf("Popped: %d\n", pop(&stack));  
        display(&stack);  
    
        return 0;
    }
    

Output:
    
    Stack elements: 40 30 20 10 
    Popped: 40
    Stack elements: 30 20 10



Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    struct Stack {
        struct Node* top;
    };
    
    void initStack(struct Stack* stack) {
        stack->top = NULL;
    }
    
    int isEmpty(struct Stack* stack) {
        return stack->top == NULL;
    }
    
    void push(struct Stack* stack, int value) {
        struct Node* newNode = malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = stack->top;
        stack->top = newNode;
    }
    
    // Function to pop an element from the stack
    int pop(struct Stack* stack) {
        if (isEmpty(stack)) {
            printf("Stack underflow\n");
            return -1;  
        }
    
        struct Node* temp = stack->top;
        int poppedValue = temp->data;
        stack->top = temp->next;  
        free(temp);  
    
        return poppedValue;
    }
    
    void display(struct Stack* stack) {
        if (isEmpty(stack)) {
            printf("Stack is empty\n");
            return;
        }
        struct Node* current = stack->top;
        printf("Stack elements: ");
        while (current) {
            printf("%d ", current->data);
            current = current->next;
        }
        printf("\n");
    }
    
    int main() {
        struct Stack stack;
        initStack(&stack);
    
        push(&stack, 10);
        push(&stack, 20);
        push(&stack, 30);
        push(&stack, 40);
    
        display(&stack);
    
        printf("Popped element: %d\n", pop(&stack));
    
        display(&stack);
    
        return 0;
    }


Output:


    Stack elements: 40 30 20 10 
    Popped element: 40
    Stack elements: 30 20 10



Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    struct Queue {
        struct Node* front;
        struct Node* rear;
    };
    
    void initQueue(struct Queue* queue) {
        queue->front = NULL;
        queue->rear = NULL;
    }
    
    int isEmpty(struct Queue* queue) {
        return queue->front == NULL;
    }
    
    void enqueue(struct Queue* queue, int value) {
        struct Node* newNode = malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
    
        if (isEmpty(queue)) {
            queue->front = newNode;
            queue->rear = newNode;
        } else {
            queue->rear->next = newNode;
            queue->rear = newNode;
        }
    }
    
    int dequeue(struct Queue* queue) {
        if (isEmpty(queue)) {
            printf("Queue underflow\n");
            return -1; 
        }
        struct Node* temp = queue->front;
        int dequeuedValue = temp->data;
        queue->front = temp->next;
        if (queue->front == NULL) {
            queue->rear = NULL; 
        }
        free(temp); // Free the memory of the dequeued node
        return dequeuedValue;
    }
    
    void display(struct Queue* queue) {
        if (isEmpty(queue)) {
            printf("Queue is empty\n");
            return;
        }
        struct Node* current = queue->front;
        printf("Queue elements: ");
        while (current) {
            printf("%d ", current->data);
            current = current->next;
        }
        printf("\n");
    }
    
    int main() {
        struct Queue queue;
        initQueue(&queue);
    
        enqueue(&queue, 10);
        enqueue(&queue, 20);
        enqueue(&queue, 30);
        enqueue(&queue, 40);
    
        display(&queue);
    
        printf("Dequeued element: %d\n", dequeue(&queue));
    
        display(&queue);
    
        return 0;
    }


Output:

    Queue elements: 10 20 30 40 
    Dequeued element: 10
    Queue elements: 20 30 40



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
    
    
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    struct Queue {
        struct Node* front;
        struct Node* rear;
    };
    
    void initQueue(struct Queue* queue) {
        queue->front = NULL;
        queue->rear = NULL;
    }
    
    int isEmpty(struct Queue* queue) {
        return queue->front == NULL;
    }
    
    void enqueue(struct Queue* queue, int value) {
        struct Node* newNode = malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
    
        if (isEmpty(queue)) {
            queue->front = newNode;
            queue->rear = newNode;
        } else {
            queue->rear->next = newNode;
            queue->rear = newNode;
        }
    }
    
    void display(struct Queue* queue) {
        if (isEmpty(queue)) {
            printf("Queue is empty\n");
            return;
        }
    
        struct Node* current = queue->front;
        printf("Queue elements: ");
        while (current != NULL) {
            printf("%d ", current->data);
            current = current->next;
        }
        printf("\n");
    }
    
    int dequeue(struct Queue* queue) {
        if (isEmpty(queue)) {
            printf("Queue underflow\n");
            return -1;
        }
    
        struct Node* temp = queue->front;
        int dequeuedValue = temp->data;
        queue->front = temp->next;
        if (queue->front == NULL) {
            queue->rear = NULL;
        }
        free(temp);
        return dequeuedValue;
    }
    
    int main() {
        struct Queue queue;
        initQueue(&queue);
    
        enqueue(&queue, 10);
        enqueue(&queue, 20);
        enqueue(&queue, 30);
        enqueue(&queuent: %d\n", dequeue(&queue));
    
        display(&queue);
    
        return 0;
    }


Output:

    Queue elements: 10 20 30 40 
    Dequeued element: 10
    Queue elements: 20 30 40


Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node* next;
    };
    
    struct Queue {
        struct Node* front;
        struct Node* rear;
    };
    
    void initQueue(struct Queue* queue) {
        queue->front = NULL;
        queue->rear = NULL;
    }
    
    int isEmpty(struct Queue* queue) {
        return queue->front == NULL;
    }
    
    void enqueue(struct Queue* queue, int value) {
        struct Node* newNode = malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
    
        if (isEmpty(queue)) {
            queue->front = newNode;
            queue->rear = newNode;
        } else {
            queue->rear->next = newNode;
            queue->rear = newNode;
        }
    }
    
    void display(struct Queue* queue) {
        if (isEmpty(queue)) {
            printf("Queue is empty\n");
            return;
        }
    
        struct Node* current = queue->front;
        printf("Queue elements: ");
        while (current != NULL) {
            printf("%d ", current->data);
            current = current->next;
        }
        printf("\n");
    }
    
    int dequeue(struct Queue* queue) {
        if (isEmpty(queue)) {
            printf("Queue underflow\n");
            return -1;
        }
    
        struct Node* temp = queue->front;
        int dequeuedValue = temp->data;
        queue->front = temp->next;
        if (queue->front == NULL) {
            queue->rear = NULL;
        }
        free(temp);
        return dequeuedValue;
    }
    
    int peek(struct Queue* queue) {
        if (isEmpty(queue)) {
            printf("Queue is empty\n");
            return -1;
        }
        return queue->front->data;
    }
    
    int main() {
        struct Queue queue;
        initQueue(&queue);
    
        enqueue(&queue, 10);
        enqueue(&queue, 20);
        enqueue(&queue, 30);
        enqueue(&queue, 40);
    
        display(&queue);
    
        printf("Peek element: %d\n", peek(&queue));
    
        printf("Dequeued element: %d\n", dequeue(&queue));
    
        display(&queue);
    
        return 0;
    }


Output:


    Queue elements: 10 20 30 40 
    Peek element: 10
    Dequeued element: 10
    Queue elements: 20 30 40




Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
