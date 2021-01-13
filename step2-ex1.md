```c
/******************************************************************************

This program will check if a number is greater than another & print (True || False)

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/
#include <stdio.h>
//Used to desplay error color in red & (Green for True || Red for False)
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"
#define ANSI_COLOR_GREEN "\x1b[32m"
// //Create booleans
// #define FALSE 0
// #define TRUE !FALSE

//Check if a > b & return (1 || 0)
#define MAX(a,b) ( (a)>(b) )

//Format (1 || 0) to (True || False)
#define FORMAT(boolean) boolean ? printf(ANSI_COLOR_GREEN" True") : printf(ANSI_COLOR_RED" False")

//Get user input & Handle character as an input case
#define ASK_NUMBER(X) while(1){\
        printf(" Please enter the value of "#X": ");\
        if (scanf("%f",&X)  != 1){\
            printf(ANSI_COLOR_RED " This is not a valid number\n" ANSI_COLOR_RESET);\
            int c;\
            while ((c = getchar()) != EOF && c != '\n');}\
        else break;}
        
int main()
{
    float a,b;
    //Ask for user input ( a & b )
    ASK_NUMBER(a);
    ASK_NUMBER(b);
    //Check if a is greater than b & format the result to (True || False)
    FORMAT(MAX(a,b));
    return 0;
}
```
