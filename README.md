Length of the string without using strlen() function
In this article we will be learning about how to work with strings in C programming. This is one of the basic operation on String datatype to count it’s length without using any library functions so that we may understand how does library function eventually work.

length of the string without using strlen
Methods discussed
Method 1: Standard method
Method 2: Using pointers
Method 3: Using Recursion Bottom-up
Method 4: Using recursion top-down
Algorithm:
Let’s look at the algorithm for length of string in C without strlen

Initialize a variable ‘str’ , ‘i’ , ‘length’.
Accept the value using ‘printf’ and ‘scanf’.
Initiate a for loop.
Terminate the loop when null(‘\0’).
Print length.
C code for Length of the string without using strlen() function.
Method 1
Run
#include <stdio.h>
int main()
{
   //Initializing variable.
    char str[100];
    int i,length=0;
    
     //Accepting input.
    printf("Enter a string: \n");
    scanf("%s",str);

     //Initializing for loop.
    for(i=0; str[i]!='\0'; i++)
    {
        length++; //Counting the length.
    }
    
    printf("\nLength of input string: %d",length);
    
     return 0;
}
Output:
Enter a string:
PREPINSTA
Length of input string: 9Enter a string:
Note
The time complexity of this code is O(n) and if you are using the build in function like strlen or length the time complexity will still be same O(n)
Related Pages
Juggling algorithm for array rotation
 
Balanced Parenthesis Problem
 
Toggle each character in a string

Count the number of vowels

Remove the vowels from a String

While loop in C
Method 2 – (Using Pointer)
Initialize a variable ‘str’ , ‘i’ , ‘length’.
Accept the value using ‘printf’ and ‘scanf’.
call the function length_of_string and pass str as a parameter store this in length.
in the function loop over the string and Terminate the loop when null(‘\0’).
Print length.
Run
#include <stdio.h> 
int length_of_string(char* p) {
    int count = 0;

    while (*p != '\0') {
        count++;
        p++;
    }

    return count;
}
int main() {
    char str[100];
    int length;

    printf("Enter any string : ");
    gets(str);
    length = length_of_string(str);

    printf("The length of the given string : %d", length);

    return 0;
}
Output
Enter any string : Prepinsta

The length of the given string : 9
Method 3 – (Using Recursion, bottom-up)
This method uses recursion in C.

We will discuss the method in two ways –

Method 1: Using pointers
Method 2: Sending the next array index location
Method 1	Method 2
Run
// this method uses top down recursion
#include <stdio.h>

int getLen(char* str, int len)   
{
    // if we reach at the end of the string
    if (*str == '\0')
        return len;
        
    // add 1 for current character
    // get the length for rest of the string after current character
    return getLen(str + 1, len + 1);
}
int main()
{
    char str[] = "PrepInsta";
    int i, length = 0;
    
    printf("Len: %d",getLen(str, 0));
    return 0;
}
Output
Len: 9
Method 4 – (Using Recursion, top-down)
This method uses recursion in C.

We will discuss the method in two ways –

Method 1: Using pointers
Method 2: Sending the next array index location
Method 1	Method 2
Run
// This uses bottom up recursive approach
#include <stdio.h>

int getLen(char str[])   
{
    // if we reach at the end of the string
    if (str[0] == '\0')
        return 0;
        
    // add 1 for current character
    // get the length for rest of the string after current character
    return 1 + getLen(str + 1);
}
int main()
{
    char str[] = "PrepInsta";
    int i, length = 0;
    
    printf("Len: %d",getLen(str));
    return 0;
}
Output
Len: 9
