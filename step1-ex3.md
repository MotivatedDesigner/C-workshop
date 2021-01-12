```c
/******************************************************************************

This program will calculate the diameter, the perimeter and the area of a circle

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/
#include <stdio.h>
#include <math.h>
#define PI 3.14159265359
//Used to desplay error color in red
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_RESET "\x1b[0m"

int main(){
    float r,D,P,A;
    //Getting radius from the user & handling characters as an input
    while(1)
    {
        printf("\n Please enter the radius: ");
        if (scanf("%f",&r)  != 1)
        {
            printf(ANSI_COLOR_RED " This is not a valid number" ANSI_COLOR_RESET);
            int c;
            while ((c = getchar()) != EOF && c != '\n');
        }
        else break;
    }
    printf("A circle of radius %0.3f has a diameter %0.3f,perimeter %0.3f and a surface %0.3f.", r, r*2, PI*r*2, PI*pow(r,2));
    return 0;
}
```
