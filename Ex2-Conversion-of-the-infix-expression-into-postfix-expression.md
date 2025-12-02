# Ex2 Conversion of the infix expression into postfix expression
## DATE: 06-09-2025
Developed by: DHARANI DHARAN K
RegisterNumber: 212223040036

## AIM:
To write a Java program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule.

## Algorithm:
1. Start the program.
2. Initialize a stack (character array) and set the top index to -1.
3. Define the push() and pop() functions to add and remove elements from the stack.
4. Define the priority() function to assign precedence values to operators.
5. Traverse the expression in the IntoPost() function:
    a. If an operand is found, print it immediately.
    b. If an opening parenthesis '(' is found, push it onto the stack.
    c. If a closing parenthesis ')' is found, pop and print operators from the stack until an opening parenthesis '(' is encountered and discard both parentheses.
    d. If an operator is found, pop and print operators from the stack that have greater or equal precedence than the current operator, then push the current operator onto the stack.
6. After processing the entire expression, pop and print any remaining operators from the stack.
7. End.

## Program:
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
            return 0; // Represents an empty stack
        else
            return stack[top--];
    }

    static int priority(char x) {
        if (x == '(')
            return 0;

        // Logical AND/OR
        if (x == '&' || x == '|')
            return 1;

        // Additive operators
        if (x == '+' || x == '-')
            return 2;

        // Multiplicative operators
        if (x == '*' || x == '/' || x == '%')
            return 3;

        // Exponentiation (Highest precedence)
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
        System.out.println("Infix Expression: " + exp);
        System.out.print("Postfix Expression: ");
        IntoPost(exp);
        System.out.println();
    }
}

## Output:
 
[![image](https://github.com/user-attachments/assets/23cf1270-fdba-4c49-ae95-3c2c5f339d3a)]

## Result:
Thus, the Java program to convert the infix expression into postfix form using stack by following the operator precedence and associative rule is implemented successfully.
