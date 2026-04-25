## Merge the two Sorted Array
**Input:** nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
**Output:** [1,2,2,3,5,6]
```
class Solution {

    public void merge(int[] nums1, int m, int[] nums2, int n) {

        int i = m-1 , j=n-1 , k=m+n-1;

        while(i >= 0 && j >= 0){

            if(nums1[i] > nums2[j]){

                nums1[k--] = nums1[i--];

            }

            else{

                nums1[k--] = nums2[j--];

            }

        }

        while(j >= 0){

            nums1[k--] = nums2[j--];

        }

    }

}
```

## Sort the Array BY Parity
**Input:** nums = [3,1,2,4]
**Output:** [2,4,3,1]
**Explanation:** The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
```
class Solution {
    public int[] sortArrayByParity(int[] nums) {
        int j = 0;
        for(int i = 0 ; i < nums.length ; i++){
            if(nums[i] % 2 == 0){
                int temp = nums[i];
                nums[i] = nums[j];
                nums[j] = temp;
                j++;
            }
        }
        return nums;
    }
}
```
## sort the Array by Parity II
**Input: nums = [4,2,5,7]
Output: [4,5,2,7]
Explanation: [4,7,2,5], [2,5,4,7], [2,7,4,5] would also have been accepted.**
```
class Solution {
    public int[] sortArrayByParityII(int[] nums) {
        int[] res = new int[nums.length];
        int even = 0;
        int odd = 1;
        for(int i = 0 ; i < nums.length ; i++){
            if(nums[i] % 2 == 0){
                res[even] = nums[i];
                even += 2;
            }
            else{
                res[odd] = nums[i];
                odd += 2;
            }
        }
        return res;
    }
}
```

**Dry Run**
```
Input:
[4,2,5,7]

Step:
4 → even → index 0
2 → even → index 2
5 → odd → index 1
7 → odd → index 3

Final:
[4,5,2,7]
```

## Rearrage the Array Element by Sign
**Input: nums = [3,1,-2,-5,2,-4]
Output: [3,-2,1,-5,2,-4]**
```
class Solution {
    public int[] rearrangeArray(int[] nums) {
        int res[] = new int[nums.length];
        int pos = 0;
        int neg = 1;
        for(int i = 0 ; i < nums.length ; i++){
            if(nums[i] > 0){
                res[pos] = nums[i];
                pos += 2;
            }
            else{
                res[neg] = nums[i];
                neg += 2;
            }
        }
        return res;
        
    }
}
```

Dry Run
```
Input: [3,1,-2,-5,2,-4]

Steps:
3 → pos → index 0
1 → pos → index 2
-2 → neg → index 1
-5 → neg → index 3
2 → pos → index 4
-4 → neg → index 5
```

## Remove the Dupplicates from the Array
**Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]**
```
class Solution {
    public int removeDuplicates(int[] nums) {
        int i = 0;
        for(int j = 1 ; j < nums.length ; j++){
            if(nums[i] != nums[j]){
                i++;
                nums[i] = nums[j];
            }
        }
        return i + 1;
    }
}
```

## Remove the Given Element from the Array
```
class Solution {
    public int removeElement(int[] nums, int val) {
        int i = 0;
        for(int j = 0 ; j < nums.length ; j++){
            if(nums[j] != val){
                nums[i] = nums[j];
                i++;
            }
        }
        return i;
    }
}
```

## Partiition Array Accordin to Given Pivot
**Input: nums = [9,12,5,10,14,3,10], pivot = 10
Output: [9,5,3,10,10,12,14]**
```
class Solution {
    public int[] pivotArray(int[] nums, int pivot) {
        ArrayList<Integer> small = new ArrayList<>();
        ArrayList<Integer> equal = new ArrayList<>();
        ArrayList<Integer> large = new ArrayList<>();
        for(int x : nums){
            if(x < pivot){
                small.add(x);
            }
            else if(x == pivot){
                equal.add(x);
            }
            else{
                large.add(x);
            }
        }
        int[] res = new int[nums.length];
        int i = 0;
        for(int x : small){
            res[i] = x;
            i++;
        }
        for(int x : equal){
            res[i] = x;
            i++;
        }
        for(int x : large){
            res[i] = x;
            i++;
        }
        return res;
    }
}
```

Dry Run 
```
nums = [9,12,5,10,14,3,10]
pivot = 10

small → [9,5,3]
equal → [10,10]
large → [12,14]

final:
[9,5,3,10,10,12,14]
```

## Rotate Array
**Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]**
```
class Solution {
    public void reverse(int[] nums , int left , int right){
        while(left < right){
            int temp = nums[left];
            nums[left] = nums[right];
            nums[right] = temp;
            left++;
            right--;
        }
    }
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        k = k % n; // For Handling the LArge Input
        reverse(nums , 0 , n - 1);
        reverse(nums , 0 , k - 1);
        reverse(nums , k , n - 1);
    }
}
```

