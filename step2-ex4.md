[Using recursion method](#Recursion)

[Using iterative method](#Iteration)


# Recursion

```c
/******************************************************************************

This program calculate the GCD of two integers entered by the user (Recurcive)

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
        
//Recurcive implementation of gcd
int gcd(int a,int b){
    
    //Used to count the steps taken by the algorithm
    static int counter;
    
    //quotion & reminder
    int r = a%b;
    int q = a/b;
    
    //Base case (reminder is null)
    if(r == 0) return b;
    
    //Recursive part
    counter++;
    printf(" Step %d: %d = %d*%d + %d\n",counter, a, b, q, r);
    return gcd(b,r);
}

int main()
{
    int a,b;
    printf("-- gcd(a,b) --\n");
    ASK_NUMBER(a);
    ASK_NUMBER(b);
    printf(" gcd(%d,%d) = %d",a ,b, gcd(a,b));
    return 0;
}
```

# Iteration

```c
/******************************************************************************

This program calculate the GCD of two integers entered by the user (Recurcive)

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
        
int main()
{
    //user input + quotion & reminder
    int a,b,q,r;
    printf("-- gcd(a,b) --\n");
    ASK_NUMBER(a);
    ASK_NUMBER(b);
    
    //preOutput the GCD
    printf(" gcd(%d,%d) = ",a ,b);
    
    //Calculating the GCD
    while(1)
    {
        //calculate the quotion & the reminder
        q = a/b;
        r = a%b;
        
        //Base case to break the loop
        if(r == 0) break;
        
        //otherwise asign (b to a) & (r to b) & loop again
        a = b;
        b = r;
    }
    
    //postOutput the GCD
    printf("%d",b);
    return 0;
}
```
