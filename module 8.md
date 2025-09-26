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

    // 1. Input
    printf("Enter a number: ");
    scanf("%d", &n);

    // 2. Switch cases for specific numbers
    switch(n) {
        case 5:
            printf("seventy one\n");
            break;
        case 6:
            printf("seventy two\n");
            break;
        case 13:
            printf("seventy three\n");
            break;
        case 7:
            printf("seventy four\n");
            break;
        case 8:
            printf("seventy five\n");
            break;
        case 9:
            printf("seventy six\n");
            break;
        case 10:
            printf("seventy seven\n");
            break;
        case 11:
            printf("seventy eight\n");
            break;
        case 12:
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

```
Enter a number: 5
seventy one
```

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
    int freq[10] = {0}; // Initialize all digit frequencies to 0

    // Input string
    printf("Enter a string of digits: ");
    scanf("%s", a);

    // Count frequency of digits 0 to 3 (and others, if needed)
    for (int i = 0; i < strlen(a); i++) {
        if (a[i] >= '0' && a[i] <= '3') {
            freq[a[i] - '0']++; // Convert char to int index
        }
    }

    // Print 10 space-separated integers
    for (int i = 0; i < 10; i++) {
        printf("%d ", freq[i]);
    }

    printf("\n");
    return 0;
}
```

Output:
```
Enter a string of digits: 012301233210
3 3 3 3 0 0 0 0 0 0
```

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

// Function to swap characters
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Comparator function for qsort
int compare(const void *a, const void *b) {
    return strcmp(*(const char **)a, *(const char **)b);
}

// Recursive function to generate permutations
void permute(char *str, int l, int r, char **result, int *index) {
    if (l == r) {
        result[*index] = (char *)malloc((strlen(str) + 1) * sizeof(char));
        strcpy(result[*index], str);
        (*index)++;
    } else {
        for (int i = l; i <= r; i++) {
            swap((str + l), (str + i));
            permute(str, l + 1, r, result, index);
            swap((str + l), (str + i)); // backtrack
        }
    }
}

int factorial(int n) {
    return (n <= 1) ? 1 : n * factorial(n - 1);
}

int main() {
    char input[20];
    printf("Enter a string: ");
    scanf("%s", input);

    int n = strlen(input);
    int total = factorial(n);

    // Allocate memory to store all permutations
    char **permutations = (char **)malloc(total * sizeof(char *));
    int index = 0;

    permute(input, 0, n - 1, permutations, &index);

    // Sort permutations lexicographically
    qsort(permutations, total, sizeof(char *), compare);

    printf("Lexicographical permutations:\n");
    for (int i = 0; i < total; i++) {
        printf("%s\n", permutations[i]);
        free(permutations[i]); // Free each permutation
    }

    free(permutations); // Free array of pointers
    return 0;
}
```
Output:

```
Enter a string: abc
Lexicographical permutations:
abc
acb
bac
bca
cab
cba
```
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

int min(int a, int b) {
    return (a < b) ? a : b;
}

int main() {
    int n;
    printf("Enter the value of n: ");
    scanf("%d", &n);

    int len = 2 * n - 1;

    for (int i = 0; i < len; i++) {
        for (int j = 0; j < len; j++) {
            int min_val = i < j ? i : j;
            min_val = min(min_val, len - 1 - i);
            min_val = min(min_val, len - 1 - j);

            printf("%d ", n - min_val);
        }
        printf("\n");
    }

    return 0;
}
```

Output:

```
3 3 3 3 3
3 2 2 2 3
3 2 1 2 3
3 2 2 2 3
3 3 3 3 3
```

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

// Function without arguments and with return type
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main() {
    int result;

    // Call the square function and store the result
    result = square();

    // Display the result
    printf("Square of the number is: %d\n", result);

    return 0;
}
```
Output:

```
Enter a number: 5
Square of the number is: 25
```

Result:
Thus, the program is verified successfully



























