```c
/******************************************************************************

This program will find the root of a polynomial of degree 2 ax^2+bx+c

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/
#include <stdio.h>
#include <math.h>

//change stdio color output
#define ANSI_COLOR_RESET "\x1b[0m"
#define ANSI_COLOR_RED "\x1b[31m"

//Get input from the user & handle character as input
#define ASK_NUMBER(X)  while(1){\
                        printf(" Please enter the value of "#X": ");\
                        if (scanf("%f", &X) != 1){\
                        printf(ANSI_COLOR_RED" Please enter a valid number\n"ANSI_COLOR_RESET);\
                        while (getchar() != '\n');} else break; }\
                        
int main()
{
    float a,b,c;
    //Get user input
    ASK_NUMBER(a);
    ASK_NUMBER(b);
    ASK_NUMBER(c);
    //Calculate delta b^2-4ac
    float delta = pow(b,2)-(4*a*c);
    
    if(delta == 0) printf(" There are one unique solution x = %0.3f", -b/(2*a));
    else if(delta > 0) 
        printf(" There are two real solutions x1 = %0.3f, x2 = %0.3f", (-b+sqrt(delta))/(2*a), (-b-sqrt(delta))/(2*a));
    else if(delta < 0)
        printf(" There are two complex solutions x1 = %0.3f + %0.3f i, x2 = %0.3f - %0.3f i",-b/(2*a),sqrt(-delta)/(2*a), -b/(2*a),sqrt(-delta)/(2*a));

    return 0;
}
```
