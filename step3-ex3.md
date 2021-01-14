[First method](#First)

[Second method](#Second)

# First

```c
/******************************************************************************

This program display pyramid of stars (first method)

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT

*******************************************************************************/

#include <stdio.h>

int main()
{
    int b=1;
    
    for (int i = 0; i < 50; i++) 
    {
        for (int j = 0; j < 50-i; j++) printf(" ");
        for (int k = 0; k < i+1; k++) printf("*");
        for (int k = 0; k < i; k++) printf("*");
        printf("\n");
    }
    return 0;
}
```
