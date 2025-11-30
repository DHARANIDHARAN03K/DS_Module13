EX 1 You’re creating a health monitoring device which stores several sensor readings in an array. To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
DATE: 13.10.2025
Developed by: DHARANI DHARAN K
RegisterNumber: 212223040036
AIM:
To write a JAVA program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.

Algorithm
Start

Read the number of elements (e.g., number of heartbeat readings).

Store all readings in an array.

Call a recursive function findMin(arr, index) If index == arr.length - 1, return arr[index] Else return min(arr[index], findMin(arr, index + 1))

Print the minimum value returned by the recursive function.

End

Program:
Java

/*
Program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
*/
import java.util.*;

public class Main {
    static int getMin(int[] arr, int i, int n) {
        if (i == n - 1) {
            return arr[i];
        }

    
        int minRest = getMin(arr, i + 1, n);
       
        return Math.min(arr[i], minRest);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        System.out.println(getMin(arr, 0, n));
    }
}
Output:
<img width="649" height="254" alt="image" src="https://github.com/user-attachments/assets/e2c774aa-cc92-40f6-acb8-778042dd4078" />

Result:
Thus the JAVA program to find the minimum value (e.g., lowest heartbeat), implement a recursive method has implemented successfully

Ex2 Count how many times a number appears in an array recursively.
DATE: 20.08.2025
AIM:
To write a Java program to Count how many times a number appears in an array recursively.

Algorithm
Start

Read the size of the array and input all elements into the array.

Read the target number whose frequency you want to count.

Call the recursive function countOccurrences(arr, index, target) If index == arr.length, return 0 If arr[index] == target, return 1 + countOccurrences(arr, index + 1, target) Else return countOccurrences(arr, index + 1, target)

Display the returned count as the total number of occurrences.

Program:
Java

/*
Program Count how many times a number appears in an array recursively.
*/
import java.util.Scanner;

public class CountOccurrences {

    // Recursive function to count occurrences of a target number
    public static int countOccurrences(int[] arr, int n, int target) {
        //write your code here
        if (n == 0) {
            return 0;
        }

        // Check the last element and add 1 if it matches the target
        if (arr[n - 1] == target) {
            return 1 + countOccurrences(arr, n - 1, target);
        } else {
            return countOccurrences(arr, n - 1, target);
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input: Size of array
        int size = scanner.nextInt();

        if (size <= 0) {
            System.out.println("Invalid array size. Must be positive.");
            return;
        }

        // Input: Array elements
        int[] arr = new int[size];
        for (int i = 0; i < size; i++) {
            arr[i] = scanner.nextInt();
        }

        // Input: Target number to count
        int target = scanner.nextInt();

        // Compute and display result
        int count = countOccurrences(arr, size, target);
        System.out.println("The number " + target + " appears " + count + " time(s) in the array.");

        scanner.close();
    }
}
Output:
<img width="1027" height="611" alt="image" src="https://github.com/user-attachments/assets/8b339a84-624e-4b20-93c5-7304d201510d" />

Result:
Thus, the Java program to Count how many times a number appears in an array recursively is implemented successfully.

EX3 Write a program to count the number of digits in an integer.
DATE: 27.08.2025
AIM:
To write a C program to implement Tower of Hanoi

Algorithm
Start the program.

Read an integer from the user.

Define a recursive function countDigits() that counts digits by dividing the number by 10 each time.

Base condition: if the number is 0, return 0.

Recursive step: return 1 + countDigits(number / 10).

Display the total count of digits.

Stop the program.

Program:
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
Output:
<img width="341" height="158" alt="image" src="https://github.com/user-attachments/assets/7937432d-e34f-46f6-bfde-6840e7fe8c8f" />

Result:
Thus, the Java program to to count the number of digits in an integer is implemented successfully.

Ex4 You are given a Java program that performs matrix addition. If Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension, what will be the nature (even/odd/mixed) of the resulting matrix?
DATE: 3.09.2025
AIM:
To write a java function to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix.

Algorithm
Start the program.

Read the dimensions of both matrices (rows and columns).

Check whether Matrix A and Matrix B have the same dimensions.

If not, display “Matrices are not of same dimension” and stop.

Read Matrix A and check each element:

If every element is odd, continue.

If any element is even, mark A as invalid and stop further checking.

If both matrices are valid, compute the resultant matrix (e.g., A + B or any operation specified).

Determine the nature of the resultant matrix:

If all elements are odd, print “Resultant matrix is an Odd Matrix”.

If all elements are even, print “Resultant matrix is an Even Matrix”.

Display the Resultant Matrix.

Stop the program.

Program:
Java

/*
Program to ind the nature of resultant matrrix.
*/
import java.util.Scanner;

public class MatrixAddition {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int rows = sc.nextInt();
        int cols = sc.nextInt();

        int[][] A = new int[rows][cols];
        int[][] B = new int[rows][cols];
        int[][] result = new int[rows][cols];

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                A[i][j] = sc.nextInt();
            }
        }
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                B[i][j] = sc.nextInt();
            }
        }
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                result[i][j] = A[i][j] + B[i][j];
            }
        }
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                System.out.print(result[i][j] + " ");
            }
            System.out.println();
        }

       
    }
}
Output:
<img width="422" height="624" alt="image" src="https://github.com/user-attachments/assets/34782319-f865-4fe8-a281-f3aed6852160" />

Result:
Thus, the java program to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix is implemented successfully.

Ex5 Count Inversions in an Array
DATE: 10.09.2025
AIM:
To write a Java program to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j

Algorithm
Start the program.

Declare an integer array arr of size n.

Read the value of n (number of elements).

Read n elements and store them in the array arr.

Initialize a variable count to 0 to store the number of inversions.

Use two nested loops:

Outer loop variable i from 0 to n - 1

Inner loop variable j from i + 1 to n - 1

For each pair (i, j), if arr[i] > arr[j] and i < j, increment count by 1.

After all comparisons, print the value of count as the total number of inversions in the array.

Stop the program.

Program:
Java

/*
Program toto Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j
*/
import java.util.Scanner;

public class CountInversions
{
    public static int countInversions(int[] arr)
{
        int n = arr.length;
        int count = 0;
        for (int i = 0; i < n - 1; i++)
{
            for (int j = i + 1; j < n; j++)
{
                if (arr[i] > arr[j]) {
                    count++; 
                }
            }
        }

        return count;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        int[] arr = new int[n];

        System.out.println("Enter " + n + " elements:");
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        int inversions = countInversions(arr);

        System.out.println("Number of inversions in the array: " + inversions);

        sc.close();
    }
}
Output:
<img width="406" height="243" alt="image" src="https://github.com/user-attachments/assets/6c314097-77b6-4f0e-a6ac-6e5e1cc689f4" />

Result:
Thus the Java program to to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j is implemented successfully.
