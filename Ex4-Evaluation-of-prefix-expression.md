Ex4 Evaluation of prefix expression
DATE: 06-09-2025
Developed by: DHARANI DHARAN K
RegisterNumber: 212223040036

AIM:
To write a Java program to evaluate the given prefix expression using stack and print the output of the given prefix expression from inside the function.

Algorithm
Start
Initialize an empty stack s with a variable top for tracking the stack index.
Define a push() function to add an element to the stack.
Define a pop() function to remove and return the top element from the stack.
In evalprefix(), loop through the given prefix expression from right to left.
For each character:
If it’s an operator (+, *), pop two operands from the stack, perform the operation, and push the result.
If it's a digit, convert it into an integer and push it onto the stack.
Finally, print the result after the loop ends.
End

Program:

/*
Program to evaluate the given prefix expression
Developed by: Dharani dharan K
RegisterNumber: 212223040036
*/
import java.util.Scanner;
import java.util.Stack;

public class PrefixEvaluator {

    public static void evalprefix(String p) {

        Stack<Integer> s = new Stack<>();
        int a, b, c;

        for (int i = p.length() - 1; i >= 0; i--) {
            char ch = p.charAt(i);

            if (Character.isDigit(ch)) {
                s.push(Character.getNumericValue(ch));
            } 
            else if (ch == '+' || ch == '*') {

                a = s.pop();
                b = s.pop();

                switch (ch) {
                    case '+':
                        c = a + b;
                        break;
                    case '*':
                        c = a * b;
                        break;
                    default:
                        c = 0;
                        break;
                }
                s.push(c);
            }
        }

        System.out.println(s.pop());
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String expression = scanner.next(); 
        evalprefix(expression);
    }
}


Output:
<img width="649" height="254" alt="image" src="https://github.com/user-attachments/assets/a810844b-7ebc-4079-952f-80e4d2850f93" />

Result:
Thus, the Java program to evaluate the prefix expression using stack and print the output of the given prefix expression from inside the function is implemented successfully
