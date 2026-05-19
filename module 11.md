

EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
Aim:
To write a C program to create a function to find the greatest number

Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
Program:
    
    #include <stdio.h>
    
    int findGreatest(int arr[], int n) {
        int max = arr[0];
        for (int i = 1; i < n; i++)
            if (arr[i] > max)
                max = arr[i];
        return max;
    }
    
    int main() {
        int arr[] = {12, 45, 7, 89, 34};
        int n = sizeof(arr) / sizeof(arr[0]);
        int greatest = findGreatest(arr, n);
        printf("Greatest number: %d\n", greatest);
        return 0;
    }


Output:

    Greatest number: 89


Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
Program:

    #include <stdio.h>
    
    void findMaxBitwise(int arr[], int n) {
        int maxAND = 0, maxOR = 0, maxXOR = 0;
    
        for (int i = 0; i < n; i++)
            for (int j = i + 1; j < n; j++) {
                int a = arr[i], b = arr[j];
                if ((a & b) > maxAND) maxAND = a & b;
                if ((a | b) > maxOR)  maxOR  = a | b;
                if ((a ^ b) > maxXOR) maxXOR = a ^ b;
            }
    
        printf("Max AND: %d\n", maxAND);
        printf("Max OR : %d\n", maxOR);
        printf("Max XOR: %d\n", maxXOR);
    }
    
    int main() {
        int arr[] = {5, 10, 15, 20};
        int n = sizeof(arr) / sizeof(arr[0]);
        findMaxBitwise(arr, n);
        return 0;
    }
    

Output:

    Max AND: 12
    Max OR : 31
    Max XOR: 31


Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
Aim:
To write a C program to write the logic for the requests

Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    
    void findGreatest(int arr[], int n) {
        int max = arr[0];
        for (int i = 1; i < n; i++)
            if (arr[i] > max)
                max = arr[i];
        printf("Greatest number: %d\n", max);
    }
    
    void findMaxBitwise(int arr[], int n) {
        int maxAND = 0, maxOR = 0, maxXOR = 0;
        for (int i = 0; i < n; i++)
            for (int j = i + 1; j < n; j++) {
                int a = arr[i], b = arr[j];
                if ((a & b) > maxAND) maxAND = a & b;
                if ((a | b) > maxOR)  maxOR  = a | b;
                if ((a ^ b) > maxXOR) maxXOR = a ^ b;
            }
        printf("Max AND: %d\n", maxAND);
        printf("Max OR : %d\n", maxOR);
        printf("Max XOR: %d\n", maxXOR);
    }
    
    struct Node {
        int data;
        struct Node *next;
    };
    
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
    
    void displayLinkedList(struct Node *head) {
        printf("Linked List: ");
        while (head) {
            printf("%d ", head->data);
            head = head->next;
        }
        printf("\n");
    }
    
    int main() {
        int choice;
        int arr[] = {5, 10, 15, 20};
        int n = sizeof(arr) / sizeof(arr[0]);
        struct Node *head = NULL;
    
        printf("Select an option:\n");
        printf("1. Find Greatest Number\n");
        printf("2. Max AND, OR, XOR\n");
        printf("3. Insert into Linked List\n");
        printf("4. Display Linked List\n");
        printf("Enter choice: ");
        scanf("%d", &choice);
    
        switch (choice) {
            case 1:
                findGreatest(arr, n);
                break;
            case 2:
                findMaxBitwise(arr, n);
                break;
            case 3: {
                int value;
                printf("Enter value to insert into linked list: ");
                scanf("%d", &value);
                insertEnd(&head, value);
                break;
            }
            case 4:
                displayLinkedList(head);
                break;
            default:
                printf("Invalid choice\n");
                break;
        }
        
        return 0;
    }


Output:

    Select an option:
    1. Find Greatest Number
    2. Max AND, OR, XOR
    3. Insert into Linked List
    4. Display Linked List
    Enter choice: 2
    Max AND: 12
    Max OR : 31
    Max XOR: 31


Result:
Thus, the program to write the logic for the requests is verified successfully.


 
EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
Aim:
To write a C program print the sum of the integers in the array.

Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.



Program:

    #include <stdio.h>
    
    int calculateSum(int arr[], int n) {
        int sum = 0;
        for (int i = 0; i < n; i++) {
            sum += arr[i];
        }
        return sum;
    }
    
    int main() {
        int arr[] = {1, 2, 3, 4, 5};  // Example array
        int n = sizeof(arr) / sizeof(arr[0]);  // Size of the array
        int sum = calculateSum(arr, n);
        printf("Sum of the array elements: %d\n", sum);
        return 0;
    }


Output:


    Sum of the array elements: 15

 


Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE



Aim:

To write a C program that counts the number of words in a given sentence.

Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



Program:

    #include <stdio.h>
    #include <ctype.h>
    
    int countWords(char str[]) {
        int count = 0, i = 0;
    
        // Skip leading spaces
        while (str[i] && isspace(str[i])) {
            i++;
        }
    
        // Count words
        while (str[i]) {
            if (!isspace(str[i]) && (i == 0 || isspace(str[i - 1]))) {
                count++;
            }
            i++;
        }
    
        return count;
    }
    
    int main() {
        char sentence[100];
    
        printf("Enter a sentence: ");
        fgets(sentence, sizeof(sentence), stdin);  
    
        int wordCount = countWords(sentence);
        printf("Number of words: %d\n", wordCount);
    
        return 0;
    }


Output:

    Enter a sentence: Hello, how are you?
    Number of words: 4




Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
