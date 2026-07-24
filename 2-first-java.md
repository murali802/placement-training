1. Write a program to print whether a number is even or odd, also take input from the user.
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int num = sc.nextInt();  // Read input

        if (num % 2 == 0) {
            System.out.println("Even");
        } else {
            System.out.println("Odd");
        }

        sc.close();
    }
}
output
Even
2. Take name as input and print a greeting message for that particular name.
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String name = sc.nextLine();  // Take name input

        System.out.println("Hello " + name);

        sc.close();
    }
}
output
Hello Murali
3. Write a program to input principal, time, and rate (P, T, R) from the user and find Simple Interest.
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double P = sc.nextDouble(); // Principal
        double T = sc.nextDouble(); // Time
        double R = sc.nextDouble(); // Rate

        double SI = (P * T * R) / 100;

        System.out.println("Simple Interest = " + SI);

        sc.close();
    }
}
output
Simple Interest = 100.0
4. Take in two numbers and an operator (+, -, *, /) and calculate the value. (Use if conditions)
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double a = sc.nextDouble();   // First number
        double b = sc.nextDouble();   // Second number
        char op = sc.next().charAt(0); // Operator

        if (op == '+') {
            System.out.println(a + b);
        } else if (op == '-') {
            System.out.println(a - b);
        } else if (op == '*') {
            System.out.println(a * b);
        } else if (op == '/') {
            if (b != 0) {
                System.out.println(a / b);
            } else {
                System.out.println("Division by zero not allowed");
            }
        } else {
            System.out.println("Invalid operator");
        }

        sc.close();
    }
}
output
4.0
5. Take 2 numbers as input and print the largest number.
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int a = sc.nextInt();
        int b = sc.nextInt();

        if (a > b) {
            System.out.println(a);
        } else if (b > a) {
            System.out.println(b);
        } else {
            System.out.println("Both are equal");
        }

        sc.close();
    }
}
output
15
