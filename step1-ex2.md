```C
#include <stdio.h>
//Used to desplay error color in red
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"
//Handle character as an input
#define ASK_INT(X) while(1){\
        printf("\n Please enter the value of "#X": ");\
        if (scanf("%d",&X)  != 1){\
            printf(ANSI_COLOR_RED " This is not a valid integer" ANSI_COLOR_RESET);\
            int c;\
            while ((c = getchar()) != EOF && c != '\n');}\
        else break;}
        
int main(){
    int a,b;
    //Getting user inputs
    ASK_INT(a);
    ASK_INT(b);
    //Printing ansears
    printf("\n  . a + b = %d",a + b);
    printf("\n  . a - b = %d",a - b);
    printf("\n  . a * b = %d",a * b);
    //Handlling division by 0
    if(b != 0)
    {
        printf("\n  . a / b = %d",a / b);
        printf("\n  . a % b = %d",a % b);
    }
    else
        printf("\n  . Dividing by 0 is undefined !!!");
    return 0;
}
```