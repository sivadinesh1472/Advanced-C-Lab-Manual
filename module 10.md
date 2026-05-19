EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.

 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node *next;
    };
    
    struct Node* create(int arr[], int n) {
        struct Node *head = NULL, *temp = NULL;
        for (int i = 0; i < n; i++) {
            struct Node *newNode = malloc(sizeof(struct Node));
            newNode->data = arr[i]; newNode->next = NULL;
            if (!head) head = temp = newNode;
            else temp->next = newNode, temp = newNode;
        }
        return head;
    }
    
    int search(struct Node* head, int key) {
        while (head) {
            if (head->data == key) return 1;
            head = head->next;
        }
        return 0;
    }
    
    int main() {
        int arr[] = {10, 20, 30, 40, 50}, key = 30;
        struct Node* head = create(arr, 5);
        if (search(head, key)) printf("Found\n");
        else printf("Not Found\n");
        return 0;
    }


Output:

    Found



Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
    
    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node *next;
    };
    
    void insertEnd(struct Node **head, int value) {
        struct Node *newNode = malloc(sizeof(struct Node));
        newNode->data = value; newNode->next = NULL;
        if (*head == NULL) *head = newNode;
        else {
            struct Node *temp = *head;
            while (temp->next) temp = temp->next;
            temp->next = newNode;
        }
    }
    
    void display(struct Node *head) {
        while (head) {
            printf("%d ", head->data);
            head = head->next;
        }
    }
    
    int main() {
        struct Node *head = NULL;
        insertEnd(&head, 10);
        insertEnd(&head, 20);
        insertEnd(&head, 30);
        display(head);
        return 0;
    }


Output:

    10 20 30


 
Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node *prev, *next;
    };
    
    void append(struct Node **head, int value) {
        struct Node *newNode = malloc(sizeof(struct Node));
        newNode->data = value; newNode->next = NULL;
        if (*head == NULL) {
            newNode->prev = NULL;
            *head = newNode;
            return;
        }
        struct Node *temp = *head;
        while (temp->next) temp = temp->next;
        temp->next = newNode;
        newNode->prev = temp;
    }
    
    void traverseForward(struct Node *head) {
        printf("Forward: ");
        while (head) {
            printf("%d ", head->data);
            if (head->next == NULL) break;
            head = head->next;
        }
        printf("\n");
    
        printf("Backward: ");
        while (head) {
            printf("%d ", head->data);
            head = head->prev;
        }
        printf("\n");
    }
    
    int main() {
        struct Node *head = NULL;
        append(&head, 10);
        append(&head, 20);
        append(&head, 30);
        traverseForward(head);
        return 0;
    }


Output:

    Forward: 10 20 30
    Backward: 30 20 10
    


Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node *prev, *next;
    };
    
    void insertEnd(struct Node **head, int value) {
        struct Node *newNode = malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
        
        if (*head == NULL) {
            newNode->prev = NULL;
            *head = newNode;
            return;
        }
    
        struct Node *temp = *head;
        while (temp->next) temp = temp->next;
    
        temp->next = newNode;
        newNode->prev = temp;
    }
    
    void display(struct Node *head) {
        while (head) {
            printf("%d ", head->data);
            head = head->next;
        }
        printf("\n");
    }
    
    int main() {
        struct Node *head = NULL;
        insertEnd(&head, 5);
        insertEnd(&head, 15);
        insertEnd(&head, 25);
        display(head);
        return 0;
    }


Output:

    5 15 25



Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
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


Program:
    
    #include <stdio.h>
    #include <stdlib.h>
    
    struct Node {
        int data;
        struct Node *next;
    };
    
    void deleteNode(struct Node **head, int key) {
        struct Node *temp = *head, *prev = NULL;
    
        if (temp && temp->data == key) {
            *head = temp->next;
            free(temp);
            return;
        }
    
        while (temp && temp->data != key) {
            prev = temp;
            temp = temp->next;
        }
    
        if (!temp) return;
    
        prev->next = temp->next;
        free(temp);
    }
    
    void insertEnd(struct Node **head, int value) {
        struct Node *newNode = malloc(sizeof(struct Node));
        newNode->data = value; newNode->next = NULL;
        if (!*head) *head = newNode;
        else {
            struct Node *temp = *head;
            while (temp->next) temp = temp->next;
            temp->next = newNode;
        }
    }
    
    void display(struct Node *head) {
        while (head) {
            printf("%d ", head->data);
            head = head->next;
        }
        printf("\n");
    }
    
    int main() {
        struct Node *head = NULL;
        insertEnd(&head, 10);
        insertEnd(&head, 20);
        insertEnd(&head, 30);
        display(head);
        deleteNode(&head, 20);
        display(head);
        return 0;
    }


Output:

    
    
    10 20 30
    10 30




Result:
Thus, the function that deletes a given element from a linked list is verified successfully.
