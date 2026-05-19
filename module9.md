EXP NO:11 C PROGRAM TO DISPLAY STACK ELEMENTS USING AN ARRAY.

Aim:
To write a C program to display stack elements using an array.
Algorithm:
1.	Include Necessary Header Files
2.	Declare Global Variables
3.	Define the Display Function
4.	Main Function (or Other Relevant Code)
5.	Initialize the stack and top as needed.
6.	Perform stack operations (push, pop, etc.).
7.	Use the display function to visualize the stack's contents
 
Program:

```
    #include <stdio.h>
    #define MAX 5
    
    int stack[MAX], top = -1;
    
    void push(int value) {
        if (top < MAX - 1) {
            stack[++top] = value;
        }
    }
    
    void display() {
        for (int i = top; i >= 0; i--) {
            printf("%d ", stack[i]);
        }
        printf("\n");
    }
    
    int main() {
        push(10);
        push(20);
        push(30);
        push(40);
        push(50);
        display();
        return 0;
    }
```

Output:

    50 40 30 20 10




Result:
Thus, the program to display stack elements using an array is verified successfully.
 

EXP NO:12  PROGRAM TO PUSH THE GIVEN ELEMENT IN TO A STACK USING ARRAY.
Aim:
To create a C program to push the given element in to a stack using array.
Algorithm:
1.	Declare global variables for the stack size, top index, and the stack itself.
2.	Define the push function to add a floating-point number to the stack.
3.	Initialize the stack size, top index, and the stack itself.
4.	Call the push function as needed.
 
Program:
```
    #include <stdio.h>
    #define MAX 5
    
    int stack[MAX], top = -1;
    
    void push(int value) {
        if (top < MAX - 1) {
            stack[++top] = value;
            printf("%d pushed onto stack\n", value);
        } else {
            printf("Stack Overflow! Cannot push %d\n", value);
        }
    }
    
    int main() {
        push(10);
        push(20);
        push(30);
        push(40);
        push(50);
        push(60); 
        return 0;
    }
    
```
Output:

    10 pushed onto stack
    20 pushed onto stack
    30 pushed onto stack
    40 pushed onto stack
    50 pushed onto stack
    Stack Overflow! Cannot push 60
    




Result:
Thus, the program to push the given element in to a stack using array is verified successfully


 
EXP NO:13 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING ARRAY.
Aim:
To write a C program to display queue elements using array

Algorithm:
1.	Declare global variables for the queue, rear, front, and iteration.
2.	Define the display function to print the elements of the queue.
3.	Initialize the queue, rear, and front as needed.
4.	Call the display function and perform other queue operations as needed.
 
Program:
```

    #include <stdio.h>
    #define MAX 5
    
    int queue[MAX], front = -1, rear = -1;
    
    void enqueue(int value) {
        if (rear < MAX - 1) {
            if (front == -1) {
                front = 0; // If the queue is empty, set front to 0
            }
            queue[++rear] = value; 
            printf("%d enqueued into queue\n", value);
        } else {
            printf("Queue Overflow! Cannot enqueue %d\n", value);
        }
    }
    
    void display() {
        if (front == -1) {
            printf("Queue is empty!\n");
        } else {
            printf("Queue elements: ");
            for (int i = front; i <= rear; i++) {
                printf("%d ", queue[i]);
            }
            printf("\n");
        }
    }
    
    int main() {
        enqueue(10);
        enqueue(20);
        enqueue(30);
        enqueue(40);
        enqueue(50);
        display();  

    enqueue(60); 
    return 0;
}
```

Output:

    10 enqueued into queue
    20 enqueued into queue
    30 enqueued into queue
    40 enqueued into queue
    50 enqueued into queue
    Queue elements: 10 20 30 40 50
    Queue Overflow! Cannot enqueue 60



Result:
Thus, the program to display queue elements using array is verified successfully.


 
EXP NO:14 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING ARRAY.
Aim:
To write a C program to insert elements in queue using array.

