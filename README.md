# EX-16-LEFT-SHIFT-OPERATION
## AIM
To write a C Program to perform the basic left shift operation for 44 integer number with 3 shifts.

## ALGORITHM
1.	Start the program.
2.	Assign values of a and b as 44 and 3.
3.	Use left shift operator (<<) and shift the value of a three times.
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int num = 44;  // The number to shift
    int shifts = 3;  // Number of shifts

    // Perform left shift operation
    int result = num << shifts;

    // Print the result
    printf("Original number: %d\n", num);
    printf("Number after left shifting by %d positions: %d\n", shifts, result);

    return 0;
}

```
## OUTPUT
![image](https://github.com/user-attachments/assets/5ffa9ce6-51b6-48b7-9ffd-3789995ab048)

## RESULT
Thus the program to perform the basic left shift operation for 44 integer number with 3 shifts has been executed successfully.




 
 


# EX-17-TWO-NUMBERS-ARE-EQUAL-OR-NOT


## AIM

Write a C Program to check whether the two numbers are equal or not using simple if statement.

## ALGORITHM

1.	Start the program.
2.	Read two numbers.
3.	If first number is equal to second number, display both are equal.
4.	Otherwise display both are not equal.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>

int main() {
    int num1, num2;

    // Input two numbers
    printf("Enter the first number: ");
    scanf("%d", &num1);

    printf("Enter the second number: ");
    scanf("%d", &num2);

    // Check if the numbers are equal
    if (num1 == num2) {
        printf("The numbers are equal.\n");
    } else {
        printf("The numbers are not equal.\n");
    }

    return 0;
}

```

## OUTPUT
   ![image](https://github.com/user-attachments/assets/976c381c-ea94-4d47-831a-3d64da53a5d3)
        
## RESULT

Thus the program to check whether the two numbers are equal or not using simple if statement has been executed successfully
 
 


# EX-18-STRING-LOWERCASE-CONVERSION
## AIM
Write a C Program to convert the given string into lowercase.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using tolower( ) function convert the given string into its lowercase.
4.	Display the result.
5.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <ctype.h>  // For the tolower() function

int main() {
    char str[100];

    // Input the string
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);  // Read the input string

    // Convert each character to lowercase
    for (int i = 0; str[i] != '\0'; i++) {
        str[i] = tolower(str[i]);  // Convert the character to lowercase
    }

    // Print the resulting lowercase string
    printf("Lowercase string: %s\n", str);

    return 0;
}

```
## OUTPUT
![image](https://github.com/user-attachments/assets/2e989db6-9ee1-465f-9d9b-d5ad4795f1fa)


## RESULT
Thus the program to convert the given string into lowercase has been executed successfully
 
 


# EX-19-COUNT-OF-WORDS-IN-A-STRING
## AIM
Write a C Program to count the total number of words in a given string using do While loop.

## ALGORITHM
1.	Start the program.
2.	Read a string variable.
3.	Using for loop, inspect the string character by character.
4.	Whenever a space is encountered increment count by 1.
5.	Display the result.
6.	Stop the program.

## PROGRAM
```
#include <stdio.h>
#include <ctype.h>  // For checking characters like whitespace

int main() {
    char str[100];
    int wordCount = 0;
    int i = 0;

    // Input the string
    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);  // Read the input string including spaces

    // Use a do-while loop to count words
    do {
        // Skip any spaces
        while (str[i] == ' ' || str[i] == '\t' || str[i] == '\n') {
            i++;  // Move to the next character if it's a space
        }

        // If the current character is not a space, it means a word starts here
        if (str[i] != '\0' && str[i] != ' ' && str[i] != '\t' && str[i] != '\n') {
            wordCount++;  // Increment the word count
            // Move to the next characters until a space or end of string is encountered
            while (str[i] != ' ' && str[i] != '\t' && str[i] != '\n' && str[i] != '\0') {
                i++;
            }
        } else {
            i++;  // Move to the next character
        }
    } while (str[i] != '\0');  // Continue the loop until the end of the string

    // Output the result
    printf("Total number of words: %d\n", wordCount);

    return 0;
}

```
## OUTPUT
![image](https://github.com/user-attachments/assets/6225e700-6c35-4527-aa48-7bf5e559b71a)


## RESULT
Thus the program to count the total number of words in a given string using do While loop has been executed successfully
 
 


# EX  -20 -COMPARING TWO STRINGS
## AIM
write a Program to compare two strings without using strcmp().
## ALGORITHM
Step 1: Start the program.
Step 2: Declare two character arrays c1 and c2 of size 100 to store the strings. Also, declare an integer variable
             flag and initialize it to 0, and i for indexing.      
Step 3: Read the first string c1 using scanf("%[^\n]", c1); — this reads input until a newline is encountered 
            (i.e., can include spaces).
Step 4: Read the second string c2 using scanf("%s", c2); — this reads input until a space or newline (i.e., no 
            spaces in the second string).
Step 5: Start comparing characters of both strings from index i = 0.
Step 6: Repeat the following while neither c1[i] nor c2[i] is '\0' (i.e., end of string):
•	If c1[i] is not equal to c2[i], set flag = 1.
•	Increment i by 1.
Step 7: After the loop, check the value of flag:
•	If flag == 0, print "strings are same".
•	Otherwise, print "strings are not same".
Step 8: End the program.

## PROGRAM
```
#include <stdio.h>

int compareStrings(char str1[], char str2[]) {
    int i = 0;

    // Loop to compare each character of both strings
    while (str1[i] != '\0' && str2[i] != '\0') {
        if (str1[i] != str2[i]) {
            return 0;  // Strings are not equal if characters don't match
        }
        i++;
    }

    // If both strings are of the same length and have the same characters
    if (str1[i] == '\0' && str2[i] == '\0') {
        return 1;  // Strings are equal
    } else {
        return 0;  // Strings are not equal if one is longer than the other
    }
}

int main() {
    char str1[100], str2[100];

    // Input two strings
    printf("Enter the first string: ");
    fgets(str1, sizeof(str1), stdin);

    printf("Enter the second string: ");
    fgets(str2, sizeof(str2), stdin);

    // Remove the trailing newline character added by fgets
    str1[strcspn(str1, "\n")] = '\0';
    str2[strcspn(str2, "\n")] = '\0';

    // Compare the strings using the compareStrings function
    if (compareStrings(str1, str2)) {
        printf("The strings are equal.\n");
    } else {
        printf("The strings are not equal.\n");
    }

    return 0;
}

```

## OUTPUT
 ![image](https://github.com/user-attachments/assets/fb33cc0a-2654-40c7-9c40-f631f5539549)


## RESULT
Thus the C Program to compare two strings without using strcmp() has been executed successfully.

