# Ex5 Stack Operations
## DATE: 01-03-2025
## AIM:
To write a C function to perform push and pop operation of the stack in the infix to postfix conversion.

## Algorithm
1. **Initialize expression** as a character array.

   * Example: `"(A*B)^C+(D%H)/F&G"`

2. **Define a `priority(char x)` function**:

   * Return a number based on operator precedence:

     * `^` → 4 (Highest)
     * `* / %` → 3
     * `+ -` → 2
     * `& |` → 1 (Lowest)
     * `(` → 0
     * Others → -1

3. **Loop through each character** in the expression:

   * Use `strlen()` to get length.

4. **Call `priority(ch[i])`** to get operator priority.

5. **If priority > 0**, display corresponding message:

   * Case 1 → "Lowest Priority"
   * Case 2 → "Second Lowest Priority"
   * Case 3 → "Second Highest Priority"
   * Case 4 → "Highest Priority"

6. **End program.**

## Program:
```c
/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: MUKESH KUMAR S
RegisterNumber: 212223240099
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
        return -1;
}

int main()
{
    char ch[100] = "(A*B)^C+(D%H)/F&G";

    for (int i = 0; i < strlen(ch); i++)
    {
        int j = priority(ch[i]);
        if (j > 0) // skip '(' and other non-operators
        {
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

    return 0;
}
```

## Output:

<img width="717" height="265" alt="image" src="https://github.com/user-attachments/assets/3fa9b60a-b28c-4167-b5b6-1be6110aa2f3" />


## Result:
Thus the C program to perform push and pop operation of the stack in the infix to postfix conversion is implemented successfully.
