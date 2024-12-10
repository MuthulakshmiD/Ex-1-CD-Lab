# Ex-1 IMPLEMENTATION-OF-SYMBOL-TABLE
# AIM :
## To write a C program to implement a symbol table.
# ALGORITHM
1.	Start the program.
2.	Get the input from the user with the terminating symbol ‘$’.
3.	Allocate memory for the variable by dynamic memory allocation function.
4.	If the next character of the symbol is an operator then only the memory is allocated.
5.	While reading, the input symbol is inserted into symbol table along with its memory address.
6.	The steps are repeated till ‘$’ is reached.
7.	To reach a variable, enter the variable to be searched and symbol table has been checked for corresponding variable, the variable along with its address is displayed as result.
8.	Stop the program. 
# PROGRAM
```
#include <stdio.h>
#include <stdlib.h>
#include <ctype.h>

int main() {
    char b[15], d[15], c, srch;
    void *add[5];
    int i = 0, x = 0, flag = 0;

    // Input Expression
    printf("Enter the Expression terminated by $: ");
    while ((c = getchar()) != '$' && i < 15) {
        b[i++] = c;
    }

    // Display Input Expression
    printf("Given Expression: ");
    for (int j = 0; j < i; j++) {
        printf("%c", b[j]);
    }
    printf("\nSymbol Table\n");
    printf("Symbol\tAddress\t\tType\n");

    // Create Symbol Table
    for (int j = 0; j < i; j++) {
        if (isalpha(b[j])) {
            add[x] = malloc(sizeof(char)); // Allocate memory
            d[x] = b[j];                  // Store symbol
            printf("%c\t%p\tidentifier\n", b[j], add[x]);
            x++;
        }
    }

    // Search for a Symbol
    printf("\nEnter the symbol to search: ");
    scanf(" %c", &srch);

    for (int j = 0; j < x; j++) {
        if (srch == d[j]) {
            printf("Symbol Found: %c @ address %p\n", srch, add[j]);
            flag = 1;
            break;
        }
    }

    if (!flag) {
        printf("Symbol Not Found\n");
    }

    // Free Allocated Memory
    for (int j = 0; j < x; j++) {
        free(add[j]);
    }
    return 0;
}
//a+b+c$
```
# OUTPUT
![image](https://github.com/user-attachments/assets/e7898a98-ed0e-41ea-8492-787cba924183)
# RESULT
### The program to implement a symbol table is executed and the output is verified.
