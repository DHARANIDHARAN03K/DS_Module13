# Ex5 Stack Operations
## DATE: 06-09-2025
## AIM:
To write a Java program to perform push and pop operations of the stack in the infix to postfix conversion.

## Algorithm
1. Initialize top as -1 and declare stack as a character array.
2. To push, increment top and assign the character to stack[top].
3. To pop, check if top is -1 and return '\0' if true.
4. If not, return stack[top] and decrement top.

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
        // Sample demonstration
        push('A');
        push('B');
        push('C');

        System.out.println("Popped element: " + pop());
        System.out.println("Popped element: " + pop());
    }
}

## Output:
![image](https://github.com/user-attachments/assets/23cf1270-fdba-4c49-ae95-3c2c5f339d3a)


## Result:
Thus the Java program to perform push and pop operations of the stack in the infix to postfix conversion is implemented successfully.
