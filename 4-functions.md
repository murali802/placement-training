1. Define two methods to print the maximum and minimum number among three numbers entered by the user.
   import java.util.Scanner;

public class MaxMin {
    static void max(int a, int b, int c) {
        int max = a;
        if(b > max) max = b;
        if(c > max) max = c;
        System.out.println("Maximum: " + max);
    }

    static void min(int a, int b, int c) {
        int min = a;
        if(b < min) min = b;
        if(c < min) min = c;
        System.out.println("Minimum: " + min);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        int c = sc.nextInt();

        max(a, b, c);
        min(a, b, c);
    }
}
output
Maximum: 20
Minimum: 5
2. Define a program to check whether a number is even or odd.
import java.util.Scanner;

public class EvenOdd {
    static void check(int n) {
        if(n % 2 == 0)
            System.out.println("Even");
        else
            System.out.println("Odd");
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        check(n);
    }
}
Output:
Even
3. Define a method to check if a person is eligible to vote (age ≥ 18).
import java.util.Scanner;

public class Vote {
    static void check(int age) {
        if(age >= 18)
            System.out.println("Eligible");
        else
            System.out.println("Not Eligible");
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int age = sc.nextInt();
        check(age);
    }
}
Output:
Not Eligible
4. Write a program to print the sum of two numbers using a method.
import java.util.Scanner;

public class Sum {
    static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();

        System.out.println(add(a, b));
    }
}
Output:
10
5.Define a method that returns the product of two numbers.
import java.util.Scanner;

public class Product {
    static int multiply(int a, int b) {
        return a * b;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();

        System.out.println(multiply(a, b));
    }
}
Output:
30
6. Write a program to print the area and circumference of a circle using methods.
import java.util.Scanner;

public class Circle {
    static double area(double r) {
        return Math.PI * r * r;
    }

    static double circumference(double r) {
        return 2 * Math.PI * r;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double r = sc.nextDouble();

        System.out.println("Area: " + area(r));
        System.out.println("Circumference: " + circumference(r));
    }
}
Output:
Area: 28.274333882308138
Circumference: 18.84955592153876
7. Define a method to check whether a number is prime or not.
import java.util.Scanner;

public class Prime {
    static void check(int n) {
        if(n <= 1) {
            System.out.println("Not Prime");
            return;
        }

        for(int i = 2; i <= n/2; i++) {
            if(n % i == 0) {
                System.out.println("Not Prime");
                return;
            }
        }
        System.out.println("Prime");
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        check(n);
    }
}
Output:
Prime
8. Write a program to display grades based on marks:
import java.util.Scanner;

public class Grade {
    static void getGrade(int marks) {
        if(marks >= 90)
            System.out.println("Grade A");
        else if(marks >= 75)
            System.out.println("Grade B");
        else if(marks >= 50)
            System.out.println("Grade C");
        else
            System.out.println("Fail");
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int marks = sc.nextInt();
        getGrade(marks);
    }
}
Output:
Fail

