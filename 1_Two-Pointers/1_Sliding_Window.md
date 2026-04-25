### Max Sum Subarray of size K
**Input:** arr[] = [100, 200, 300, 400], k = 2
**Output:** 700
**Explanation:** arr2 + arr3 = 700, which is maximum.
```
class Solution {
    public int maxSubarraySum(int[] arr, int k) {
        // Code here
        int sum = 0;
        for(int i = 0 ; i < k ; i++){
            sum += arr[i];
        }
        int maxsum = sum;
        for(int i = k ; i < arr.length ; i++){
            sum += arr[i];
            sum -= arr[i - k];
            maxsum = Math.max(maxsum ,  sum);
        }
        return maxsum;
    }
}
```

### Max Consecutive Ones
**Input:** nums = [1,1,0,1,1,1]
**Output:** 3
```
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int count= 0;
        int max = 0;
        for(int x : nums){
            if(x == 1){
                count++;
                max = Math.max(max , count);
            }
            else{
                count = 0;
            }
        }
        return max;
    }
}
```

### Ma Conseutive Ones III
**Input:** nums = [1,1,1,0,0,0,1,1,1,1,0], k = 2
**Output:** 6
```
class Solution {
    public int longestOnes(int[] arr, int k) {
        int left = 0;
        int zero = 0;
        int max = 0;
        for(int right = 0 ; right < arr.length ; right++){
            if(arr[right] == 0) zero++;
            while(zero > k){
                if(arr[left] == 0) zero--;
                left++;
            }
            max = Math.max(max , right - left + 1);
        }
        return max;
    }
}
```

### Subarray Product Less Than K
**Input:** nums = [10,5,2,6], k = 100
**Output:** 8
**Explanation:** The 8 subarrays that have product less than 100 are:
[10], [5], [2], [6], [10, 5], [5, 2], [2, 6], [5, 2, 6]
```
class Solution {
    public int numSubarrayProductLessThanK(int[] nums, int k) {
        if(k <= 1) return 0;
        int left = 0;
        int prod = 1;
        int count = 0;
        for(int right = 0 ; right < nums.length ; right++){
            prod = prod * nums[right];
            while(prod >= k){
                prod = prod / nums[left];
                left++;
            }
            count += (right - left + 1);
        }
        return count;
    }
}
```

### Fruits into basket
**Input:** fruits = [1,2,1]
**Output:** 3
**Explanation:** We can pick from all 3 trees.
```
class Solution {
    public int totalFruit(int[] fruits) {
        Map<Integer,Integer> map = new HashMap<>();
        int left = 0 , max = 0;
        for(int right = 0 ; right < fruits.length ; right++){
            map.put(fruits[right],map.getOrDefault(fruits[right],0)+1);
            while(map.size() > 2){
                map.put(fruits[left],map.get(fruits[left]) - 1);
                if(map.get(fruits[left]) == 0){
                    map.remove(fruits[left]);
                }
                left++;
            }
            max = Math.max(max , right - left + 1);
        }
        return max;
    }
}
```

### Minimum Size Subarray Sum
**Input:** target = 7, nums = [2,3,1,2,4,3]
**Output:** 2
**Explanation:** The subarray [4,3] has the minimal length under the problem constraint.
