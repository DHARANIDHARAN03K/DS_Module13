Ex2 Conversion of the infix expression into postfix expression
DATE: 06-09-2025
Developed by: DHARANI DHARAN K
RegisterNumber: 212223040036

AIM:
To write a Java program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

Algorithm
Start the program.
Initialize a stack and set the top index to -1.
Define the push() and pop() functions to add and remove elements from the stack.
Define the priority() function to assign priorities to operators.
Traverse the expression in the IntoPost() function, handling operands, parentheses, and operators.
After processing the expression, pop and print any remaining operators from the stack.
End.

Program:

/*
Program to convert the infix expression into postfix expression
Developed by: Dharani dharan K
RegisterNumber: 212223040036
*/

import java.util.*;

public class InfixToPostfix {

    static char[] stack = new char[100];
    static int top = -1;

    static void push(char x) {
        stack[++top] = x;
    }

    static char pop() {
        if (top == -1)
            return 0;
        else
            return stack[top--];
    }

    static int priority(char x) {
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

        return 0;
    }

    static void IntoPost(String exp) {
        char x;
        for (int i = 0; i < exp.length(); i++) {

            char ch = exp.charAt(i);

            if (Character.isLetterOrDigit(ch)) {
                System.out.print(ch + " ");
            }
            else if (ch == '(') {
                push(ch);
            }
            else if (ch == ')') {
                while ((x = pop()) != '(')
                    System.out.print(x + " ");
            }
            else {
                while (top != -1 && priority(stack[top]) >= priority(ch))
                    System.out.print(pop() + " ");

                push(ch);
            }
        }

        while (top != -1) {
            System.out.print(pop() + " ");
        }
    }

    public static void main(String[] args) {
        String exp = "3%2+4*(A&B)";
        IntoPost(exp);
    }
}


Output:
<img width="421" height="141" alt="image" src="https://github.com/user-attachments/assets/0ae6f929-4110-4654-a2ec-afd1c7638a3b" />

Result:
Thus, the Java program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
