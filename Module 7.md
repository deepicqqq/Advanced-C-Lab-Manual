## REGISTER NO: 212223240024
## NAME: DEEPIKA P
## EXP NO:1 C PROGRAM FOR ARRAY OF STRUCTURE TO CHECK ELIGIBILITY FOR THE VACCINE.

## Aim:
To write a C program for array of structure to check eligibility for the vaccine person age above 6 years of age.

## Algorithm:
1.	Declare structure eligible with age (integer) and n (character array)
2.	Declare variable e of type eligible
3.	Input age and name using scanf, store in e
4.	If e.age <= 6
-	Print "Vaccine Eligibility: No"
Else
-	Print "Vaccine Eligibility: Yes"
5.	Print details (e.age, e.n)
6.	Return 0
 
## Program:
#include <stdio.h>

// Step 1: Declare structure
struct eligible {
    int age;
    char n[50];
};

int main() {
    // Step 2: Declare array of structure
    int i, num;
    printf("Enter the number of persons: ");
    scanf("%d", &num);
    
    struct eligible e[num]; // Array of structures

    // Step 3: Input data
    for(i = 0; i < num; i++) {
        printf("\nEnter name of person %d: ", i + 1);
        scanf("%s", e[i].n);
        printf("Enter age of person %d: ", i + 1);
        scanf("%d", &e[i].age);
    }

    // Step 4: Check eligibility and print details
    printf("\nVaccine Eligibility Check:\n");
    for(i = 0; i < num; i++) {
        printf("\nName: %s\n", e[i].n);
        printf("Age: %d\n", e[i].age);
        if(e[i].age <= 6) {
            printf("Vaccine Eligibility: No\n");
        } else {
            printf("Vaccine Eligibility: Yes\n");
        }
    }

    return 0;
}


//type your code here


## Output:

//paste your output here
![Screenshot 2025-04-26 142815](https://github.com/user-attachments/assets/80f28130-3e52-4ef3-b2b1-4597bbb249a8)


## Result:
Thus, the program is verified successfully. 










Output:


//paste your output here











Result:
Thus, the program is verified successfully
 


