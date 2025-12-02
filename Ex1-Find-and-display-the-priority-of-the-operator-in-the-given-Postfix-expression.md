# EX 1 Display operator precedence in the infix expression.
## DATE: 06-09-2025
## AIM:
To write a Java program to find and display the priority of the operator in the given Infix expression.

## Algorithm:
1. Start the program.
2. Define the priority() function to assign and return the precedence level of specific operators (e.g., ^ as 4, *, /, % as 3, +, - as 2, &, | as 1).
3. Initialize the string containing the infix expression.
4. Loop through each character in the expression string.
5. Check if the current character is an operator defined in the priority levels.
6. If it is an operator, call the priority() function to determine its precedence value.
7. Print the operator and its corresponding descriptive priority level (e.g., Highest Priority, Lowest Priority).
8. End.

## Program:
/*
Program to find and display the priority of the operator in the given Infix expression
Developed by: Dharani dharan K
RegisterNumber: 212223040036
*/
import java.util.Scanner;

public class OperatorPrecedence {

    // 2. Define the priority() function to return the priority of operators.
    static int priority(char x) {
        if (x == '&' || x == '|')
            return 1; // Lowest Priority
        if (x == '+' || x == '-')
            return 2; // Second Lowest Priority
        if (x == '*' || x == '/' || x == '%')
            return 3; // Second Highest Priority
        if (x == '^')
            return 4; // Highest Priority
        return 0; // For operands or parentheses
    }

    public static void main(String[] args) {
        // 3. Initialize the string containing operators and operands.
        String expression = "(A*B)^C+(D%H)/F&G";
        System.out.println("Analyzing Infix Expression: " + expression + "\n");

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


[![image](https://github.com/user-attachments/assets/23cf1270-fdba-4c49-ae95-3c2c5f339d3a)]

## Result:
Thus the Java program to find and display the priority of the operator in the given Infix expression is implemented successfully.
