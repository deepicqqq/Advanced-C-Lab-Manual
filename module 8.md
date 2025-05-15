## REGISTER NO: 212223240024
## NAME: DEEPIKA P
## EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
## Aim:
To write a C program print the lowercase English word corresponding to the number
## Algorithm:
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
 
## Program:

// Program to print the lowercase English word corresponding to the number
#include <stdio.h>

int main() {
    int n;

    // Start
    printf("Enter a number: ");
    scanf("%d", &n);

    // Input validation and switch statement
    switch (n) {
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
            printf("Greater than 13\n");
            break;
    }

    // Exit the program
    return 0;
}


## Output:



![Screenshot 2025-04-27 155140](https://github.com/user-attachments/assets/25f26383-89c0-483d-b9be-6e2fe0e2b4e9)


## Result:
Thus, the program is verified successfully
 
## EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
## Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
## Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
## Program:
// Program to print frequency of digits 0 to 3
#include <stdio.h>

int main() {
    char a[50];
    int i, h, c;

    // Input the string
    printf("Enter a string containing digits: ");
    scanf("%s", a);

    // Outer loop for each digit from 0 to 3
    for (h = 0; h <= 3; h++) {
        c = 0; // Initialize counter to 0

        // Loop through each character in the string
        for (i = 0; a[i] != '\0'; i++) {
            if (a[i] == (h + '0')) { // Compare character digits
                c++;
            }
        }

        // Print the count for current digit
        printf("%d ", c);
    }

    // Print remaining counts as 0 for digits 4 to 9
    for (h = 4; h <= 9; h++) {
        printf("0 ");
    }

    return 0;
}


## Output:

![Screenshot 2025-04-27 155311](https://github.com/user-attachments/assets/8ad4b0cf-5a46-4ff5-9822-756cfbed0423)


## Result:
Thus, the program is verified successfully

## EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
## Aim:
To write a C program to print all of its permutations in strict lexicographical order.

## Algorithm:
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
 
## Program:

// Program to print all permutations in strict lexicographical order
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to swap two characters
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}

// Function to sort a string
void sortString(char *str) {
    int i, j, n = strlen(str);
    for (i = 0; i < n-1; i++) {
        for (j = i+1; j < n; j++) {
            if (str[i] > str[j]) {
                swap(&str[i], &str[j]);
            }
        }
    }
}

// Function to find the next lexicographical permutation
int nextPermutation(char *str) {
    int i = strlen(str) - 2;
    while (i >= 0 && str[i] >= str[i+1]) {
        i--;
    }
    if (i < 0) return 0; // Last permutation

    int j = strlen(str) - 1;
    while (str[j] <= str[i]) {
        j--;
    }
    swap(&str[i], &str[j]);

    // Reverse the suffix
    int left = i + 1, right = strlen(str) - 1;
    while (left < right) {
        swap(&str[left], &str[right]);
        left++;
        right--;
    }
    return 1;
}

int main() {
    char *s;
    int n, i;

    // Input
    printf("Enter the string: ");
    s = (char *)malloc(100 * sizeof(char));
    scanf("%s", s);

    // Sort the string initially to start with the smallest lexicographical permutation
    sortString(s);

    // Permutation generation loop
    do {
        printf("%s\n", s);
    } while (nextPermutation(s));

    // Memory deallocation
    free(s);

    return 0;
}



## Output:



![Screenshot 2025-04-27 155444](https://github.com/user-attachments/assets/6070763f-1b5f-4f44-97d6-6ca673f6fe0b)


## Result:
Thus, the program is verified successfully
 
## EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
## Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
## Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
## Program:
// Program to print a pattern of numbers from 1 to n
#include <stdio.h>

int main() {
    int n, i, j, len, min;

    // Step 3: Read the value of n
    printf("Enter the value of n: ");
    scanf("%d", &n);

    // Step 4: Calculate the length of the side of the square matrix
    len = n * 2 - 1;

    // Step 5: Matrix Generation Loop
    for (i = 0; i < len; i++) {
        for (j = 0; j < len; j++) {
            // Step 6: Calculate min as the minimum distance to the borders
            min = (i < j) ? i : j;
            min = (min < len - i - 1) ? min : len - i - 1;
            min = (min < len - j - 1) ? min : len - j - 1;
            
            // Print the number corresponding to the minimum distance from the borders
            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0; // End of program
}






## Output:



![Screenshot 2025-04-27 155655](https://github.com/user-attachments/assets/1199c8fa-5555-40f6-b240-9ec5b64d532d)






## Result:
Thus, the program is verified successfully

## EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

## Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

## Algorithm:

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

## Program:


#include <stdio.h>

// Function to calculate square without parameters
int square() {
    int num;
    
    // Ask the user to input a number
    printf("Enter a number: ");
    scanf("%d", &num);
    
    // Calculate the square of the number
    return num * num; // Return the square of the number
}

int main() {
    int result;

    // Call the square function and store the result
    result = square();
    
    // Display the result
    printf("The square of the number is: %d\n", result);

    return 0; // End of program
}



## Output:

![Screenshot 2025-04-27 155842](https://github.com/user-attachments/assets/3bd7b928-660e-4b13-ae62-8867aa260ef7)


## Result:
Thus, the program is verified successfully



