## Apply Operations to an Array
**For every index i:
if nums[i] == nums[i+1]
double it → nums[i] = nums[i] * 2
make next zero → nums[i+1] = 0
**After that → move all 0s to end**
```
class Solution {

    public int[] applyOperations(int[] nums) {

        int n = nums.length;

        //Rule

        for(int i = 0 ; i < n - 1; i++){

            if(nums[i] == nums[i + 1]){

                nums[i] = nums[i] * 2;

                nums[i + 1] = 0;

            }

        }

        // Move Zero to End

        int i = 0;

        for(int j = 0 ; j < nums.length ; j++){

            if(nums[j] != 0){

                int temp = nums[j];

                nums[j] = nums[i];

                nums[i] = temp;

                i++;

            }

        }

        return nums;

    }

}
```

## Two Sum
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int i = 0 ; i < nums.length ; i++){
            int need = target - nums[i];
            if(map.containsKey(need)){
                return new int[]{map.get(need),i};
            }
            map.put(nums[i],i);
        }
        return new int[]{-1, -1};
    }
}
```

## Three Sum
```
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        for(int i = 0 ; i < nums.length ; i++){
            if(i > 0 && nums[i] == nums[i - 1]) continue;
            int l = i + 1;
            int r = nums.length - 1;
            while(l < r){
                int sum = nums[i] + nums[l] + nums[r];
                if(sum == 0){
                    res.add(Arrays.asList(nums[i],nums[l],nums[r]));
                    while(l < r && nums[l] == nums[l+1]) l++;
                    while(l < r && nums[r] == nums[r-1]) r--;
                    l++;
                    r--;
                }
                else if(sum < 0){
                    l++;
                }
                else{
                    r--;
                }
            }
        }
        return res;
    }
}
```

## Closest 3Sum 
```
class Solution {
    public int threeSumClosest(int[] nums, int target) {
        Arrays.sort(nums);
        int close = nums[0] + nums[1] + nums[2];
        for(int i = 0 ; i < nums.length ; i++){
            int l = i + 1;
            int r = nums.length - 1;
            while(l < r){
                int sum = nums[i] + nums[l] + nums[r];
                if(Math.abs(target - sum) < Math.abs(target - close)){
                    close = sum;
                }
                if(sum < target){
                    l++;
                }
                else if(sum > target){
                    r--;
                }
                else{    // exact sum
                    return sum;
                }
            }
        }
        return close;
    }
}
```

## 4 SUm
```
class Solution {
    public List<List<Integer>> fourSum(int[] nums, int target) {
        Arrays.sort(nums);
        List<List<Integer>> res = new ArrayList<>();
        for(int i = 0 ; i < nums.length ; i++){
            if(i > 0 && nums[i] == nums[i - 1]) continue;
            for(int j = i + 1; j < nums.length ; j++){
                if(j > i+1 && nums[j] == nums[j - 1]) continue;
                int l = j + 1;
                int r = nums.length - 1;
                while(l < r){
                    long sum = (long)nums[i]+nums[l]+nums[r]+nums[j];
                    if(sum == target){
                        res.add(Arrays.asList(nums[i],nums[j],nums[l],nums[r]));
                        while(l<r && nums[l] == nums[l + 1]) l++;
                        while(l<r && nums[r] == nums[r - 1]) r--;
                        l++;
                        r--;
                    }
                    else if(sum < target) l++;
                    else r--;
                }
            }
        }
        return res;
    }
}
```

## Sort the Colors
**Input: nums = [2,0,2,1,1,0]
Output: [0,0,1,1,2,2]**
```
class Solution {
    public void sortColors(int[] nums) {
        int low=  0;
        int mid = 0;
        int high = nums.length - 1;
        while(mid <= high){
            if(nums[mid] == 0){
                int temp = nums[low];
                nums[low] = nums[mid];
                nums[mid] = temp;
                low++;
                mid++;
            }
            else if(nums[mid] == 1){
                mid++;
            }
            else{
                int temp = nums[mid];
                nums[mid] = nums[high];
                nums[high] = temp;
                high--;
            }
        }
    }
}
```
## Container with the Most Water
```
class Solution {
    public int maxArea(int[] height) {
        int left = 0;
        int right = height.length - 1;
        int max = 0;
        while(left < right){
            int h = Math.min(height[left],height[right]);
            int width = right - left;
            int area = h * width;
            if(area > max){
                max = area;
            }
            if(height[left] < height[right]){
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

## NExt Permutation
**Input: nums = [1,2,3]
Output: [1,3,2]**
```
class Solution {
    public void nextPermutation(int[] nums) {
        int n = nums.length;
        int i;
        for(i = n - 2; i >= 0 ; i--){
            if(nums[i] < nums[i + 1]){
                break;
            }
        }  
        if(i >= 0){
            for(int j = n-1; j > i; j--){
                if(nums[j] > nums[i]){
                    int temp = nums[i];
                    nums[i] = nums[j];
                    nums[j] = temp;
                    break;
                }
            }
        }
        int l = i + 1 , r = n - 1;
        while(l < r){
            int temp = nums[l];
            nums[l] = nums[r];
            nums[r] = temp;
            l++;
            r--;
        }
    }
}
```
Dry Run
```
[1,3,2]
start i = 1 (n-2)
check → 3 < 2 ❌
move left
i = 0
check → 1 < 3 ✔

→ i = 0

--------------------------------

find number > 1 from right
j = 2 → 2 > 1 ✔
swap nums[i] and nums[j]
→ [2,3,1]

--------------------------------

reverse right side (i+1 to end)
right part = [3,1]
reverse → [1,3]

--------------------------------

final → [2,1,3]
```

