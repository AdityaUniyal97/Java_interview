
```
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int ans[] = new int[n];
        ans[0] = 1;
        for(int i = 1; i < n ; i++){
            ans[i] = ans[i - 1] * nums[i - 1];
        }
        int right = 1;
        for(int i = n - 1; i >= 0 ; i--){
            ans[i] = ans[i] * right;
            right = right * nums[i];
        }
        return ans;
    }
}
```

## Trapping the Rainwater 
```
class Solution {
    public int trap(int[] height) {
        int n = height.length;
        int lm[] = new int[n];
        int rm[] = new int[n];
        lm[0] = height[0];
        for(int i = 1 ; i < n ; i++){
            lm[i] = Math.max(lm[i - 1] , height[i]);
        }
        rm[n - 1] = height[n - 1];
        for(int i = n - 2 ; i >= 0 ; i--){
            rm[i] = Math.max(rm[i + 1] , height[i]);
        }
        int count = 0;
        for(int i= 0 ; i < n ; i++){
            count += Math.min(lm[i],rm[i]) - height[i];
        }
        return count;
    }
}
```

## Longest Mountain in the Array
**Input: arr = [2,1,4,7,3,2,5]
Output: 5
Explanation: The largest mountain is [1,4,7,3,2] which has length 5.**
```
class Solution {
    public int longestMountain(int[] arr) {
        int n = arr.length;
        int maxLen = 0;
        for(int i = 1; i < n  - 1; i++){
            if(arr[i] > arr[i - 1] && arr[i] > arr[i + 1]){
                int left = i;
                int right = i;
                while(left > 0 && arr[left] > arr[left - 1]){
                    left--;
                }
                while(right < n - 1 && arr[right] > arr[right + 1]){
                    right++;
                }
                int len = right - left + 1;
                maxLen = Math.max(maxLen , len);
            }
        }   
        return maxLen;
    }
}
```