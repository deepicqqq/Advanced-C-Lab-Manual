## NAME : DEEPIKA P
## REGISTER NO: 212223240024

## EXP NO:21 C PROGRAM TO CREATE A FUNCTION TO FIND THE GREATEST NUMBER
## Aim:
To write a C program to create a function to find the greatest number

## Algorithm:
1.	Include the necessary header #include <stdio.h>.
2.	Use a series of if and else if statements to compare the values and return the maximum among them.
3.	Declare variables n1, n2, n3, n4, and greater to store user input and the result.
4.	Use scanf to take four integers as input.
5.	Call the max_of_four function with the input integers and store the result in the greater variable
 
## Program:
#include <stdio.h>\
int max_of_four(int a, int b, int c, int d) {\
    int max = a;

    if (b > max)
        max = b;
    if (c > max)
        max = c;
    if (d > max)
        max = d;

    return max;
}

int main() {
    int n1, n2, n3, n4, greater;\
    printf("Enter four integers: ");\
    scanf("%d %d %d %d", &n1, &n2, &n3, &n4);\
    greater = max_of_four(n1, n2, n3, n4);\
    printf("The greatest number is: %d\n", greater);

    return 0;
}

## Output:
![Screenshot 2025-05-13 161943](https://github.com/user-attachments/assets/f8a68057-55c2-4d68-8b2a-5bd4f0ed8345)


## Result:
Thus, the program  that create a function to find the greatest number is verified successfully.


 
## EXP NO:22 C PROGRAM TO PRINT THE MAXIMUM VALUES FOR THE AND, OR AND  XOR COMPARISONS
## Aim:
To write a C program to print the maximum values for the AND, OR and XOR comparisons

## Algorithm:
1.	Define a function calculate_the_max that takes two integers n and k as parameters.
2.	Declare variables a, o, and x to store the maximum values for AND, OR, and XOR operations, respectively.
3.	Use nested loops to iterate through pairs of integers (i, j) from 1 to n.
4.	Within the loops, check conditions for AND, OR, and XOR operations and update the corresponding maximum values (a, o, x).
5.	Declare variables n and k to store user input.
6.	Use scanf to take two integers as input.
7.	Call the calculate_the_max function with input values.
 
## Program:
#include <stdio.h>\
void calculate_the_max(int n, int k) {\
    int a = 0, o = 0, x = 0;

    for (int i = 1; i <= n; i++) {
        for (int j = i + 1; j <= n; j++) {
            int and_val = i & j;
            int or_val = i | j;
            int xor_val = i ^ j;

            if (and_val < k && and_val > a)
                a = and_val;
            if (or_val < k && or_val > o)
                o = or_val;
            if (xor_val < k && xor_val > x)
                x = xor_val;
        }
    }

    printf("Maximum AND value less than %d: %d\n", k, a);
    printf("Maximum OR value less than %d: %d\n", k, o);
    printf("Maximum XOR value less than %d: %d\n", k, x);
}

int main() {
    int n, k;

    // Input from user
    printf("Enter the values for n and k: ");
    scanf("%d %d", &n, &k);

    // Function call
    calculate_the_max(n, k);

    return 0;
}


## Output:
![Screenshot 2025-05-13 162128](https://github.com/user-attachments/assets/30ed8681-9d60-4bca-b005-e1e6d91a397b)


## Result:
Thus, the program to print the maximum values for the AND, OR and XOR comparisons
is verified successfully.


 
## EXP NO:23 C PROGRAM TO WRITE THE LOGIC FOR THE REQUESTS
## Aim:
To write a C program to write the logic for the requests

## Algorithm:
1.	Declare variables noshel and noque to store the number of shelves and the number of queries, respectively.
2.	Use scanf to take two integers as input for the number of shelves and queries.
3.	Declare a 2D array shelarr to represent shelves and books, and an array nobookarr to store the number of books on each shelf.
4.	Declare variables k and c to keep track of the book index and the total number of books.
5.	Use a for loop to iterate over the queries.
 
## Program:
#include <stdio.h>\
#include <stdlib.h>

int main() {\
    int noshel, noque;
    
    // Step 1 and 2: Read number of shelves and number of queries
    printf("Enter number of shelves and queries: ");
    scanf("%d %d", &noshel, &noque);

    // Step 3: Allocate arrays
    int **shelarr = (int **)malloc(noshel * sizeof(int *)); // 2D array for shelves
    int *nobookarr = (int *)calloc(noshel, sizeof(int)); // Array to store number of books on each shelf

    for (int i = 0; i < noshel; i++) {
        shelarr[i] = NULL;
    }

    // Step 5: Loop through each query
    for (int i = 0; i < noque; i++) {
        int type, shelf, book;
        scanf("%d", &type);

        if (type == 1) {
            // Add book with pages = book to shelf
            scanf("%d %d", &shelf, &book);
            nobookarr[shelf]++;
            shelarr[shelf] = (int *)realloc(shelarr[shelf], nobookarr[shelf] * sizeof(int));
            shelarr[shelf][nobookarr[shelf] - 1] = book;
        } else if (type == 2) {
            // Print number of pages in book of given shelf
            int book_idx;
            scanf("%d %d", &shelf, &book_idx);
            printf("%d\n", shelarr[shelf][book_idx]);
        } else if (type == 3) {
            // Print total number of books on given shelf
            scanf("%d", &shelf);
            printf("%d\n", nobookarr[shelf]);
        }
    }

    // Free allocated memory
    for (int i = 0; i < noshel; i++) {
        free(shelarr[i]);
    }
    free(shelarr);
    free(nobookarr);

    return 0;
}


## Output:

![Screenshot 2025-05-13 162336](https://github.com/user-attachments/assets/f1e672cf-5786-451b-b5f1-f761209d6ee9)


## Result:
Thus, the program to write the logic for the requests is verified successfully.


 
## EXP NO:24 C PROGRAM PRINT THE SUM OF THE INTEGERS IN THE ARRAY.
## Aim:
To write a C program print the sum of the integers in the array.

## Algorithm:
1.	Declare a variable n to store the number of integers.
2.	Use scanf to take an integer n as input.
3.	Declare an array a of size n to store the integers.
4.	Declare a variable sum and initialize it to zero.
5.	Use a for loop to iterate n times:
6.	Use scanf to input each integer and add it to the sum.
7.	Print the final sum using printf.

## Program:
#include <stdio.h>

int main() {
    int n;

    // Step 1 & 2: Input the number of integers
    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int a[n], sum = 0;

    // Step 5 & 6: Input the elements and calculate sum
    printf("Enter %d integers: ", n);
    for (int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
        sum += a[i];
    }

    // Step 7: Print the sum
    printf("Sum of the integers: %d\n", sum);

    return 0;
}

## Output:


 ![Screenshot 2025-05-13 162641](https://github.com/user-attachments/assets/970b0f8d-9c08-4890-ade7-bc14d07c8153)



## Result:
Thus, the program prints the sum of the integers in the array is verified successfully.


 
## EXP NO 25: C PROGRAM TO COUNT THE NUMBER OF WORDS IN A      SENTENCE

## Aim:

To write a C program that counts the number of words in a given sentence.

## Algorithm:

1.	Input the sentence: Take a sentence from the user.
2.	Initialize a counter variable: This will keep track of the number of words.
3.	Process each character of the sentence:
o	Iterate through the sentence, checking each character.
o	If a character is not a space, it may belong to a word. If it's the first non-space character after a space or at the start, increment the word count.
4.	Handle spaces and punctuation: Skip over spaces, punctuation marks, and consider each word as a sequence of characters separated by spaces.
5.	Display the result: After processing the sentence, output the total word count.



## Program:
#include <stdio.h>\
#include <string.h>\
#include <ctype.h>

int main() {
    char sentence[1000];\
    int i, word_count = 0;\
    int in_word = 0;

    // Step 1: Input the sentence
    printf("Enter a sentence: ");
    fgets(sentence, sizeof(sentence), stdin);

    // Step 3: Iterate through the sentence
    for (i = 0; sentence[i] != '\0'; i++) {
        if (!isspace(sentence[i])) {
            if (in_word == 0) {
                word_count++;
                in_word = 1;
            }
        } else {
            in_word = 0;
        }
    }

    // Step 5: Output the result
    printf("Number of words in the sentence: %d\n", word_count);

    return 0;
}


## Output:

![Screenshot 2025-05-13 162811](https://github.com/user-attachments/assets/90361468-ffe4-4426-aed6-1f432f57099d)

## Result:

Thus, the program that counts the number of words in a given sentence is verified 
successfully.
