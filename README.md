# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
# Date : 29/12/2025
# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:
~~~
#include <stdio.h>

int main() {
    int decimal, binary = 0, place = 1;
    
    printf("Enter a decimal number: ");
    scanf("%d", &decimal);
    
    int temp = decimal;
    
    while(temp > 0) {
        binary = binary + (temp % 2) * place;
        temp = temp / 2;
        place = place * 10;
    }
    
    printf("Binary equivalent: %d\n", binary);
    
    return 0;
}
~~~
# Output:
<img width="473" height="234" alt="image" src="https://github.com/user-attachments/assets/89cf09b5-b5f6-44a3-9bda-9a57c8849928" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
# Date : 29/12/2025
# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row `i` from `0` to `m−1`:
- **Step 7.1:** Set `min` as the first element of the row.  
- **Step 7.2:** Scan the row to find its minimum element and store its position in `pos[0]`.  
- **Step 7.3:** Let `j` be the column of this minimum element.  
- **Step 7.4:** Set `max` as the first element of column `j`.  
- **Step 7.5:** Scan column `j` to find its maximum element and store its position in `pos[1]`.  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If `min == max` **and their positions match**, then the element is a **saddle point**.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:
~~~
#include <stdio.h>

int main() {
    int rows, cols;
    
    printf("Enter number of rows: ");
    scanf("%d", &rows);
    printf("Enter number of columns: ");
    scanf("%d", &cols);
    
    int matrix[rows][cols];
    
    printf("Enter matrix elements:\n");
    for(int i = 0; i < rows; i++) {
        printf("Row %d: ", i + 1);
        for(int j = 0; j < cols; j++) {
            scanf("%d", &matrix[i][j]);
        }
    }
    
    printf("\nThe matrix:\n");
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            printf("%4d", matrix[i][j]);
        }
        printf("\n");
    }
    
    int saddleFound = 0;
    
    for(int i = 0; i < rows; i++) {
        for(int j = 0; j < cols; j++) {
            int current = matrix[i][j];
            int isMinInRow = 1;
            int isMaxInCol = 1;
            
            for(int c = 0; c < cols; c++) {
                if(matrix[i][c] < current) {
                    isMinInRow = 0;
                    break;
                }
            }
            
            for(int r = 0; r < rows; r++) {
                if(matrix[r][j] > current) {
                    isMaxInCol = 0;
                    break;
                }
            }
            
            if(isMinInRow && isMaxInCol) {
                printf("\nSaddle Point Found!\n");
                printf("Element: %d\n", current);
                printf("Position: (%d, %d)\n", i + 1, j + 1);
                saddleFound = 1;
            }
        }
    }
    
    if(!saddleFound) {
        printf("\nNo saddle point exists.\n");
    }
    
    return 0;
}
~~~
# Output:
<img width="449" height="827" alt="image" src="https://github.com/user-attachments/assets/16c7aa91-d3cc-40af-aa1f-cb3d9abd8c7a" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
# Date : 29/12/2025
# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: `s` to store the input string and `d` to store the reversed string.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]s", s);`
### Step 5: 
  Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.
### Step 6: 
  Initialize a counter `j` for the reversed string.
### Step 7: 
  Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string `d` with the null character `'\0'`.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:
~~~
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int length, i;
    
    printf("Enter a string: ");
    fgets(str, 100, stdin);
    
    str[strcspn(str, "\n")] = 0;
    
    length = strlen(str);
    
    printf("Original string: %s\n", str);
    
    for(i = 0; i < length / 2; i++) {
        char temp = str[i];
        str[i] = str[length - 1 - i];
        str[length - 1 - i] = temp;
    }
    
    printf("Reversed string: %s\n", str);
    
    return 0;
}
~~~
# Output:
<img width="449" height="252" alt="image" src="https://github.com/user-attachments/assets/74e9fd02-f75d-41ed-9827-51cbe0008e82" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
# Date : 29/12/2035
# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]", s);`
### Step 5: 
  Calculate the length of the string using `strlen(s)` and store it in `n`.
### Step 6: 
 For each character `s[i]` in the string (from `i = 0` to `n - 1`):
 - If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  
  - Initialize `count = 0`.  
  - Loop through the string again and increment `count` for every occurrence of `s[i]`.  
  - Print `s[i]` and its count.  
  - Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:
~~~
#include <stdio.h>
#include <string.h>

int main() {
    char str[100];
    int freq[256] = {0};
    int i;
    
    printf("Enter a string: ");
    fgets(str, 100, stdin);
    
    str[strcspn(str, "\n")] = 0;
    
    for(i = 0; str[i] != '\0'; i++) {
        freq[(int)str[i]]++;
    }
    
    printf("\nCharacter frequencies:\n");
    
    for(i = 0; i < 256; i++) {
        if(freq[i] != 0) {
            printf("'%c' : %d\n", i, freq[i]);
        }
    }
    
    return 0;
}
~~~
# Output:
<img width="462" height="478" alt="image" src="https://github.com/user-attachments/assets/a16df8ab-a597-4c76-a51d-4f1bb2fd1be4" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Date : 29/12/2025
# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `str` to store the input string and a 2D array `words` to store individual words.
### Step 4: 
  Read the input string using `scanf("%[^\n]s", str);`
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to `'\0'`.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:
~~~
#include <stdio.h>
#include <string.h>

int main() {
    char str[500];
    char result[500] = "";
    char tempWord[50];
    char seenWords[100][50];
    int seenCount = 0;
    int i = 0, j = 0;
    
    printf("Enter a string: ");
    fgets(str, 500, stdin);
    
    str[strcspn(str, "\n")] = '\0';
    
    while(str[i] != '\0') {
        j = 0;
        
        while(str[i] != '\0' && str[i] != ' ') {
            tempWord[j] = str[i];
            j++;
            i++;
        }
        tempWord[j] = '\0';
        
        if(j > 0) {
            int isDuplicate = 0;
            
            for(int k = 0; k < seenCount; k++) {
                if(strcmp(tempWord, seenWords[k]) == 0) {
                    isDuplicate = 1;
                    break;
                }
            }
            
            if(!isDuplicate) {
                strcpy(seenWords[seenCount], tempWord);
                seenCount++;
                
                if(strlen(result) > 0) {
                    strcat(result, " ");
                }
                strcat(result, tempWord);
            }
        }
        
        if(str[i] == ' ') {
            i++;
        }
    }
    
    printf("\nString without duplicate words:\n%s\n", result);
    
    return 0;
}
~~~
# Output:

<img width="454" height="303" alt="image" src="https://github.com/user-attachments/assets/49240350-e4be-461e-93dd-c7fa8f1ecce5" />

# Result: 
 Thus, the program was implemented and executed successfully, and the required output was obtained.
 Thus, the program was implemented and executed successfully, and the required output was obtained.

