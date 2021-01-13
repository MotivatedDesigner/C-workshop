[Conditional calculator](#Conditional)

[Switch case calculator](#Switch)

# Conditional

```c
/******************************************************************************

A simple conditioned calculator

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/
#include <stdio.h>

//Used to desplay error color in red
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"
#define ANSI_COLOR_BLUE "\x1b[34m"

//Get user input & Handle character as an input case
#define ASK_NUM(X) while(1){\
        printf(" Please enter the value of "#X": ");\
        if (scanf("%f",&X)  != 1){\
            printf(ANSI_COLOR_RED " This is not a valid integer\n" ANSI_COLOR_RESET);\
            while (getchar() != '\n');}\
        else break;}
int main()
{
    char operationType,choice;
    float a,b;
    do
    {
        //Ask for user input ( a & b )
        ASK_NUM(a);
        ASK_NUM(b);
        
        //Print the size of a & b (bytes && hexadecimal)
        int size = sizeof(float);
        printf("\n The size of a & b is: %d Bytes (%#04x)\n",size,size);
        
        //get user operation choice
        printf(ANSI_COLOR_BLUE);
        printf("  . '+' for a + b\n");
        printf("  . '-' for a - b\n");
        printf("  . '*' for a * b\n");
        printf("  . '/' for a / b\n");
        printf("  . '%%' for a %% b\n");
        printf(" Please choose the type of operation you wanna perform: ");
        scanf(" %c",&operationType);
        printf(ANSI_COLOR_RESET);
        
        //Handle user choice & output the result if the choice is valid
        if( operationType == '+') printf(" a + b = %0.3f\n", a+b);
        else if( operationType == '-') printf(" a - b = %0.3f\n", a-b);
        else if( operationType == '*') printf(" a * b = %0.3f\n", a*b);
        else if( operationType == '/')
        {
            if(b != 0) printf(" a / b = %0.3f\n", a/b);
            else printf(ANSI_COLOR_RED " You can't devide by 0\n" ANSI_COLOR_RESET);
        }
        else if( operationType == '%')
        {
            if(b != 0) printf(" a %% b = %d\n", (int)a%(int)b);
            else printf(ANSI_COLOR_RED " You can't devide by 0\n" ANSI_COLOR_RESET);
        }
        else printf(ANSI_COLOR_RED " Wrong choice\n" ANSI_COLOR_RESET);
        
        //Ask the user choice to continue using the calculator
        printf(" Do u wanna continue using this program (y): ");
        scanf(" %c",&choice);
    }while(choice == 'y');
    
    return 0;
}
```
# Switch

```c
/******************************************************************************

A simple conditioned calculator

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/
#include <stdio.h>

//Used to desplay error color in red
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"
#define ANSI_COLOR_BLUE "\x1b[34m"

//Get user input & Handle character as an input case
#define ASK_NUM(X) while(1){\
        printf(" Please enter the value of "#X": ");\
        if (scanf("%f",&X)  != 1){\
            printf(ANSI_COLOR_RED " This is not a valid integer\n" ANSI_COLOR_RESET);\
            while (getchar() != '\n');}\
        else break;}
int main()
{
    char operationType,choice;
    float a,b;
    do
    {
        //Ask for user input ( a & b )
        ASK_NUM(a);
        ASK_NUM(b);
        
        //Print the size of a & b (bytes && hexadecimal)
        int size = sizeof(float);
        printf("\n The size of a & b is: %d Bytes (%#04x)\n",size,size);
        
        //get user operation choice
        printf(ANSI_COLOR_BLUE);
        printf("  . '+' for a + b\n");
        printf("  . '-' for a - b\n");
        printf("  . '*' for a * b\n");
        printf("  . '/' for a / b\n");
        printf("  . '%%' for a %% b\n");
        printf(" Please choose the type of operation you wanna perform: ");
        scanf(" %c",&operationType);
        printf(ANSI_COLOR_RESET);
        
        //Handle user choice & output the result if the choice is valid
        switch(operationType)
        {
            case '+': printf(" a + b = %0.3f\n", a+b); break;
            case '-': printf(" a - b = %0.3f\n", a-b); break;
            case '*': printf(" a * b = %0.3f\n", a*b); break;
            case '/':
                if(b != 0) printf(" a / b = %0.3f\n", a/b);
                else printf(ANSI_COLOR_RED " You can't devide by 0\n" ANSI_COLOR_RESET);
                break;
            case '%':
                if(b != 0) printf(" a %% b = %d\n", (int)a%(int)b);
                else printf(ANSI_COLOR_RED " You can't devide by 0\n" ANSI_COLOR_RESET);
                break;
            default: printf(ANSI_COLOR_RED " Wrong choice\n" ANSI_COLOR_RESET); break;
        }

        //Ask the user choice to continue using the calculator
        printf(" Do u wanna continue using this program (y): ");
        scanf(" %c",&choice);
        
    }while(choice == 'y');
    
    return 0;
}
```
