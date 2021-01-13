[First method O(n)](#First)

[Second method O(sqrt(n))](#Second)

# First
```c
/******************************************************************************

This program check whether a number is prime or not (first method)

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/

#include <stdio.h>

//change stdio outpu color
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"

//Get user input & Handle character as an input case
#define ASK_NUMBER(X) while(1){\
        printf(" Please enter the value of "#X": ");\
        if (scanf("%d",&X)  != 1){\
            printf(ANSI_COLOR_RED " This is not a valid number\n" ANSI_COLOR_RESET);\
            int c;\
            while ((c = getchar()) != EOF && c != '\n');}\
        else break;}
#define False 0     
#define True !False

typedef int bool;

int main()
{
    bool isPrime = True;
    //user input
    int n;
    ASK_NUMBER(n);
    
    //loop through all elements between 2 & n
    for (int i = 2; i < n; i++) {
        if(n%i == 0)
        {
            printf(" %d is not a prime number",n);
            isPrime = False;
            break;
        }
    }
    if(isPrime) printf(" %d is a prime number",n);
    
    return 0;
}
```

# Second
```c
/******************************************************************************

This program check whether a number is prime or not (second method) O(sqrt(n)) time complexity

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/

#include <stdio.h>
#include <math.h>

//change stdio outpu color
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"

//Get user input & Handle character as an input case
#define ASK_NUMBER(X) while(1){\
        printf(" Please enter the value of "#X": ");\
        if (scanf("%d",&X)  != 1){\
            printf(ANSI_COLOR_RED " This is not a valid number\n" ANSI_COLOR_RESET);\
            int c;\
            while ((c = getchar()) != EOF && c != '\n');}\
        else break;}

int main()
{
    //user input
    int n;
    ASK_NUMBER(n);
    
    float sqrtOf_N = sqrt(n); 
    int i;
    //loop through all elements between 2 & n
    for (i = 2; i < sqrtOf_N ; i++) {
        if(n%i == 0)
        {
            printf(" %d is not a prime number",n);
            break;
        }
    }
    if(i == ceil(sqrtOf_N)) printf(" %d is a prime number",n);
    
    return 0;
}
```