Algorithm:
1.	Declare global variables for the size, rear, front, and the queue itself.
2.	Define the enqueue function to add a float to the queue.
3.	Initialize the rear, front, and size of the queue as needed.
4.	Call the enqueue function as needed.

Program:
```
    #include <stdio.h>
    #define MAX 5
    
    int queue[MAX], front = -1, rear = -1;
    
    void enqueue(int value) {
        if (rear == MAX - 1) {
            printf("Queue Overflow! Cannot enqueue %d\n", value);
        } else {
            if (front == -1) {
                front = 0;  
            }
            queue[++rear] = value;  
            printf("%d enqueued into queue\n", value);
        }
    }
    
    void display() {
        if (front == -1) {
            printf("Queue is empty!\n");
        } else {
            printf("Queue elements: ");
            for (int i = front; i <= rear; i++) {
                printf("%d ", queue[i]);
            }
            printf("\n");
        }
    }
    
    int main() {
        enqueue(10);  
        enqueue(20); 
        enqueue(30); 
        enqueue(40);  
        enqueue(50);  
        display();    
    
        enqueue(60);  
        return 0;
    }
``` 

Output:

    10 enqueued into queue
    20 enqueued into queue
    30 enqueued into queue
    40 enqueued into queue
    50 enqueued into queue
    Queue elements: 10 20 30 40 50
    Queue Overflow! Cannot enqueue 60


Result:
Thus, the program to insert elements in queue using array is verified successfully.



 
EXP NO:15 C FUNCTION TO DELETE ELEMENTS IN QUEUE USING ARRAY



Aim:

To create a function in C that deletes an element from a queue implemented using an array.

Algorithm:

1.	Check if the Queue is Empty
o	If the front pointer is -1, it means the queue is empty, and there are no elements to delete. Print a message indicating that the queue is empty.
2.	Delete the Front Element
o	If the queue is not empty, the element at the front index is deleted.
o	Increment the front pointer by 1 to remove the element and point to the next element in the queue.
3.	Check if the Queue Becomes Empty After Deletion:
o	After deletion, check if the front pointer has passed the rear pointer (front > rear). If this is true, reset both front and rear to -1, indicating that the queue is now empty.
4.	End the Function.



Program:
```
    #include <stdio.h>
    #define MAX 5
    
    int queue[MAX], front = -1, rear = -1;
    
    void enqueue(int value) {
        if (rear == MAX - 1) {
            printf("Queue Overflow! Cannot enqueue %d\n", value);
        } else {
            if (front == -1) {
                front = 0;   
            }
            queue[++rear] = value;  
            printf("%d enqueued into queue\n", value);
        }
    }
    
    void dequeue() {
        if (front == -1 || front > rear) {
            printf("Queue Underflow! Queue is empty\n");
        } else {
            printf("%d dequeued from queue\n", queue[front]);
            front++;  
        }
    }
    
    void display() {
        if (front == -1 || front > rear) {
            printf("Queue is empty!\n");
        } else {
            printf("Queue elements: ");
            for (int i = front; i <= rear; i++) {
                printf("%d ", queue[i]);
            }
            printf("\n");
        }
    }
    
    int main() {
        enqueue(10);   
        enqueue(20);   
        enqueue(30);   
        enqueue(40);            
        enqueue(50);  
        display();   
    
        dequeue();   
        display();    
    
        dequeue();   
        display();    
    
        return 0;
    }
    
```
Output:


    10 enqueued into queue
    20 enqueued into queue
    30 enqueued into queue
    40 enqueued into queue
    50 enqueued into queue
    Queue elements: 10 20 30 40 50
    10 dequeued from queue
    Queue elements: 20 30 40 50
    20 dequeued from queue
    Queue elements: 30 40 50


Result:
Thus, the function that deletes an element from a queue implemented using an array is verified successfully.
