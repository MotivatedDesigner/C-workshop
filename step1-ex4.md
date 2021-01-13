```c
/******************************************************************************

This program will calculate theaverage of entered positive numbers & quit when the user enter -1

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/
#include <stdio.h>
//Used to desplay error color in red
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"

//number: from the user, sum: of the entered numbers, counter: of the total numbers entered by the user
int number,sum = 0,counter = 0;
//Prototype
void getUserChoice();

int main(){
    //Ask for user choice
    printf(" Enter a positive number (will be added to the average)");
    printf("\n Enter -1 (to get the answer)\n");
    while(1)
    {
        //Get user choice (this will be stored in number)
        getUserChoice();
        if(number > 0)
        {
            counter++;
            sum += number;
        }
        if(number == -1)
        {
            printf("The average of these %d integers is %f.",counter,(float)sum/counter);
            break;
        }
    }
    return 0;
}

void getUserChoice(){
 while(1)
    {
        printf(" Please enter your choice (+# || -1): ");
        if ( scanf("%d",&number) != 1 || number < -1 )
        {
            printf(ANSI_COLOR_RED " This is not a valid input\n" ANSI_COLOR_RESET);
            int c;
            while ((c = getchar()) != EOF && c != '\n');
        }
        else break;
    }
}
```
