Ex4 Evaluation of prefix expression
DATE: 06-09-2025
AIM:
To write a C function to evaluate the given prefix expression using stack and print the output of the given prefix expression from the stack inside the function.

Algorithm
Start 

Initialize an empty stack s with a variable top for tracking the stack index. 

Define a push() function to add an element to the stack. 

Define a pop() function to remove and return the top element from the stack. 

In evalprefix(), loop through the given prefix expression from right to left. 

For each character, if it’s an operator (+, *), pop two operands from the stack, perform the     operation, and push the result. 

If it's a digit, convert it to an integer and push it onto the stack; finally, print the         result after the loop ends. 

End

Program:
Java

/*
Program to evaluate the given prefix expression
Developed by: Dharani dharan K
RegisterNumber: 212223040036
*/
import java.util.Scanner;
import java.util.Stack;

public class PrefixEvaluator {

    // The core logic is now in a static method within the class,
    // using Java's built-in Stack structure.
    public static void evalprefix(String p) {
        // Java's Stack is safer and dynamically sized compared to C arrays.
        Stack<Integer> s = new Stack<>();
        int a, b, c;

        // Loop through the prefix expression from right to left (p.length() - 1 to 0)
        for (int i = p.length() - 1; i >= 0; i--) {
            char ch = p.charAt(i);

            if (Character.isDigit(ch)) {
                // If it's a digit, convert char to int value and push.
                // This replaces the C logic of p[i] - '0' or p[i] - 48
                s.push(Character.getNumericValue(ch));
            } else if (ch == '+' || ch == '*') {
                // If it's an operator, pop two operands (a and b),
                // performing the operation based on the order pop() retrieves them.

                // The stack pop order is crucial in evaluation:
                // a is the first operand (op2 in C context)
                a = s.pop();
                // b is the second operand (op1 in C context)
                b = s.pop();

                switch (ch) {
                    case '+':
                        c = a + b;
                        break;
                    case '*':
                        c = a * b;
                        break;
                    default:
                        // Should not happen for this specific program
                        c = 0;
                        break;
                }
                s.push(c);
            }
        }
        // After the loop, the result is the last element remaining on the stack.
        System.out.println(s.pop());
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        // Assuming input is taken on one line
        String expression = scanner.next(); 
        evalprefix(expression);
        // Note: The original C code did not read input; 
        // this Java version includes input reading for functionality.
    }
}
Output:
Result:
Thus, the C program to evaluate the prefix expression using stack and print the output of the given prefix expression from the stack inside the function is implemented successfully.
