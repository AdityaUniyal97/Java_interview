Two pointer means using the two variables to solve a problem of array or string
Two Pointer only works when the array is sorted 
```
//Two Sum (2no sum = result)
class A{
    public static void main(String args[]){
        int arr[] = {1,2,3,4,6};
        int x = 6;
        int left = 0;
        int right = arr.length - 1;
        boolean found = false;
        while(left < right){
            int sum = arr[left] + arr[right];
            if(sum == x){
                System.out.println("Pair Found: "+arr[left]+" + "arr[right]");
                found = true;
                break;
            }
            else if(sum < x){
                left++;
            }
            else{
                right--;
            }
        }
        if(!found){
            System.out.println("No Pair Found");
        }
    }
}
```

## ✅ Question 1: Valid Pair Exists?
👉 **Problem:**
You are given a **sorted array** and a target.
👉 Return **true or false**:
```
arr = [1, 2, 3, 4, 6]
target = 8
OP = true
```

## Question 2: Return Pair Index
👉 Same problem, but now:
### ❗ Return indexes instead of true/false
```
arr = [1,2,3,4,6]
target = 6
OP = 1 3
```

# Question 3 (Adjusted): Count All Pairs
## ✅ Problem
👉 Given a **sorted array**, count how many pairs have sum = target
### 🧾 Input:
arr = [1,2,3,4,5,6]  
target = 7
### ✅ Output:
3

# Question 4: Count Pairs ≤ Target
## 📥 Input
arr = [1,2,3,4,5]  
target = 6
## 📤 Output
6
```
import java.util.*;

class Solution {
    public static int countPairs(int[] arr, int target) {
        Arrays.sort(arr); // just in case
        int left = 0;
        int right = arr.length - 1;
        int count = 0;

        while (left < right) {
            if (arr[left] + arr[right] <= target) {
                count += (right - left);
                left++;
            } else {
                right--;
            }
        }

        return count;
    }

    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5};
        int target = 6;

        System.out.println(countPairs(arr, target)); // 6
    }
}
```
# Q5  Problem: Count pairs **< target**
## 🧾 Input
arr = [2,3,4,6,9]  
target = 8
## Output
3

## Q6 Squares of a Sorted Array
## 🧾 Input
arr = [-4, -1, 0, 3, 10]          ,    [-5, -4, -1, 0, 2]
## ✅ Output
[0, 1, 9, 16, 100]
```
class Solution {
    public int[] sortedSquares(int[] nums) {
        int[] res = new int[nums.length];
        int left = 0;
        int right = nums.length - 1;
        int k = nums.length - 1;
        while(left <= right){
            int ls = nums[left] * nums[left];
            int rs = nums[right] * nums[right];
            if(ls > rs){
                res[k] = ls;
                left++;
                k--;
            }
            else{
                res[k] = rs;
                right--;
                k--;
            }
        }
        return res;
    }
}
```
# Q7 3Sum — Core Pattern
## ❗ Problem
Find all triplets:
arr[i] + arr[j] + arr[k] = 0
## 🧾 Input
arr = [-1, 0, 1, 2, -1, -4]
## ✅ Output
[[-1, -1, 2], [-1, 0, 1]]
```
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        List<List<Integer>> res = new ArrayList<>();
        Arrays.sort(nums);
        for(int i = 0 ; i < nums.length - 2; i++){
            if(i > 0 && nums[i] == nums[i - 1]){
                continue;
            }
            int low = i + 1;
            int right = nums.length - 1;
            while(low < right){
                int sum = nums[i] + nums[low] + nums[right];
                if(sum == 0){
                    res.add(Arrays.asList(nums[i],nums[low],nums[right]));
                    while(low < right && nums[low] == nums[low + 1]){
                            low++;
                    }
                    while(low < right && nums[right] == nums[right - 1]){
                        right--;
                    }

                    low++;
                    right--;
                }
                else if(sum < 0){
                    low++;
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
## Q8 Container with the Most water 
```
class Solution {
    public int maxArea(int[] height) {
      int left = 0;
      int right = height.length - 1;
      int maxy = 0;
      while(left < right){
        int length = Math.min(height[left],height[right]);
        int width = right - left;
        int area = length * width;
         maxy = Math.max(area, maxy);
        if(height[left]<height[right]){
            left++;
        }
        else{
            right--;
        }
      }
      return maxy;  
    }
}
```
# Q9 Two Sum II - Input Array Is Sorted  = Index return
- return the actual values
- Return true or false

# Q10 Four Sum
```
class Solution {
    public List<List<Integer>> fourSum(int[] nums, int target) {
        List<List<Integer>> ans = new ArrayList<>();
        Arrays.sort(nums);
        int n = nums.length;
        for(int i = 0 ; i < n - 3 ; i++){
            if(i > 0 && nums[i] == nums[i - 1]){
                continue;
            }
            for(int j = i + 1 ; j < n - 2 ; j++){
                if(j > i + 1 && nums[j] == nums[j - 1]){
                    continue;
                }
                int low = j + 1;
                int right = nums.length - 1;
                while(low < right){
                    long sum = (long)nums[i]+nums[j]+nums[low]+nums[right];
                    if(sum==target){
                        ans.add(Arrays.asList(nums[i],nums[j],nums[low],nums[right]));
                        while(low < right && nums[low] == nums[low + 1]){
                            low++;
                        }
                        while(low < right && nums[right] == nums[right - 1]){
                            right--;
                        }
                        low++;
                        right--;
                    }
                    else if(sum < target){
                        low++;
                    }
                    else{
                        right--;
                    }
                }
            }
        }
        return ans;
    }
}
```


# 3 SUM closest
```
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);
        int close = nums[0] + nums[1] + nums[2];
        for(int i = 0 ; i < nums.length - 2; i++){
            int left = i + 1;
            int right = nums.length - 1;
            while(left < right){
                int sum = nums[i] + nums[left] + nums[right];
                if(Math.abs(sum-target) < Math.abs(target-close)){
                    close = sum;
                }
                if(sum < target){
                    left++;
                }
                else{
                    right--;
                }
            }
        }
        return close;
    }
}
```