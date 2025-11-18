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

```
#include <stdio.h>

struct eligible {
    int age;
    char n[50];   // name of the person
};

int main() {
    int i, num;
    
    printf("Enter number of people: ");
    scanf("%d", &num);

    struct eligible e[num];  // array of structures

    for(i = 0; i < num; i++) {
        printf("\nEnter name: ");
        scanf("%s", e[i].n);

        printf("Enter age: ");
        scanf("%d", &e[i].age);
    }

    printf("\n--- Vaccine Eligibility Results ---\n");
    for(i = 0; i < num; i++) {
        if(e[i].age <= 6) {
            printf("%s (Age: %d) → Vaccine Eligibility: No\n", e[i].n, e[i].age);
        } else {
            printf("%s (Age: %d) → Vaccine Eligibility: Yes\n", e[i].n, e[i].age);
        }
    }

    return 0;
}

```


Output:

<img width="428" height="456" alt="513199958-35c0af3a-1387-4946-bd1f-ae304247e652" src="https://github.com/user-attachments/assets/26c9057f-fbf5-4c12-a3bb-121d7eb9cae4" />



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

```
#include <stdio.h>

// Define structure
struct numbers {
    int a;
    int b;
    int sum;  // to store result
};

// Function that takes structure and returns structure
struct numbers add(struct numbers n) {
    n.sum = n.a + n.b;
    return n;
}

int main() {
    struct numbers n, result;

    // Input values
    printf("Enter value for a: ");
    scanf("%d", &n.a);

    printf("Enter value for b: ");
    scanf("%d", &n.b);

    // Call function
    result = add(n);

    // Print result
    printf("Sum of %d and %d = %d\n", result.a, result.b, result.sum);

    return 0;
}
```




Output:


<img width="410" height="215" alt="513200430-13e1b477-6176-4bba-b4f6-ad05e5e1a9c9" src="https://github.com/user-attachments/assets/f84d8415-e90b-4393-93bd-0097b6a827aa" />




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

```
#include <stdio.h>
#include <stdlib.h>  // for exit()

int main() {
    FILE *p;          // file pointer
    char name[100];   // to store file name

    // Prompt user for file name
    printf("Enter the file name to create: ");
    scanf("%s", name);

    // Try to open file in write mode
    p = fopen(name, "w");

    if (p == NULL) {
        // fopen failed
        printf("Error: Could not create file %s\n", name);
        exit(1);  // exit with non-zero status
    }

    // Success
    printf("File '%s' has been created successfully.\n", name);
    printf("File '%s' has been opened successfully.\n", name);

    // Close file
    fclose(p);
    printf("File '%s' has been closed.\n", name);

    return 0;  // successful execution
}
```




Output:







<img width="965" height="854" alt="513202074-674d1e2a-63b3-44ac-a9d0-f16ca1543a1c" src="https://github.com/user-attachments/assets/25ab5153-4cc7-4a8c-94fb-4d512bb52fa2" />







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

```
#include <stdio.h>
#include <stdlib.h>   // for exit()

int main() {
    FILE *p;                 // file pointer
    char name[100];          // to store file name
    char text[200];          // to store each string
    int num, i;

    // Prompt user for file name
    printf("Enter the file name to create: ");
    scanf("%s", name);

    // Prompt user for number of strings
    printf("Enter the number of strings to insert: ");
    scanf("%d", &num);

    // Open file in write mode
    p = fopen(name, "w");
    if (p == NULL) {
        printf("Error: Could not create/open file %s\n", name);
        exit(1);  // exit with non-zero status
    }

    printf("File '%s' has been opened successfully.\n", name);

    // Loop to input strings and write them to file
    for (i = 0; i < num; i++) {
        printf("Enter string %d: ", i + 1);
        scanf(" %[^\n]", text);   // read string with spaces
        fputs(text, p);
        fputs("\n", p);           // add newline after each string
    }

    // Close file
    fclose(p);
    printf("Data has been added successfully to '%s'.\n", name);

    return 0;  // successful execution
}

```




Output:


<img width="1475" height="780" alt="513203833-6f92d254-4f1e-41f3-bd19-f44aeb35ee99" src="https://github.com/user-attachments/assets/50e59130-396d-4873-aae0-46137459a7df" />







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

```
#include <stdio.h>
#include <stdlib.h>   // for malloc and free

// Define structure
struct subject {
    char name[50];
    int marks;
};

int main() {
    int n, i;
    struct subject *s;   // pointer to dynamically allocated array

    // Step 1 & 2: Input number of subjects
    printf("Enter the number of subjects: ");
    scanf("%d", &n);

    // Step 3 & 4: Dynamically allocate memory
    s = (struct subject *)malloc(n * sizeof(struct subject));

    // Step 5: Check if memory allocation failed
    if (s == NULL) {
        printf("Error: Memory allocation failed!\n");
        return 1;  // exit with non-zero status
    }

    // Step 6 & 7: Input details of each subject
    for (i = 0; i < n; i++) {
        printf("\nEnter name of subject %d: ", i + 1);
        scanf("%s", s[i].name);

        printf("Enter marks for subject %d: ", i + 1);
        scanf("%d", &s[i].marks);
    }

    // Step 8 & 9: Display details of each subject
    printf("\n--- Student Subject Details ---\n");
    for (i = 0; i < n; i++) {
        printf("Subject: %s | Marks: %d\n", s[i].name, s[i].marks);
    }

    // Step 10 & 11: Free allocated memory
    free(s);

    // Step 12 & 13: End program
    return 0;
}

```




Output:




<img width="641" height="552" alt="513204868-9b662022-f024-4c6d-9608-920d0a7f0c37" src="https://github.com/user-attachments/assets/90d9d892-d011-410e-9aae-1f13ae2d9d3d" />





Result:
Thus, the program is verified successfully
