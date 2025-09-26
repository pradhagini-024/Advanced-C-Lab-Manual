

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
```
#include <stdio.h>

// Function to find the greatest among four numbers
int max_of_four(int n1, int n2, int n3, int n4) {
    int max = n1;

    if (n2 > max) {
        max = n2;
    }
    if (n3 > max) {
        max = n3;
    }
    if (n4 > max) {
        max = n4;
    }

    return max;
}

int main() {
    int n1, n2, n3, n4, greater;

    printf("Enter four integers: ");
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);

    greater = max_of_four(n1, n2, n3, n4);

    printf("The greatest number is: %d\n", greater);

    return 0;
}
```
Output:
```
Enter four integers: 12 45 7 30
The greatest number is: 45
```
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
```
#include <stdio.h>

void calculate_the_max(int n, int k) {
    int max_and = 0, max_or = 0, max_xor = 0;

    // Iterate over all pairs (i, j) where 1 <= i < j <= n
    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;

            // Update max AND value less than k
            if (and_val > max_and && and_val < k)
                max_and = and_val;

            // Update max OR value less than k
            if (or_val > max_or && or_val < k)
                max_or = or_val;

            // Update max XOR value less than k
            if (xor_val > max_xor && xor_val < k)
                max_xor = xor_val;
        }
    }

    printf("Maximum AND value less than %d is: %d\n", k, max_and);
    printf("Maximum OR value less than %d is: %d\n", k, max_or);
    printf("Maximum XOR value less than %d is: %d\n", k, max_xor);
}

int main() {
    int n, k;

    printf("Enter two integers (n and k): ");
    scanf("%d %d", &n, &k);

    calculate_the_max(n, k);

    return 0;
}
```


Output:
```
Enter two integers (n and k): 5 4
Maximum AND value less than 4 is: 2
Maximum OR value less than 4 is: 3
Maximum XOR value less than 4 is: 3
```
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
```
#include <stdio.h>

int main() {
    int noshel, noque;
    printf("Enter number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);

    int shelarr[noshel][1000]; // Assuming max 1000 books per shelf
    int nobookarr[noshel];     // To store number of books in each shelf

    // Initialize number of books on each shelf to 0
    for (int i = 0; i < noshel; i++) {
        nobookarr[i] = 0;
    }

    int k, c;
    for (int q = 0; q < noque; q++) {
        int queryType;
        printf("Enter query type: ");
        scanf("%d", &queryType);

        if (queryType == 1) {
            // Query 1: Add a book with pages 'c' to shelf 'k'
            printf("Enter shelf index and book pages: ");
            scanf("%d %d", &k, &c);
            shelarr[k][nobookarr[k]] = c;
            nobookarr[k]++;
        }
        else if (queryType == 2) {
            // Query 2: Print pages of the 'c'-th book on shelf 'k'
            printf("Enter shelf index and book index: ");
            scanf("%d %d", &k, &c);
            if (c < nobookarr[k])
                printf("Pages: %d\n", shelarr[k][c]);
            else
                printf("Invalid book index\n");
        }
        else if (queryType == 3) {
            // Query 3: Print number of books on shelf 'k'
            printf("Enter shelf index: ");
            scanf("%d", &k);
            printf("Number of books: %d\n", nobookarr[k]);
        }
        else {
            printf("Invalid query type\n");
        }
    }

    return 0;
}
```
Output:
```
Enter number of shelves and queries: 2 5
Enter query type: 1
Enter shelf index and book pages: 0 100
Enter query type: 1
Enter shelf index and book pages: 1 200
Enter query type: 2
Enter shelf index and book index: 0 0
Pages: 100
Enter query type: 3
Enter shelf index: 1
Number of books: 1
Enter query type: 2
Enter shelf index and book index: 1 0
Pages: 200
```
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
```
#include <stdio.h>

int main() {
    int n, sum = 0;

    printf("Enter the number of integers: ");
    scanf("%d", &n);

    int a[n];  // Array to store integers

    printf("Enter %d integers:\n", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    printf("Sum of the integers is: %d\n", sum);

    return 0;
}
```
Output:
```
Enter the number of integers: 5
Enter 5 integers:
10 20 30 40 50
Sum of the integers is: 150
```
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
```
#include <stdio.h>
#include <ctype.h>

int main() {
    char sentence[1000];
    int i = 0, wordCount = 0;
    int inWord = 0;  // Flag to track if we are inside a word

    printf("Enter a sentence:\n");
    fgets(sentence, sizeof(sentence), stdin);

    while (sentence[i] != '\0') {
        if (isspace(sentence[i]) || ispunct(sentence[i])) {
            // If space or punctuation, we are not inside a word
            inWord = 0;
        } else if (inWord == 0) {
            // Start of a new word
            inWord = 1;
            wordCount++;
        }
        i++;
    }

    printf("Number of words: %d\n", wordCount);

    return 0;
}
```
Output:
```
Enter a sentence:
Hello, how are you doing today?
Number of words: 6
```


Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
