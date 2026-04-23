## Left and Right Sum Difference
**Input: nums = [10,4,8,3]
Output: [15,1,11,22]**
```
class Solution {
    public int[] leftRightDifference(int[] nums) {
        int n = nums.length;
        int[] res = new int[n];
        for(int i = 0 ; i < n ; i++){
            int lsum = 0;
            int rsum = 0;
            for(int j = 0 ; j < i ; j++){
                lsum += nums[j];
            }
            for(int k = i + 1 ; k < n ; k++){
                rsum += nums[k];
            }
            res[i] = Math.abs(lsum -rsum);
        }
        return res;
    }
}
```