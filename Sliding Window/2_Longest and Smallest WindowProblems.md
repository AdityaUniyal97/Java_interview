
## Longest Substring Without Repeating Characters
**Input :** S = "abcddabac"
**Output :** 4
**Explanation :** The answer is "abcd" , with a length of 4.
```
public int longestNonRepeatingSubstring(String s) {
        int slow = 0;
        HashMap<Character,Integer> map = new HashMap<>();
        int res = 0;
        for(int right = 0 ; right < s.length() ; right++){
            char rs = s.charAt(right);
            map.put(rs,map.getOrDefault(rs , 0) + 1);
            while(map.get(rs) > 1){
                char ls = s.charAt(slow);
                map.put(ls,map.get(ls) - 1);
                if(map.get(ls) == 0){
                    map.remove(ls);
                }
                slow++;
            }
            res = Math.max(res,right-slow + 1);
        }
        return res;
    }
```

## Max Consecutive III
Input : nums = [1, 1, 1, 0, 0, 0, 1, 1, 1, 1, 0] , k = 3
Output : 10
Explanation : The maximum number of consecutive 1's are obtained only if we flip the 0's present at position 3, 4, 5 (0 base indexing).
The array after flipping becomes [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 0].
The number of consecutive 1's is 10.
```
class Solution {
    public int longestOnes(int[] nums, int k) {
        int left = 0;
        int zero = 0;
        int res = 0;
        for(int i = 0 ; i < nums.length ; i++){
            if(nums[i] == 0){
                zero++;
            }
            if(zero > k){
                if(nums[left] == 0){
                    zero--;
                }
                left++;
            }
            res = Math.max(res , i - left + 1);
        }
        return res;
    }
}
```

## Fruits into the Basket 
Input : fruits = [1, 2, 1]
Output : 3
Explanation : We will start from first tree.
The first tree produces the fruit of kind '1' and we will put that in the first basket.
The second tree produces the fruit of kind '2' and we will put that in the second basket.
The third tree produces the fruit of kind '1' and we have first basket that is already holding fruit of kind '1'. So we will put it in first basket.
Hence we were able to collect total of 3 fruits.

```
class Solution {
    public int totalFruits(int[] fruits) {
        int left = 0;
        int res = 0;
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int right = 0 ; right < fruits.length ; right++){
            map.put(fruits[right],map.getOrDefault(fruits[right],0) + 1);
            while(map.size() > 2){
                map.put(fruits[left],map.get(fruits[left]) - 1);
                if(map.get(fruits[left]) == 0){
                        map.remove(fruits[left]);
                }
                left++;
            }
            res = Math.max(res , right - left + 1);
        }
        return res;
    }
}
```