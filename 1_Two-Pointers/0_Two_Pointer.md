### Move zeroes to the End of the Array
```
class Solution {
    public void moveZeroes(int[] nums) {
        int slow = 0;
        for(int fast = 0 ; fast < nums.length ; fast++){
            if(nums[fast] != 0){
                int temp = arr[slow];
                arr[slow] = arr[fast];
                arr[fast] = temp;
                slow++;
            }
        }
    }
}
```

### Two Sum ii - Input Array is Sorted
**Input:** numbers = [2,7,11,15], target = 9
**Output:** [1,2]
```
class Solution {
    public int[] twoSum(int[] arr, int target) {
        int left = 0;
        int right = arr.length - 1;
        while(left < right){
            int sum = arr[left] + arr[right];
            if(sum == target){
                return new int[]{left , right};
            }
            else if(sum < target){
                left++;
            }
            else{
                right--;
            }
        }
        return new int[]{-1,-1};
    }
}
```

### 3 Sum
```
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        for(int i = 0 ; i < nums.length - 2; i++){
            if(i > 0 && nums[i] == nums[i - 1]) continue;
            int left = i + 1;
            int right = nums.length - 1;
            while(left < right){
                int sum = nums[i]+nums[left]+nums[right];
                if(sum == 0){
                    res.add(Arrays.asList(nums[i],nums[left],nums[right]));
                    while(left < right && nums[left] == nums[left + 1]) left++;
                    while(left > right && nums[right] == nums[right - 1]) right--;
                    left++;
                    right--;
                }
                else if(sum < 0){
                    left++;
                }
                else{
                    right--;
                }
            }
        }
        return res;
    }
}
```

### Sort The Colors
Input: nums = [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]
```
class Solution {
    public void sortColors(int[] arr) {
        int low = 0;
        int mid = 0;
        int high = arr.length - 1;
        while(mid <= high){
            if(arr[mid] == 0){
                swap(arr,low,mid);
                low++;
                mid++;
            }
            else if(arr[mid] == 1){
                mid++;
            }
            else{
                swap(arr,high,mid);
                high--;
            }
        }
    }
    static void swap(int[]arr,int i,int j){
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }
}
```

### Container with the Most Water
![[Pasted image 20260424204005.jpg]]
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7].
```
class Solution {
    public int maxArea(int[] arr) {
        int left = 0;
        int right = arr.length - 1;
        int max = 0;
        while(left < right){
            int area = Math.min(
                arr[left],arr[right]) * (right - left);
            max = Math.max(max,area);
            if(arr[left] < arr[right]){
                left++;
            }
            else{
                right--;
            }
        }
        return max;
    }
}
```

### Trapping the Rain Water
![](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg)

**Input:** height = [1,8,6,2,5,4,8,3,7]
**Output:** 49
```
class Solution {
    public int trap(int[] arr) {
        int left = 0, right = arr.length - 1;
        int leftMax = 0;
        int rightMax = 0;
        int water = 0;
        while (left < right) {
            if (arr[left] < arr[right]) {
                if (arr[left] >= leftMax) {
                    leftMax = arr[left];
                }
                else{
                    water += leftMax - arr[left];
                }
                left++;
            }
            else{
                if(arr[right] >= rightMax){
                    rightMax = arr[right];
                }
                else{
                    water += rightMax - arr[right];
                }
                right--;
            }
        }
        return water;
    }
}
```