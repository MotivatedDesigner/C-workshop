### The diffrence between [ int main() & int main(int argc,char **argv[]) ], is that the last one can use arguments passed from the user at run-time
### Example is this code that calculate the nth fibonacci term with three diffrent methods specifyed with an option entered by the user & show the result + execution time

```c
/*********************************************************************************************************

    This program calculate the nth fibonacci term using three methods (user argument)
    m: with memorization, w: without any optimization t:Compiler Tail recursion optimization

    Author   : Ayoub Elmendoub
    Version  : 1.0
    Language : C
    License  : MIT

**********************************************************************************************************/

#include <stdio.h>
#include <stdlib.h>
//change stdio color output
#define ANSI_COLOR_RESET "\x1b[0m"
#define ANSI_COLOR_RED "\x1b[31m"
#define ANSI_COLOR_YELLOW "\x1b[33m"

//Get input from and handle characters as inputs
#define ASK_NUMBER(X)  while(1){\
                        printf(" Please enter the value of "#X": ");\
                        if (scanf("%d", &X) != 1){\
                        printf(ANSI_COLOR_RED" Please enter a valid number\n"ANSI_COLOR_RESET);\
                        while (getchar() != '\n');} else break; }
                        
//To measure time of execution
#include <time.h>
clock_t start, end;
double cpu_time_used;

//Prototypes
int fib(int n);
int fibMemory(int n,int *f);
int fibTail(int n, int a, int b);

int main(int argc,char * argv[])
{
    //Handling user arguments
    char option;
    int n;
    
    if(argc == 1) option = 'w';
    else if(argc == 2)
    { 
        option = (char)*argv[1];
        if(option == 'w' || option == 'm' || option == 't') 
        {   ASK_NUMBER(n);  }
        else
        {
            //Wrong option
            printf(ANSI_COLOR_RED"Wrong option"ANSI_COLOR_RESET);
            printf(ANSI_COLOR_YELLOW" Please try again with (w || m || t) as argument"ANSI_COLOR_RESET);
            return -1;
        }
    }
    else {
        printf(ANSI_COLOR_RED" Too many arguments !!!"ANSI_COLOR_RESET);
        printf(ANSI_COLOR_YELLOW" Please try again with (w || m || t) as argument"ANSI_COLOR_RESET);
        return -2;
    }
    
    //Switch for user option
    switch(option)
    {
         //Default without optimization
        case 'w':
            start = clock();
            printf("%d",fib(n));
            end = clock();
            break;
         //With memorization
        case 'm':
            start = clock();
            //Allocate memory for memorized terms & initialize to -1
            int *f = malloc((n+1) * sizeof(int)); 
            for (int i = 0; i <= n; i++) f[i]=-1;
            //Do the work
            printf("%d",fibMemory(n,f));
            //Free allocated memory
            free(f);
            end = clock();
            break;
         //with Compiler optimization (Tail recursion)
        case 't':
            start = clock();
            printf("%d",fibTail(n,0,1));
            end = clock();
            break;
    }
    
    //Calculate & show the time of execution
    cpu_time_used = ((double) (end - start)) / CLOCKS_PER_SEC;
    printf("\n It takes %lf to execute",cpu_time_used);

}

//Normal fib
int fib(int n){
    
    if(n < 2) return n;
    return fib(n-1)+fib(n-2);
    
}
//Tail recursion
int fibTail(int n,int a,int b){
    
    if(n == 0) return a;
    if(n == 1) return b;
    return fibTail(n-1,b,a+b);
    
}
//Dynamic Programin
int fibMemory(int n,int *f){
    
    if(n < 2) return n;
    if(f[n] != -1) return f[n];
    return f[n] = fib(n-1)+fib(n-2);
    
}

```
