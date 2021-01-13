```c
/******************************************************************************

This program display table of multiplication from 1 to 10 of an integer entered by the user

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/

#include <stdio.h>
#include <math.h>

//change stdio outpu color
#define RED "\x1b[31m"
#define GREEN "\x1b[32m"
#define RESET "\x1b[0m"

//Get user input & Handle character as an input case
#define ASK_NUMBER(X) while(1){\
        printf(" Please enter the value of "#X": ");\
        if (scanf("%d",&X)  != 1){\
            printf(RED " This is not a valid number\n" RESET);\
            int c;\
            while ((c = getchar()) != EOF && c != '\n');}\
        else break;}

int main()
{
    //user input
    int n;
    ASK_NUMBER(n);
    
    //loop 1 to 10 - print the table and comute the resulte of n*i
    for (int i = 1; i <= 10 ; i++) {
        printf(GREEN" %d "  RED"X"  GREEN" %d "  RED"=" GREEN" %d\n", n, i, n*i);
    }

    return 0;
}
```
