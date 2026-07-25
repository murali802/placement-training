1. Linear Search
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();          // size of array
        int[] arr = new int[n];

        for(int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();    // input elements
        }

        int key = sc.nextInt();       // element to search
        int pos = -1;

        for(int i = 0; i < n; i++) {
            if(arr[i] == key) {
                pos = i;
                break;
            }
        }

        System.out.println(pos);
    }
}
Output
2
2. Binary Search
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();           // size of array
        int[] arr = new int[n];

        for(int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();     // sorted array input
        }

        int key = sc.nextInt();        // element to search

        int low = 0, high = n - 1;
        int pos = -1;

        while(low <= high) {
            int mid = (low + high) / 2;

            if(arr[mid] == key) {
                pos = mid;
                break;
            }
            else if(arr[mid] < key) {
                low = mid + 1;
            }
            else {
                high = mid - 1;
            }
        }

        System.out.println(pos);
    }
}
Output
3
->Easy
1. Square Root
   import java.util.*;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int x = sc.nextInt();

        int low = 0, high = x;
        int ans = 0;

        while (low <= high) {
            int mid = (low + high) / 2;

            if ((long)mid * mid <= x) {
                ans = mid;
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }

        System.out.println(ans);
    }
}
Output
2
2. Guess Number Higher or Lower
public class Main {

    // Suppose the picked number is 6
    static int picked = 6;

    // Guess API
    public static int guess(int num) {
        if (num == picked) return 0;
        else if (num > picked) return -1;
        else return 1;
    }

    public static void main(String[] args) {
        int n = 10;

        int low = 1, high = n;
        int result = -1;

        while (low <= high) {
            int mid = (low + high) / 2;
            int res = guess(mid);

            if (res == 0) {
                result = mid;
                break;
            } else if (res == 1) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }

        System.out.println(result);
    }
}
Output
6
3. First Bad Version
public class Main {

    // Suppose version 4 is the first bad version
    static int bad = 4;

    public static boolean isBadVersion(int version) {
        return version >= bad;
    }

    public static void main(String[] args) {
        int n = 10;

        int low = 1, high = n;
        int firstBad = n;

        while (low <= high) {
            int mid = (low + high) / 2;

            if (isBadVersion(mid)) {
                firstBad = mid;
                high = mid - 1;
            } else {
                low = mid + 1;
            }
        }

        System.out.println(firstBad);
    }
}
Output
4
->Medium
1. Find First and Last Position of Element in Sorted Array
   import java.util.*;

public class Solution {
    public static int[] searchRange(int[] nums, int target) {
        int first = -1, last = -1;

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] == target) {
                if (first == -1) first = i;
                last = i;
            }
        }
        return new int[]{first, last};
    }

    public static void main(String[] args) {
        int[] nums = {5,7,7,8,8,10};
        int target = 8;

        int[] result = searchRange(nums, target);
        System.out.println(result[0] + " " + result[1]);
    }
}

Output:

3 4
2. Single Element in a Sorted Array
import java.util.*;

public class Solution {
    public static int singleNonDuplicate(int[] nums) {
        int result = 0;
        for (int num : nums) {
            result ^= num;  // XOR operation
        }
        return result;
    }

    public static void main(String[] args) {
        int[] nums = {1,1,2,3,3,4,4,8,8};
        System.out.println(singleNonDuplicate(nums));
    }
}

Output:

2
3. Search in Rotated Sorted Array
import java.util.*;

public class Solution {
    public static int search(int[] nums, int target) {
        int left = 0, right = nums.length - 1;

        while (left <= right) {
            int mid = (left + right) / 2;

            if (nums[mid] == target)
                return mid;

            if (nums[left] <= nums[mid]) { // left part sorted
                if (target >= nums[left] && target < nums[mid])
                    right = mid - 1;
                else
                    left = mid + 1;
            } else { // right part sorted
                if (target > nums[mid] && target <= nums[right])
                    left = mid + 1;
                else
                    right = mid - 1;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        int[] nums = {4,5,6,7,0,1,2};
        int target = 0;

        System.out.println(search(nums, target));
    }
}

Output:

4
->Hard
1. Median of Two Sorted Arrays
   import java.util.*;

public class Solution {
    public static double findMedianSortedArrays(int[] nums1, int[] nums2) {
        int[] merged = new int[nums1.length + nums2.length];
        int i = 0, j = 0, k = 0;

        // Merge two arrays
        while (i < nums1.length && j < nums2.length) {
            if (nums1[i] < nums2[j])
                merged[k++] = nums1[i++];
            else
                merged[k++] = nums2[j++];
        }

        while (i < nums1.length)
            merged[k++] = nums1[i++];

        while (j < nums2.length)
            merged[k++] = nums2[j++];

        int n = merged.length;

        if (n % 2 == 0)
            return (merged[n/2 - 1] + merged[n/2]) / 2.0;
        else
            return merged[n/2];
    }

    public static void main(String[] args) {
        int[] nums1 = {1, 3};
        int[] nums2 = {2};

        System.out.println(findMedianSortedArrays(nums1, nums2));
    }
}

Output:

2.0
2. Find Minimum in Rotated Sorted Array II
import java.util.*;

public class Solution {
    public static int findMin(int[] nums) {
        int left = 0, right = nums.length - 1;

        while (left < right) {
            int mid = left + (right - left) / 2;

            if (nums[mid] < nums[right]) {
                right = mid;
            } else if (nums[mid] > nums[right]) {
                left = mid + 1;
            } else {
                right--; // handle duplicates
            }
        }
        return nums[left];
    }

    public static void main(String[] args) {
        int[] nums = {2,2,2,0,1};

        System.out.println(findMin(nums));
    }
}

Output:

0
