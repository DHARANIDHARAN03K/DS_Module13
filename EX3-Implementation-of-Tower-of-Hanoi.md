# EX3 Write a program to count the number of digits in an integer.
## DATE: 27.08.2025
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm
Start the program.

Read an integer from the user.

Define a recursive function countDigits() that counts digits by dividing the number by 10 each time.

Base condition: if the number is 0, return 0.

Recursive step: return 1 + countDigits(number / 10).

Display the total count of digits.

Stop the program.

## Program:
Java

/*
Program to to count the number of digits in an integer
*/
import java.util.Scanner;

public class CountDigitsRecursive {
    static int countDigits(int n) {
        if (n == 0)
            return 0;
        return 1 + countDigits(n / 10);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter an integer: ");
        int n = sc.nextInt();
        if (n == 0)
            System.out.println("Number of digits: 1");
        else
            System.out.println("Number of digits: " + countDigits(Math.abs(n)));
        sc.close();
    }
}

## Output:
<img width="341" height="158" alt="image" src="https://github.com/user-attachments/assets/7937432d-e34f-46f6-bfde-6840e7fe8c8f" />

## Result:
Thus, the Java program to count the number of digits in an integer is implemented successfully.



