## Remove Element
s = nums = [3,2,2,3], val = 3  
Rule: if nums[i] != val → place at k → k++  
Example: [3,2,2,3] → [2,2]  
Final: k = 2

**Pattern**  
two pointer, overwrite

**Time Complexity**  
O(n)

**Space Complexity**  
O(1)

**Memory Line**  
scan + place valid elements

```java
class Solution {
    public int removeElement(int[] nums, int val) {
        int k = 0;

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != val) {
                nums[k] = nums[i];
                k++;
            }
        }

        return k;
    }
}
```

## Remove Duplicates from Sorted Array

s = nums = [1,1,2]
Rule: if nums[i] != nums[k-1] → place at k → k++
Example: [1,1,2] → [1,2]
Final: k = 2

**Pattern**
two pointer, unique check

**Time Complexity**
O(n)

**Space Complexity**
O(1)

**Memory Line**
keep unique, skip duplicates

```java id="q7n2kd"
class Solution {
    public int removeDuplicates(int[] nums) {
        int k = 1;

        for (int i = 1; i < nums.length; i++) {
            if (nums[i] != nums[k - 1]) {
                nums[k] = nums[i];
                k++;
            }
        }

        return k;
    }
}
```


## Move Zeroes

s = nums = [0,1,0,3,12]  
Rule: if nums[i] != 0 → place at k → k++ → fill rest with 0  
Example: [0,1,0,3,12] → [1,3,12,0,0]  
Final: nums = [1,3,12,0,0]

**Pattern**  
two pointer, non-zero shift

**Time Complexity**  
O(n)

**Space Complexity**  
O(1)

**Memory Line**  
move non-zero front, zero back

```java
class Solution {
    public void moveZeroes(int[] nums) {
        int k = 0;

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] != 0) {
                nums[k] = nums[i];
                k++;
            }
        }

        while (k < nums.length) {
            nums[k] = 0;
            k++;
        }
    }
}
```

## Sort Array By Parity

s = nums = [3,1,2,4]  
Rule: if even → place at k → k++  
Example: [3,1,2,4] → [2,4,_,_]  
Final: nums = [2,4,1,3]

**Pattern**  
two pointer, even front

**Time Complexity**  
O(n)

**Space Complexity**  
O(1)

**Memory Line**  
even left, odd right

```java
class Solution {
    public int[] sortArrayByParity(int[] nums) {
        int k = 0;

        for (int i = 0; i < nums.length; i++) {
            if (nums[i] % 2 == 0) {
                int temp = nums[k];
                nums[k] = nums[i];
                nums[i] = temp;
                k++;
            }
        }

        return nums;
    }
}
```


## Intersection of Two Arrays

s = nums1 = [1,2,2,1], nums2 = [2,2]
Rule: store nums1 in set → check nums2 → add common → unique
Example: [1,2,2,1] & [2,2] → [2]
Final: [2]

**Pattern**
set, intersection

**Time Complexity**
O(n)

**Space Complexity**
O(n)

**Memory Line**
use set to find common unique

```java id="k2v7nx"
import java.util.*;

class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
        Set<Integer> set1 = new HashSet<>();
        Set<Integer> result = new HashSet<>();

        for (int n : nums1) {
            set1.add(n);
        }

        for (int n : nums2) {
            if (set1.contains(n)) {
                result.add(n);
            }
        }

        int[] ans = new int[result.size()];
        int i = 0;

        for (int n : result) {
            ans[i++] = n;
        }

        return ans;
    }
}
```


## Separate Black and White Balls

s = s = "101"  
Rule: count swaps → when '1' before '0' → add distance  
Example: "101" → swaps = 1  
Final: 1

**Pattern**  
count, prefix ones

**Time Complexity**  
O(n)

**Space Complexity**  
O(1)

**Memory Line**  
count ones left, add moves for zero

```java
class Solution {
    public long minimumSteps(String s) {
        long swaps = 0;
        long ones = 0;

        for (int i = 0; i < s.length(); i++) {
            if (s.charAt(i) == '1') {
                ones++;
            } else {
                swaps += ones;
            }
        }

        return swaps;
    }
}
```

