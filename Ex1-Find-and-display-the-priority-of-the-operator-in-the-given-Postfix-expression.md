# EX 1 Display operator precedence in the infix expression.
## DATE: 06-09-2025
## AIM:
To write a Java program to find and display the priority of the operator in the given Postfix expression

## Algorithm
Start the program.

Define the priority() function to return the priority of operators.

Initialize the string containing operators and operands.

Loop through each character in the string.

For each operator, call the priority() function to determine its priority.

Print the operator and its corresponding priority level.

End.

## Program:
Java

/*
Program to find and display the priority of the operator in the given Postfix expression
Developed by: Dharani dharan K
RegisterNumber: 212223040036
*/
import java.util.Scanner;

public class OperatorPrecedence {

    // 2. Define the priority() function to return the priority of operators.
    static int priority(char x) {
        if (x == '&' || x == '|')
            return 1;
        if (x == '+' || x == '-')
            return 2;
        if (x == '*' || x == '/' || x == '%')
            return 3;
        if (x == '^')
            return 4;
        return 0; // For operands or parentheses
    }

    public static void main(String[] args) {
        // 3. Initialize the string containing operators and operands.
        String expression = "(A*B)^C+(D%H)/F&G";

        // 4. Loop through each character in the string.
        for (int i = 0; i < expression.length(); i++) {
            char ch = expression.charAt(i);

            // 5. Check if the character is an operator
            if (ch == '+' || ch == '-' || ch == '*' || ch == '/' || 
                ch == '%' || ch == '^' || ch == '&' || ch == '|') {
                
                int p = priority(ch); // Call the priority() function

                // 6. Print the operator and its corresponding priority level
                System.out.print(ch + " ---- > ");
                switch (p) {
                    case 1:
                        System.out.println("Lowest Priority");
                        break;
                    case 2:
                        System.out.println("Second Lowest Priority");
                        break;
                    case 3:
                        System.out.println("Second Highest Priority");
                        break;
                    case 4:
                        System.out.println("Highest Priority");
                        break;
                    default:
                        System.out.println("Unknown Priority");
                        break;
                }
            }
        }
    }
}

## Output:
![image](https://github.com/user-attachments/assets/a810844b-7ebc-4079-952f-80e4d2850f93)

## Result:
Thus the Java program to find and display the priority of the operator in the given Postfix expression is implemented successfully.
