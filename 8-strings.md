1. Defanging an IP Address
   import java.util.*;

public class Solution {
    public static String defangIPaddr(String address) {
        return address.replace(".", "[.]");
    }

    public static void main(String[] args) {
        String address = "1.1.1.1";
        System.out.println(defangIPaddr(address));
    }
}

Output:

1[.]1[.]1[.]1
2. Shuffle String
import java.util.*;

public class Solution {
    public static String restoreString(String s, int[] indices) {
        char[] result = new char[s.length()];

        for (int i = 0; i < s.length(); i++) {
            result[indices[i]] = s.charAt(i);
        }

        return new String(result);
    }

    public static void main(String[] args) {
        String s = "abc";
        int[] indices = {2, 1, 0};

        System.out.println(restoreString(s, indices));
    }
}

Output:

cba
->Medium
1. Jump Game VII
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
->Hard
1. Valid Number
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