## Remove Duplicates from Sorted Array II

s = nums = [1,1,1,2,2,3]  
Rule: if nums[i] != nums[k-2] → place at k → k++  
Example: [1,1,1,2,2,3] → [1,1,2,2,3]  
Final: k = 5

**Pattern**  
two pointer, allow twice

**Time Complexity**  
O(n)

**Space Complexity**  
O(1)

**Memory Line**  
keep max two, skip extra

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums.length <= 2) return nums.length;

        int k = 2;

        for (int i = 2; i < nums.length; i++) {
            if (nums[i] != nums[k - 2]) {
                nums[k] = nums[i];
                k++;
            }
        }

        return k;
    }
}
```

## Move Pieces to Obtain a String

s = start = "*L__R__R*", target = "L______RR"
Rule: remove '_' → strings same → check L only left, R only right
Example: "*L__R__R*" → "LRR" == "LRR" → valid
Final: true

**Pattern**
two pointer, direction check

**Time Complexity**
O(n)

**Space Complexity**
O(1)

**Memory Line**
L left only, R right only

```java id="v9k2ht"
class Solution {
    public boolean canChange(String start, String target) {
        int i = 0, j = 0;
        int n = start.length();

        while (i < n || j < n) {

            // skip blanks
            while (i < n && start.charAt(i) == '_') i++;
            while (j < n && target.charAt(j) == '_') j++;

            // both should end together
            if (i == n || j == n) {
                return i == n && j == n;
            }

            // characters must match (L with L, R with R)
            if (start.charAt(i) != target.charAt(j)) return false;

            // L can only move left (so i >= j)
            if (start.charAt(i) == 'L' && i < j) return false;

            // R can only move right (so i <= j)
            if (start.charAt(i) == 'R' && i > j) return false;

            i++;
            j++;
        }

        return true;
    }
}
```


## Sort Colors

s = nums = [2,0,2,1,1,0]  
Rule: 0 → left, 2 → right, 1 → middle (3 pointers)  
Example: [2,0,2,1,1,0] → [0,0,1,1,2,2]  
Final: nums = [0,0,1,1,2,2]

**Pattern**  
three pointer, Dutch flag

**Time Complexity**  
O(n)

**Space Complexity**  
O(1)

**Memory Line**  
0 left, 2 right, 1 stay

```java
class Solution {
    public void sortColors(int[] nums) {
        int low = 0, mid = 0, high = nums.length - 1;

        while (mid <= high) {

            // if 0 → swap with low
            if (nums[mid] == 0) {
                int temp = nums[low];
                nums[low] = nums[mid];
                nums[mid] = temp;
                low++;
                mid++;
            }

            // if 1 → move mid
            else if (nums[mid] == 1) {
                mid++;
            }

            // if 2 → swap with high
            else {
                int temp = nums[mid];
                nums[mid] = nums[high];
                nums[high] = temp;
                high--;
            }
        }
    }
}
```


## String Compression

s = chars = ["a","a","b","b","c","c","c"]
Rule: count same chars → write char + count (>1)
Example: ["a","a","b","b","c","c","c"] → ["a","2","b","2","c","3"]
Final: k = 6

**Pattern**
two pointer, count group

**Time Complexity**
O(n)

**Space Complexity**
O(1)

**Memory Line**
group count, write char + freq

```java id="y4p9sd"
class Solution {
    public int compress(char[] chars) {
        int k = 0;
        int i = 0;

        while (i < chars.length) {
            char curr = chars[i];
            int count = 0;

            // count same characters
            while (i < chars.length && chars[i] == curr) {
                i++;
                count++;
            }

            // write character
            chars[k++] = curr;

            // write count if > 1
            if (count > 1) {
                String c = Integer.toString(count);
                for (int j = 0; j < c.length(); j++) {
                    chars[k++] = c.charAt(j);
                }
            }
        }

        return k;
    }
}
```

