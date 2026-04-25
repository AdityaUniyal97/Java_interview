## Max Sum Subarray of size K
**Input: arr[] = [100, 200, 300, 400], k = 2
Output: 700
Explanation: arr2 + arr3 = 700, which is maximum.**
```
class Solution {
    public int maxSubarraySum(int[] arr, int k) {
        // Code here
        int ws = 0;
        for(int i = 0 ; i < k ; i++){
            ws += arr[i];
        }
        int ms = ws;
        for(int i = k ; i < arr.length ; i++){
            ws += arr[i];
            ws -= arr[i - k];
            ms = Math.max(ms , ws);
        }
        return ms;
    }
}
```

## Max Consecutive Ones
**1 1 0 1 1 1
↑ ↑     ↑ ↑ ↑
count → 2 reset → 0 → then → 3 **
```
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int count = 0;
        int max = 0;
        for(int i = 0 ; i < nums.length ; i++){
            if(nums[i] == 1){
                count++;
                max = Math.max(count , max);
            }
            else{
                count = 0;
            }
        }
        return max;
    }
}
```

## Max Consecutive Ones III
**Input: nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
Output: 6
Explanation: [1,1,1,0,0,1,1,1,1,1,1]**
```
class Solution {
    public int longestOnes(int[] nums, int k) {
        int left = 0;
        int zero = 0;
        int max = 0;
        for(int right = 0 ; right < nums.length ; right++){
            if(nums[right] == 0) zero++;
            while(zero > k){
                if(nums[left] == 0) zero--;
                left++;
            }
            max = Math.max(max,right - left + 1);
        }
        return max;
    }
}
```

## Subarray Less than the K
**Input: nums = [10,5,2,6], k = 100
Output: 8
Explanation: The 8 subarrays that have product less than 100 are:
[10], [5], [2], [6], [10, 5], [5, 2], [2, 6], [5, 2, 6]**
```
class Solution {
    public int numSubarrayProductLessThanK(int[] nums, int k) {
       if(k <= 1) return 0;
       int left = 0;
       int product = 1;
       int count = 0;
       for(int right = 0 ; right < nums.length ; right++){
        product *= nums[right];
        while(product >= k){
            product /= nums[left];
            left++;
        }
        // How Many Subarrays at the end
        count += (right - left + 1);
       } 
       return count;
    }
}
```

## Fruits into the Baskets
**fruits = [1,2,3,2,2]
1 2 → ok
1 2 3 → ❌ → remove 1
→ 2 3 → ok
→ 2 3 2 → ok
→ 2 3 2 2 → ok ✅ (max = 4)**
```
class Solution {
    public int totalFruit(int[] nums) {
        int left = 0;
        int max = 0;
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int right = 0 ; right < nums.length ; right++){
            map.put(nums[right],map.getOrDefault(nums[right],0) + 1);
            while(map.size() > 2){
                map.put(nums[left],map.get(nums[left]) - 1);
                if(map.get(nums[left]) == 0){
                    map.remove(nums[left]);
                }
                left++;
            }
            max = Math.max(max , right - left + 1);
        }
        return max;
    }
}
```

## Minimum Size Subarray Sum
**Input: target = 7, nums = [2,3,1,2,4,3]
Output: 2
Explanation: The subarray [4,3] has the minimal length**
```
class Solution {
    public int minSubArrayLen(int target, int[] nums) {
        int min = Integer.MAX_VALUE;
        int left = 0;
        int sum = 0;
        for(int right = 0 ; right < nums.length ; right++){
            sum += nums[right];
            while(sum >= target){
                min = Math.min(min , right - left + 1);
                sum -= nums[left];
                left++;
            }
        }
        return min == Integer.MAX_VALUE ? 0 : min;
    }
}
```

## Subarray with K Different Integers
**Input: nums = [1,2,1,2,3], k = 2
Output:**

**Valid subarrays with exactly 2 distinct:
[1,2]
[1,2,1]
[1,2,1,2]
[2,1]
[2,1,2]
[1,2]
[2,3]**
```
class Solution {
    public int subarraysWithKDistinct(int[] nums, int k) {
        return helper(nums , k) - helper(nums , k - 1);
    }
    private int helper(int[] nums , int k){
        int left = 0;
        int count = 0;
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int right = 0 ; right < nums.length ; right++){
            map.put(nums[right],map.getOrDefault(nums[right],0) + 1);
            while(map.size() > k){
                map.put(nums[left],map.get(nums[left]) - 1);
                if(map.get(nums[left]) == 0){
                    map.remove(nums[left]);
                }
                left++;
            }
            count += (right - left + 1);
        }
        return count;
    }
}
```

## Substrings of Size Three with Distinct Characters
**Input: s = "xyzzaz"
Output: 1**
**xyz → ✅ (all distinct)
yzz → ❌
zza → ❌
zaz → ❌**
```
class Solution {
    public int countGoodSubstrings(String s) {
        int count = 0;
        for(int i = 0 ; i <= s.length() - 3; i++){
            char a = s.charAt(i);
            char b = s.charAt(i + 1);
            char c = s.charAt(i + 2);
            if(a != b && b != c && a != c){
                count++;
            }
        }
        return count;
    }
}
```