# EX 1 Display operator precedence in the infix expression.
## DATE: 23-02-2025
## AIM:
To write a C program to find and display the priority of the operator in the given Postfix expression

## Algorithm
1. Start the program.
2. Define the priority() function to return the priority of operators.
3. Initialize the string containing operators and operands.
4. Loop through each character in the string.
5. For each operator, call the priority() function to determine its priority.
6. Print the operator and its corresponding priority level.
7. End.   

## Program:
```c
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: MUKESH KUMAR S
Register Number: 212223240099
*/

#include <stdio.h>
#include <string.h>

int priority(char x)
{
    if (x == '(')
        return 0;
    if (x == '&' || x == '|')
        return 1;
    if (x == '+' || x == '-')
        return 2;
    if (x == '*' || x == '/' || x == '%')
        return 3;
    if (x == '^')
        return 4;
    else
        return 0;
}

int main()
{
    char ch[100] = "K%L-M*N+(O^P)";
    for (int i = 0; i < strlen(ch); i++)
    {
        if (ch[i] == '%' || ch[i] == '-' || ch[i] == '*' || ch[i] == '+' || ch[i] == '^')
        {
            int j = priority(ch[i]);
            switch (j)
            {
            case 1:
                printf("%c  ----> Lowest Priority\n", ch[i]);
                break;

            case 2:
                printf("%c  ----> Second Lowest Priority\n", ch[i]);
                break;

            case 3:
                printf("%c  ----> Second Highest Priority\n", ch[i]);
                break;

            case 4:
                printf("%c  ----> Highest Priority\n", ch[i]);
                break;
            }
        }
    }
}
```

## Output:
<img width="776" height="248" alt="image" src="https://github.com/user-attachments/assets/e4ab555b-d742-4e8e-b3cc-b98b2c4addc5" />



## Result:
Thus the C program to find and display the priority of the operator in the given Postfix expression is implemented successfully
