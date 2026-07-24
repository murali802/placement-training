1. import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        double r = sc.nextDouble();

        double area = Math.PI * r * r;
        System.out.println(area);

        sc.close();
    }
}
output
153.93804002589985
2. Area of Triangle
double b = sc.nextDouble();
double h = sc.nextDouble();
double area = 0.5 * b * h;
System.out.println(area);
output
25.0
3. Area of Rectangle
double l = sc.nextDouble();
double w = sc.nextDouble();
double area = l * w;
System.out.println(area);
output
24.0
4. double b = sc.nextDouble();
double h = sc.nextDouble();
double area = 0.5 * b * h;
System.out.println(area);
output
20.0
5. Area of Parallelogram
double b = sc.nextDouble();
double h = sc.nextDouble();
double area = b * h;
System.out.println(area);
output
24.0
6. Area of Rhombus
double d1 = sc.nextDouble();
double d2 = sc.nextDouble();
double area = 0.5 * d1 * d2;
System.out.println(area);
output
40.0
7. Area of Equilateral Triangle
double a = sc.nextDouble();
double area = (Math.sqrt(3) / 4) * a * a;
System.out.println(area);
output
15.588457268119896
8. Perimeter of Circle
double r = sc.nextDouble();
double perimeter = 2 * Math.PI * r;
System.out.println(perimeter);
output
43.982297150257104
9. Perimeter of Equilateral Triangle
double a = sc.nextDouble();
double perimeter = 3 * a;
System.out.println(perimeter);
output
15.0
10. Perimeter of Parallelogram
double a = sc.nextDouble();
double b = sc.nextDouble();
double perimeter = 2 * (a + b);
System.out.println(perimeter);
output
16.0
-> intermediate Java Programs
1. Factorial Program
import java.util.Scanner;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int fact = 1;
        for(int i = 1; i <= n; i++) fact *= i;
        System.out.println(fact);
    }
}
output
2. Electricity Bill
   int units = sc.nextInt();
int bill = units * 5;
System.out.println(bill);
output
500
3. Average of N Numbers
   int n = sc.nextInt();
int sum = 0;
for(int i = 0; i < n; i++) sum += sc.nextInt();
System.out.println((double)sum / n);
Output:
20.0
4. Discount of Product
double price = sc.nextDouble();
double discount = sc.nextDouble();
double result = price - (price * discount / 100);
System.out.println(result);
Output:
900.0
5. Distance Between Two Points
   double x1 = sc.nextDouble(), y1 = sc.nextDouble();
double x2 = sc.nextDouble(), y2 = sc.nextDouble();
double d = Math.sqrt(Math.pow(x2-x1,2) + Math.pow(y2-y1,2));
System.out.println(d);
Output:
5.0
6. Commission Percentage
   double sales = sc.nextDouble();
double rate = sc.nextDouble();
System.out.println(sales * rate / 100);
Output:
500.0
7. Power in Java
import java.util.Scanner;

public class Power {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int x = sc.nextInt();
        int y = sc.nextInt();

        int result = 1;
        for(int i = 1; i <= y; i++) {
            result *= x;
        }

        System.out.println(result);
    }
}
Output:
8
8. Calculate Depreciation of Value
import java.util.Scanner;

public class Depreciation {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double cost = sc.nextDouble();
        double salvage = sc.nextDouble();
        double life = sc.nextDouble();

        double depreciation = (cost - salvage) / life;
        System.out.println(depreciation);
    }
}
Output:
2000.0
9. import java.util.Scanner;

public class BattingAverage {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int runs = sc.nextInt();
        int innings = sc.nextInt();
        int notOut = sc.nextInt();

        double avg = (double) runs / (innings - notOut);
        System.out.println(avg);
    }
}
Output:
33.333333333333336
10. Calculate CGPA Java Program
import java.util.Scanner;

public class CGPA {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        double sum = 0;

        for(int i = 0; i < n; i++) {
            sum += sc.nextDouble();
        }

        double cgpa = sum / n;
        System.out.println(cgpa);
    }
}
Output:
8.125
11. Compound Interest Java Program
import java.util.Scanner;

public class CompoundInterest {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double p = sc.nextDouble();
        double r = sc.nextDouble();
        int t = sc.nextInt();

        double ci = p * Math.pow((1 + r / 100), t);
        System.out.println(ci);
    }
}
Output:
1210.0
12. Calculate Average Marks
import java.util.Scanner;

public class AverageMarks {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int sum = 0;

        for(int i = 0; i < n; i++) {
            sum += sc.nextInt();
        }

        double avg = (double) sum / n;
        System.out.println(avg);
    }
}
Output:
80.0
13. Sum Of N Numbers
import java.util.Scanner;

public class SumN {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int sum = 0;

        for(int i = 1; i <= n; i++) {
            sum += i;
        }

        System.out.println(sum);
    }
}
Output:
15
14. Armstrong Number In Java
import java.util.Scanner;

public class Armstrong {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int num = sc.nextInt();
        int original = num;
        int sum = 0;

        while(num > 0) {
            int digit = num % 10;
            sum += digit * digit * digit;
            num /= 10;
        }

        if(sum == original)
            System.out.println("Armstrong Number");
        else
            System.out.println("Not Armstrong Number");
    }
}
Output:
Armstrong Number
