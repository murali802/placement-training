1. Build Array from Permutation
   import java.util.*;

public class BuildArray {
    public static void main(String[] args) {
        int[] nums = {0,2,1,5,3,4};
        int[] ans = new int[nums.length];

        for(int i = 0; i < nums.length; i++) {
            ans[i] = nums[nums[i]];
        }

        System.out.println(Arrays.toString(ans));
    }
}
Output:
[0, 1, 2, 4, 5, 3]
2. Concatenation of Array
import java.util.*;

public class ConcatArray {
    public static void main(String[] args) {
        int[] nums = {1,2,1};
        int[] ans = new int[2 * nums.length];

        for(int i = 0; i < nums.length; i++) {
            ans[i] = nums[i];
            ans[i + nums.length] = nums[i];
        }
        Output:
[1, 2, 1, 1, 2, 1]
3. Running Sum of 1D Array
import java.util.*;

public class RunningSum {
    public static void main(String[] args) {
        int[] nums = {1,2,3,4};

        for(int i = 1; i < nums.length; i++) {
            nums[i] += nums[i-1];
        }

        System.out.println(Arrays.toString(nums));
    }
}
Output:
[1, 3, 6, 10]
4. Richest Customer Wealth
public class Wealth {
    public static void main(String[] args) {
        int[][] accounts = {{1,2,3},{3,2,1}};
        int max = 0;

        for(int i = 0; i < accounts.length; i++) {
            int sum = 0;
            for(int j = 0; j < accounts[i].length; j++) {
                sum += accounts[i][j];
            }
            if(sum > max) max = sum;
        }

        System.out.println(max);
    }
}
Output:
6
5. Shuffle the Array
import java.util.*;

public class Shuffle {
    public static void main(String[] args) {
        int[] nums = {2,5,1,3,4,7};
        int n = 3;
        int[] ans = new int[nums.length];

        for(int i = 0; i < n; i++) {
            ans[2*i] = nums[i];
            ans[2*i + 1] = nums[i+n];
        }

        System.out.println(Arrays.toString(ans));
    }
}
Output:
[2, 3, 5, 4, 1, 7]
6. Kids With the Greatest Number of Candies
import java.util.*;

public class Candies {
    public static void main(String[] args) {
        int[] candies = {2,3,5,1,3};
        int extra = 3;

        int max = 0;
        for(int i = 0; i < candies.length; i++) {
            if(candies[i] > max) max = candies[i];
        }

        ArrayList<Boolean> result = new ArrayList<>();

        for(int i = 0; i < candies.length; i++) {
            if(candies[i] + extra >= max)
                result.add(true);
            else
                result.add(false);
        }

        System.out.println(result);
    }
}
Output:
[true, true, true, false, true]
7. Number of Good Pairs
public class GoodPairs {
    public static void main(String[] args) {
        int[] nums = {1,2,3,1,1,3};
        int count = 0;

        for(int i = 0; i < nums.length; i++) {
            for(int j = i + 1; j < nums.length; j++) {
                if(nums[i] == nums[j])
                    count++;
            }
        }

        System.out.println(count);
    }
}
Output:
4
8. How Many Numbers Are Smaller Than the Current Number
import java.util.*;

public class SmallerNumbers {
    public static void main(String[] args) {
        int[] nums = {8,1,2,2,3};
        int[] result = new int[nums.length];

        for(int i = 0; i < nums.length; i++) {
            int count = 0;
            for(int j = 0; j < nums.length; j++) {
                if(nums[j] < nums[i])
                    count++;
            }
            result[i] = count;
        }

        System.out.println(Arrays.toString(result));
    }
}
Output:
[4, 0, 1, 1, 3]
9. Create Target Array in Given Order
import java.util.*;

public class TargetArray {
    public static void main(String[] args) {
        int[] nums = {0,1,2,3,4};
        int[] index = {0,1,2,2,1};

        ArrayList<Integer> list = new ArrayList<>();

        for(int i = 0; i < nums.length; i++) {
            list.add(index[i], nums[i]);
        }

        System.out.println(list);
    }
}
Output:
[0, 4, 1, 3, 2]
10. Check if Sentence is Pangram
public class Pangram {
    public static void main(String[] args) {
        String s = "thequickbrownfoxjumpsoverthelazydog";
        boolean[] arr = new boolean[26];

        for(int i = 0; i < s.length(); i++) {
            arr[s.charAt(i) - 'a'] = true;
        }

        for(int i = 0; i < 26; i++) {
            if(!arr[i]) {
                System.out.println("Not Pangram");
                return;
            }
        }
        System.out.println("Pangram");
    }
}
Output:
Pangram
11. Count Items Matching a Rule
public class MatchRule {
    public static void main(String[] args) {
        String[][] items = {
            {"phone","blue","pixel"},
            {"computer","silver","lenovo"},
            {"phone","gold","iphone"}
        };

        String ruleKey = "color";
        String ruleValue = "silver";

        int index = 0;
        if(ruleKey.equals("type")) index = 0;
        else if(ruleKey.equals("color")) index = 1;
        else index = 2;

        int count = 0;

        for(int i = 0; i < items.length; i++) {
            if(items[i][index].equals(ruleValue))
                count++;
        }

        System.out.println(count);
    }
}
Output:
1
12. Find the Highest Altitude
public class Altitude {
    public static void main(String[] args) {
        int[] gain = {-5,1,5,0,-7};
        int max = 0, sum = 0;

        for(int i = 0; i < gain.length; i++) {
            sum += gain[i];
            if(sum > max)
                max = sum;
        }

        System.out.println(max);
    }
}
Output:
1

        System.out.println(Arrays.toString(ans));
    }
}
