# Ex5 Stack Operations
## DATE: 06-09-2025
## AIM:
To write a Java program to perform push and pop operations of the stack in the infix to postfix conversion.

## Algorithm
Start
Initialize an empty stack as a character array with a variable top for tracking the stack index.
Define a push() function to add a character to the stack.
Define a pop() function to remove and return the top character from the stack.
In the main function, demonstrate push and pop operations.
End

## Program:
/*
Program to perform push and pop operations of the stack
Developed by: Dharani dharan K
RegisterNumber: 212223040036
*/

public class StackOperations {

    static char[] stack = new char[100];
    static int top = -1;

    public static void push(char x) {
        stack[++top] = x;
    }

    public static char pop() {
        if (top == -1)
            return '\0';   // Represents empty stack
        else
            return stack[top--];
    }

    public static void main(String[] args) {
        push('A');
        push('B');
        push('C');

        System.out.println(pop());
        System.out.println(pop());
    }
}

## Output:
![image](https://github.com/user-attachments/assets/23cf1270-fdba-4c49-ae95-3c2c5f339d3a)

## Result:
Thus, the Java program to perform push and pop operations of the stack in the infix to postfix conversion is implemented successfully.
