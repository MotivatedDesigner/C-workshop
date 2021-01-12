```c
/******************************************************************************

This program will get user info & display it

Author   : Ayoub Elmendoub
Version  : 1.0
Language : C
License  : MIT
*******************************************************************************/
//Ask user info & store user input
#define ASK(X,PLACEHOLDER) printf("Please enter your " #X " :"); \
               fgets(PLACEHOLDER, sizeof(PLACEHOLDER), stdin);

int main ()
{
  //Variables to store user info
  char firstName[20], lastName[20], gender[10], age[10], phoneNumber[20];
  //Getting user info
  ASK (first name, firstName);
  ASK (last name, lastName);
  ASK (gender, gender);
  ASK (age, age);
  ASK (phone number, phoneNumber);
  //Printing user info    
  printf ("\nFirst name: %s", firstName);
  printf ("Last name: %s", lastName);
  printf ("Gender: %s", gender);
  printf ("Age: %s", age);
  printf ("Phone number: %s", phoneNumber);
  return 0;
}
```
