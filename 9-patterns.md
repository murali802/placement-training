Pattern Questions

Print these patterns using loops:
1. Square Star Pattern


Jump Game VII
Question:
You are given a binary string s and two integers minJump and maxJump.
You are initially positioned at index 0 (which is always '0').

You can jump from index i to any index j such that:

i + minJump ≤ j ≤ i + maxJump

s[j] == '0'

Return true if you can reach the last index of the string, otherwise return false.

Java Code:

import java.util.*;

public class Solution {
    public static boolean canReach(String s, int minJump, int maxJump) {
        int n = s.length();
        boolean[] visited = new boolean[n];
        Queue<Integer> queue = new LinkedList<>();

        queue.add(0);
        visited[0] = true;

        int farthest = 0;

        while (!queue.isEmpty()) {
            int current = queue.poll();

            int start = Math.max(current + minJump, farthest);
            int end = Math.min(current + maxJump, n - 1);

            for (int i = start; i <= end; i++) {
                if (s.charAt(i) == '0' && !visited[i]) {
                    if (i == n - 1) return true;

                    queue.add(i);
                    visited[i] = true;
                }
            }

            farthest = end + 1;
        }

        return n == 1;
    }

    public static void main(String[] args) {
        String s = "011010";
        int minJump = 2;
        int maxJump = 3;

        System.out.println(canReach(s, minJump, maxJump));
    }
}
Output:

true
Explanation (Short):

Start from index 0.

Use BFS to explore reachable indices.

Only jump to positions with '0'.

If you reach last index → return true.

If you want, I can give dry run, optimized sliding window explanation, or similar DP problems.


Valid Number

Valid Number
Question:
A valid number can be split into these parts:

An optional sign (+ or -)

Digits with optional decimal point

Optional exponent part (e or E) followed by an integer

Given a string s, return true if it is a valid number, otherwise return false.

Java Code:

import java.util.*;

public class Solution {
    public static boolean isNumber(String s) {
        s = s.trim();

        boolean seenDigit = false;
        boolean seenDot = false;
        boolean seenExp = false;

        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);

            if (Character.isDigit(c)) {
                seenDigit = true;
            } 
            else if (c == '+' || c == '-') {
                // sign allowed only at start or after exponent
                if (i != 0 && s.charAt(i - 1) != 'e' && s.charAt(i - 1) != 'E')
                    return false;
            } 
            else if (c == '.') {
                // dot allowed only once and before exponent
                if (seenDot || seenExp)
                    return false;
                seenDot = true;
            } 
            else if (c == 'e' || c == 'E') {
                // exponent allowed only once and must follow a number
                if (seenExp || !seenDigit)
                    return false;
                seenExp = true;
                seenDigit = false; // reset for exponent part
            } 
            else {
                return false;
            }
        }

        return seenDigit;
    }

    public static void main(String[] args) {
        String s = "2e10";
        System.out.println(isNumber(s));
    }
}
Output:

true
Examples:

"2" → true

"0089" → true

"-0.1" → true

"2e10" → true

"abc" → false

"1a" → false

"e3" → false

Explanation (Simple):

Track digits, decimal point, and exponent.

Only one . and one e/E allowed.

Sign allowed at start or after exponent.

Must contain at least one digit.

If you want, I can give regex solution, edge case list, or step-by-step dry run.


1.  *****
    *****
    *****
    *****
    *****


2.  *
    **
    ***
    ****
    *****


   import java.util.*;

public class Main {
    public static void main(String[] args) {
        int n = 5;

        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}

Output:

*****
*****
*****
*****
*****
2. Right-Angled Triangle Star Pattern
  import java.util.*;

public class Main {
    public static void main(String[] args) {
        int n = 5;

        for (int i = 1; i <= n; i++) {
            for (int j = 1; j <= i; j++) {
                System.out.print("*");
            }
            System.out.println();
        }
    }
}

Output:

*
**
***
****
***** 
