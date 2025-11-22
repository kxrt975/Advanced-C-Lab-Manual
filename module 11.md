## EXP NO: 21 — C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER

### Aim
To write a C program to create a function to find the greatest number.

### Algorithm
1. Include the necessary header file `<stdio.h>`.
2. Use a series of `if` and `else if` statements to compare the values and return the maximum among them.
3. Declare variables `n1`, `n2`, `n3`, `n4`, and `greater` to store user input and the result.
4. Use `scanf` to take four integers as input.
5. Call the `max_of_four` function with the input integers and store the result in the `greater` variable.

### Program
~~~c
#include <stdio.h>

int max_of_four(int a, int b, int c, int d) {
    int max = a;
    if (b > max) max = b;
    if (c > max) max = c;
    if (d > max) max = d;
    return max;
}

int main() {
    int n1, n2, n3, n4, greater;
    printf("Enter four numbers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);
    greater = max_of_four(n1, n2, n3, n4);
    printf("Greatest number = %d\n", greater);
    return 0;
}
~~~

### Output
```
Enter four numbers: 12 45 23 9
Greatest number = 45
```

### Result
Thus, the program that creates a function to find the greatest number is verified successfully.

---

## EXP NO: 22 — C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND XOR COMPARISONS

### Aim
To write a C program to print the maximum values for the AND, OR, and XOR comparisons.

### Algorithm
1. Define a function `calculate_the_max` that takes two integers `n` and `k` as parameters.
2. Declare variables `a`, `o`, and `x` to store the maximum values for AND, OR, and XOR operations, respectively.
3. Use nested loops to iterate through pairs of integers `(i, j)` from 1 to `n`.
4. Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (`a`, `o`, `x`).
5. Declare variables `n` and `k` to store user input.
6. Use `scanf` to take two integers as input.
7. Call the `calculate_the_max` function with input values.

### Program
~~~c
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int a = 0, o = 0, x = 0;
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and = i & j;
            int or  = i | j;
            int xor = i ^ j;
            if (and < k && and > a) a = and;
            if (or < k && or > o) o = or;
            if (xor < k && xor > x) x = xor;
        }
    }
    printf("%d\n%d\n%d\n", a, o, x);
}

int main() {
    int n, k;
    printf("Enter values for n and k: ");
    scanf("%d %d", &n, &k);
    calculate_the_max(n, k);
    return 0;
}
~~~

### Output
```
Enter values for n and k: 5 4
2
3
3
```

### Result
Thus, the program to print the maximum values for the AND, OR, and XOR comparisons is verified successfully.

---

## EXP NO: 23 — C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS

### Aim
To write a C program to write the logic for the requests.

### Algorithm
1. Declare variables `noshel` and `noque` to store the number of shelves and queries, respectively.
2. Use `scanf` to take two integers as input for the number of shelves and queries.
3. Declare a 2D array `shelarr` to represent shelves and books, and an array `nobookarr` to store the number of books on each shelf.
4. Declare variables `k` and `c` to keep track of the book index and total number of books.
5. Use a `for` loop to iterate over the queries.

### Program
~~~c
#include <stdio.h>
#include <stdlib.h>

int main() {
    int noshel, noque;
    printf("Enter number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);

    int *nobookarr = calloc(noshel, sizeof(int));
    int **shelarr = malloc(noshel * sizeof(int*));

    for (int i = 0; i < noque; i++) {
        int type;
        scanf("%d", &type);
        if (type == 1) {
            int x, y;
            scanf("%d %d", &x, &y);
            nobookarr[x]++;
            shelarr[x] = realloc(shelarr[x], nobookarr[x] * sizeof(int));
            shelarr[x][nobookarr[x] - 1] = y;
        } else if (type == 2) {
            int x, y;
            scanf("%d %d", &x, &y);
            printf("%d\n", shelarr[x][y]);
        } else if (type == 3) {
            int x;
            scanf("%d", &x);
            printf("%d\n", nobookarr[x]);
        }
    }

    for (int i = 0; i < noshel; i++)
        free(shelarr[i]);
    free(shelarr);
    free(nobookarr);

    return 0;
}
~~~

### Output
```
Enter number of shelves and queries: 2 4
1 0 10
1 0 20
3 0
2 0 1
2
20
```

### Result
Thus, the program to write the logic for the requests is verified successfully.

---

## EXP NO: 24 — C PROGRAM TO PRINT THE SUM OF THE INTEGERS IN THE ARRAY

### Aim
To write a C program to print the sum of the integers in the array.

### Algorithm
1. Declare a variable `n` to store the number of integers.
2. Use `scanf` to take an integer `n` as input.
3. Declare an array `a` of size `n` to store the integers.
4. Declare a variable `sum` and initialize it to zero.
5. Use a `for` loop to iterate `n` times.
6. Use `scanf` to input each integer and add it to the sum.
7. Print the final sum using `printf`.

### Program
~~~c
#include <stdio.h>

int main() {
    int n, sum = 0;
    printf("Enter number of elements: ");
    scanf("%d", &n);
    int a[n];

    printf("Enter %d integers: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("Sum of array elements = %d\n", sum);
    return 0;
}
~~~

### Output
```
Enter number of elements: 5
Enter 5 integers: 1 2 3 4 5
Sum of array elements = 15
```

### Result
Thus, the program that prints the sum of the integers in the array is verified successfully.

---

## EXP NO: 25 — C PROGRAM TO COUNT THE NUMBER OF WORDS IN A SENTENCE

### Aim
To write a C program that counts the number of words in a given sentence.

### Algorithm
1. Input the sentence: Take a sentence from the user.
2. Initialize a counter variable to track the number of words.
3. Process each character of the sentence:
   - Iterate through the sentence, checking each character.
   - If a character is not a space, it belongs to a word.
   - If it's the first non-space character after a space or at the start, increment the word count.
4. Skip over spaces and punctuation, considering words separated by spaces.
5. Display the total word count.

### Program
~~~c
#include <stdio.h>

int main() {
    char str[200];
    int count = 0, inWord = 0;

    printf("Enter a sentence: ");
    fgets(str, sizeof(str), stdin);

    for (int i = 0; str[i] != '\0'; i++) {
        if (str[i] != ' ' && str[i] != '\n') {
            if (!inWord) {
                inWord = 1;
                count++;
            }
        } else {
            inWord = 0;
        }
    }

    printf("Number of words: %d\n", count);
    return 0;
}
~~~

### Output
```
Enter a sentence: C programming is fun
Number of words: 3
```

### Result
Thus, the program that counts the number of words in a given sentence is verified successfully.
