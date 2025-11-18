EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```
#include <stdio.h>

int main() {
    int n;

    // Step 1: Initialize and take input
    printf("Enter a number: ");
    scanf("%d", &n);

    // Step 2: Switch statement for mapping
    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 7:
            printf("seventy three\n");
            break;
        case 8:
            printf("seventy four\n");
            break;
        case 9:
            printf("seventy five\n");
            break;
        case 10:
            printf("seventy six\n");
            break;
        case 11:
            printf("seventy seven\n");
            break;
        case 12:
            printf("seventy eight\n");
            break;
        case 13:
            printf("seventy nine\n");
            break;
        default:
            printf("greater than 13\n");
            break;
    }

    return 0;
}

```




Output:



<img width="439" height="196" alt="513417861-b44d8388-55d8-4bf9-8b05-6213203e7e5b" src="https://github.com/user-attachments/assets/c88fed53-42a9-428d-b2e6-fa991731e02e" />






Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include <stdio.h>
#include <string.h>

int main() {
    char a[50];
    int i, h, c;

    printf("Enter a string: ");
    scanf("%s", a);

    for (h = 0; h <= 9; h++) {  // loop for each digit 0–9
        c = 0;
        for (i = 0; i < strlen(a); i++) {
            if (a[i] == (h + '0')) {  // check if character matches digit
                c++;
            }
        }
        printf("%d ", c);  // print frequency
    }

    return 0;
}
```




Output:



<img width="542" height="227" alt="513420773-a3e69c78-22fd-4dc1-b36e-349b64fc2665" src="https://github.com/user-attachments/assets/1ed6bc9d-cbb5-434e-8fe1-e6abe2a9a212" />





Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to swap two characters
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Function to sort a string in lexicographical order
void sortString(char *str) {
    int i, j, n = strlen(str);
    for (i = 0; i < n - 1; i++) {
        for (j = i + 1; j < n; j++) {
            if (str[i] > str[j]) {
                swap(&str[i], &str[j]);
            }
        }
    }
}

// Function to find next lexicographical permutation
int nextPermutation(char *str) {
    int i = strlen(str) - 2;
    while (i >= 0 && str[i] >= str[i + 1])
        i--;

    if (i < 0) return 0;  // No next permutation

    int j = strlen(str) - 1;
    while (str[j] <= str[i])
        j--;

    swap(&str[i], &str[j]);

    // Reverse the suffix
    int left = i + 1, right = strlen(str) - 1;
    while (left < right)
        swap(&str[left++], &str[right--]);

    return 1;
}

int main() {
    char *s;
    int n;

    // Input string length
    printf("Enter the length of string: ");
    scanf("%d", &n);

    // Dynamic memory allocation
    s = (char *)malloc((n + 1) * sizeof(char));

    if (s == NULL) {
        printf("Memory allocation failed.\n");
        return 1;
    }

    // Input string
    printf("Enter the string: ");
    scanf("%s", s);

    // Step 1: Sort to start with lexicographically smallest permutation
    sortString(s);

    // Step 2: Print all permutations in lexicographical order
    printf("\nAll permutations in lexicographical order:\n");
    do {
        printf("%s\n", s);
    } while (nextPermutation(s));

    // Step 3: Free memory
    free(s);

    return 0;
}

```




Output:



<img width="537" height="337" alt="513421313-d232fb19-d264-4b87-be92-0d4175446635" src="https://github.com/user-attachments/assets/7f50d88f-c9af-4add-85a8-97c881cc05b4" />






Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```
#include <stdio.h>

int main() {
    int n, i, j, min, len;

    // Input from user
    printf("Enter the value of n: ");
    scanf("%d", &n);

    // Calculate matrix size
    len = n * 2 - 1;

    // Generate the pattern
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            // Calculate the minimum distance to any border
            int top = i;
            int left = j;
            int right = len - 1 - j;
            int bottom = len - 1 - i;

            min = top;
            if (left < min) min = left;
            if (right < min) min = right;
            if (bottom < min) min = bottom;

            // Print pattern value
            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```




Output:



<img width="615" height="347" alt="513421740-dfb48b37-39ff-4cae-a9ca-3a14d9dcc0da" src="https://github.com/user-attachments/assets/0bd74d85-a40e-4254-9fbf-317ea9ccae89" />





Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```
#include <stdio.h>

// Function definition (no arguments, returns an integer)
int square() {
    int num, sq;
    printf("Enter a number: ");
    scanf("%d", &num);
    sq = num * num;   // calculate square
    return sq;        // return result
}

int main() {
    int result;

    // Call the function and store the return value
    result = square();

    // Display the result
    printf("Square of the given number is: %d\n", result);

    return 0;
}
```




Output:




<img width="525" height="212" alt="513422151-83719317-cdf1-4d2e-ae11-26d95a70187e" src="https://github.com/user-attachments/assets/e4aaf1df-d05f-4254-aee5-e1c7a2f92e65" />





Result:
Thus, the program is verified successfully



























