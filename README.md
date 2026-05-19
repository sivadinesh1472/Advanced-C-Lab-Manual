EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
Program:

    #include <stdio.h>
    
    #define SIZE 5  
    
    
    struct Person {
        char name[50];
        int age;
    };
    
    int main() {
        struct Person people[SIZE];
        int i;

    printf("Enter details for %d people:\n", SIZE);
    for(i = 0; i < SIZE; i++) {
        printf("Person %d:\n", i + 1);
        printf("Name: ");
        scanf(" %[^\n]", people[i].name);
        printf("Age: ");
        scanf("%d", &people[i].age);
    }

    printf("\nVaccine Eligibility:\n");
    for(i = 0; i < SIZE; i++) {
        if(people[i].age > 6) {
            printf("%s is eligible for vaccination (Age: %d)\n", people[i].name, people[i].age);
        } else {
            printf("%s is NOT eligible for vaccination (Age: %d)\n", people[i].name, people[i].age);
        }
    }

    return 0;
}



Output:

    Enter details for 5 people:
    Person 1:
    Name: Alice
    Age: 10
    Person 2:
    Name: Bob
    Age: 5
    Person 3:
    Name: Charlie
    Age: 7
    Person 4:
    Name: Diana
    Age: 6
    Person 5:
    Name: Eve
    Age: 15
    
    Vaccine Eligibility:
    Alice is eligible for vaccination (Age: 10)
    Bob is NOT eligible for vaccination (Age: 5)
    Charlie is eligible for vaccination (Age: 7)
    Diana is NOT eligible for vaccination (Age: 6)
    Eve is eligible for vaccination (Age: 15)



Result:
Thus, the program is verified successfully. 



EXP NO:2 C PROGRAM FOR PASSING STRUCTURES AS FUNCTION ARGUMENTS AND RETURNING A STRUCTURE FROM A FUNCTION
Aim:
To write a C program for passing structure as function and returning a structure from a function

Algorithm:
1.	Define structure numbers with members a and b.
2.	Declare variable n of type numbers.
3.	Prompt the user to enter values for a and b.
4.	Input values for a and b into n using scanf.
5.	Call the add function with n as an argument.
6.	Print the result returned by the add function.
7.	Return 0
 
Program:

    #include <stdio.h>
    
    struct Person {
        char name[50];
        int age;
    };
    
    struct Person update(struct Person p) {
        if(p.age < 18)
            p.age = 18;
        return p;
    }
    
    int main() {
        struct Person p1, p2;

    printf("Enter name: ");
    scanf(" %[^\n]", p1.name);
    printf("Enter age: ");
    scanf("%d", &p1.age);

    p2 = update(p1);

    printf("Name: %s\n", p2.name);
    printf("Age: %d\n", p2.age);

    return 0;
}





Output:

    Enter name: John
    Enter age: 16
    Name: John
    Age: 18





Result:
Thus, the program is verified successfully


 
EXP.NO:3 C PROGRAM TO READ A FILE NAME FROM USER AND WRITE THAT FILE USING FOPEN()

Aim:
To write a C program to read a file name from user

Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare a character array name to store the file name.
4.	Prompt the user to enter a file name.
Use scanf to input the file name into the name array.
5.	Print a message indicating that the file with the specified name has been created successfully.
6.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
1.	Print a message indicating that the file has been opened successfully.
2.	Use fclose to close the file.
3.	Print a message indicating that the file has been closed.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

    #include <stdio.h>
    
    int main() {
        char filename[100];
        FILE *fp;

    printf("Enter the file name: ");
    scanf("%s", filename);

    fp = fopen(filename, "r");

    if (fp == NULL) {
        printf("Unable to open file: %s\n", filename);
    } else {
        printf("File '%s' opened successfully.\n", filename);
        fclose(fp);
    }

    return 0;
}





Output:

    
    Enter the file name: example.txt
    File 'example.txt' opened successfully.
    











Result:
Thus, the program is verified successfully
 


EXP NO:4   PROGRAM TO READ A FILE NAME FROM USER, WRITE THAT FILE AND INSERT TEXT IN TO THAT FILE
Aim:
To write a C program to read, a file and insert text in that file
Algorithm:
1.	Include the necessary header file stdio.h.
2.	Begin the main function.
3.	Declare a file pointer p.
Declare character arrays name and text. Declare an integer variable num.
4.	Prompt the user to enter a file name and the number of strings.
Use scanf to input the file name into the name array and the number of strings into the num variable.
5.	Use fopen to open a file with the name provided by the user in write mode ("w").
-	If successful, continue to the next step.
-	If unsuccessful, print an error message and exit the program with a non-zero status.
6.	Print a message indicating that the file has been opened successfully.
1.	Use a loop to input strings from the user and write them to the file using fputs.
2.	Use fclose to close the file.
3.	Print a message indicating that data has been added successfully.
4.	End the main function.
5.	Return 0 to indicate successful program execution.
 
Program:

    #include <stdio.h>
    
    int main() {
        char filename[100];
        char text[1000];
        FILE *fp;

    printf("Enter the file name: ");
    scanf("%s", filename);

    fp = fopen(filename, "a");  
    if (fp == NULL) {
        printf("Unable to open file: %s\n", filename);
        return 1;
    }

    printf("Enter text to insert into the file:\n");
    getchar();  
    fgets(text, sizeof(text), stdin);

    fputs(text, fp);
    fclose(fp);

    printf("Text inserted successfully into '%s'.\n", filename);
    return 0;
}





Output:


    Enter the file name: notes.txt
    Enter text to insert into the file:
    This is a new line added to the file.
    Text inserted successfully into 'notes.txt'.







Result:
Thus, the program is verified successfully



Ex No 5 : C PROGRAM TO DISPLAY STUDENT DETAILS USING STRUCTURE

Aim:
The aim of this program is to dynamically allocate memory to store information about multiple subjects (name and marks), input the details for each subject, and then display the stored information. Finally, it frees the allocated memory to prevent memory leaks.

Algorithm:
1.Input the number of subjects.

2.Read the integer value n from the user, which represents the number of subjects.

3.Dynamically allocate memory:

4.Use malloc to allocate memory for n subjects. Each subject has a name (array of characters) and marks (integer).

5.If memory allocation fails (i.e., the pointer s is NULL), display an error message and exit the program.

6.Input the details of each subject

7.Use a for loop to read the name and marks of each subject using scanf. For each subject, store the name as a string and marks as an integer in the dynamically allocated memory.

8.Display the details of each subject

9.Use another for loop to print the name and marks of each subject.

10.Free the allocated memory

11.After all operations are done, call free(s) to release the dynamically allocated memory.

12.Return from the main function

13.End the program by returning 0.

Program:

    #include <stdio.h>
    struct Student {
        char name[50];
        int roll_no;
        float marks;
    };
    
    int main() {
        struct Student student;

    /* Input student details */
    printf("Enter student's name: ");
    scanf(" %[^\n]", student.name);  
    printf("Enter roll number: ");
    scanf("%d", &student.roll_no);
    printf("Enter marks: ");
    scanf("%f", &student.marks);

    /* Display student details */
    printf("\nStudent Details:\n");
    printf("Name: %s\n", student.name);
    printf("Roll Number: %d\n", student.roll_no);
    printf("Marks: %.2f\n", student.marks);

    return 0;
}





Output:




    Enter student's name: John Doe
    Enter roll number: 101
    Enter marks: 85.5
    
    Student Details:
    Name: John Doe
    Roll Number: 101
    Marks: 85.50





Result:
Thus, the program is verified successfully
