
# Simple Problems 
# Easy

# Largest Element in the Array
Time Complexity = O(n)
Space = O(1)
```
class Solution {
    public static int largest(int[] arr) {
        int max = arr[0];
        for(int i =1 ; i < arr.length ; i++){
            if(arr[i] > max){
                max = arr[i];
            }
        }
        return max;
    }
}
```

# Second_largest 
Time-Complxity = O(n)
Space-Compleixty = O(1)
```
class Solution {
    public int getSecondLargest(int[] arr) {
        if(arr.length < 2){
            return - 1;
        }
        int large = Integer.MIN_VALUE;
        int second = Integer.MIN_VALUE;
        for(int i = 0 ; i < arr.length ;i++){
            if(arr[i] > large){
                second = large;
                large = arr[i];
            }
            else if(arr[i] > second && arr[i] != large){
                second = arr[i];
            }
        }
        return (second == Integer.MIN_VALUE) ? -1 : second;
    }
}
```

# Remove Elements(inplace = no extra variable allowed)
```
class Solution {
    public int removeElement(int[] nums, int val) {
        int index = 0;
        for(int i = 0 ; i < nums.length ; i++){
            if(nums[i] != val){
                nums[index] = nums[i];
                index++;
            }
        }
        return index;
    }
}
```

# Check if Array is Sorted and Rotated
```
class Solution {
    public boolean check(int[] nums) {
        int count = 0;
        for(int i = 0 ; i < nums.length - 1 ; i++){
            if(nums[i] > nums[ i + 1]){
                count++;
            }
        }    
            if(count == 0){
                return true;
            }
            else if(count == 1){
                return nums[nums.length - 1] <= nums[0];
            }
            else{
                return false;
            }
        }
    }
```

# Remove the Duplicates from the Array
```
class Solution {
    public int removeDuplicates(int[] nums) {
        if(nums.length == 0){
            return 0;
        }
        int i = 0 ;
        for(int j = 1 ; j < nums.length ;j++){
            if(nums[j] != nums[i]){
                i++;
                nums[i] = nums[j];
            }
        }
        return i + 1;
    }
}
```

# Rotate a Array
```
class Solution {
    public void rotate(int[] nums, int k) {
        int n = nums.length;
        k = k % n;
        reverse(nums , 0 , n - 1);
        reverse(nums , 0 , k - 1);
        reverse(nums , k , n - 1);
    }
    public void reverse(int[] nums , int start , int end){
        while(start < end){
            int temp = nums[start];
            nums[start] = nums[end];
            nums[end] = temp;
            start++;
            end--;
        }
    }
}
```

# Move Zeroes to the END
Time Complexity = O(n) one pass to move non zeros and another pass to fill zeroes
Space Complexity = O(1)
```
class Solution {
    public void moveZeroes(int[] nums) {
        int i =0 ;
        for(int j = 0 ; j < nums.length ; j++){
            if(nums[j] != 0){
                nums[i] = nums[j];
                i++;
            }
        }

        while(i < nums.length){
            nums[i] = 0;
            i++;
        }
    }
}
```
# Union of two sorted Array ?
```
 class Solution 
{
    public static ArrayList<Integer> findUnion(int a[], int b[]) {
        ArrayList<Integer> r = new ArrayList<Integer>();
        int i = 0;
        int j = 0;
        int n = a.length;
        int m = b.length;
        while(i < n && j < m){
            if(a[i] < b[j]){
                if(r.isEmpty() || r.get(r.size() - 1) != a[i]){
                  r.add(a[i]);
                }  
                i++;
            }
            else if(a[i] > b[j]){
                if(r.isEmpty() || r.get(r.size() - 1) != b[j]){
                  r.add(b[j]);
                }
                j++;
            }
            else{
                if(r.isEmpty() || r.get(r.size() - 1) != a[i]){
                    r.add(a[i]);
                }
                i++;
                j++;
            }
        }
        // if elements left
        while(i < n){
            if(r.isEmpty() || r.get(r.size() - 1) != a[i]){
               r.add(a[i]);
            }
            i++;
        }
        while(j < m){
            if(r.isEmpty() || r.get(r.size() - 1) != b[j]){
            r.add(b[j]);
            }
            j++;
        }
        return r;
    }
}
```

# Missing Number
Time Compleixty : 1st loop (n + 1) times => O(n)
                 2nd loop (n) times => O(n)
               Total => O(n) + O(n) = O(n)
Space Complexity : O(1)
```
class Solution {
    public int missingNumber(int[] nums) {
        int n = nums.length;
        int xor = 0;
        for(int i = 0 ; i <= n ; i++){
            xor ^= i;
        }
        for(int num : nums){
            xor ^= num;
        }
        return xor;
    }
}
```

# Maximum Consecutive Ones ?
Time Compleixty : The loop iterate through the array one (O(n))
Space Compleixty : O(1)
```
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        int mCC = 0;
        int CC = 0;
        for(int num : nums){
            if(num == 1){
                CC++;
                mCC = Math.max(mCC , CC);
            }
            else{
                CC = 0;
            }
        }
        return mCC;
    }
}
```

# Find the single non repeating element in the Non Repeating
Ex = [2,2,2,1] op = 1
Time Complexity = O(n)
Space Compleixty = O(1)
```
class Solution {
    public int singleNumber(int[] nums) {
        int xor = 0;
        for(int num : nums){
            xor ^= num;
        }
        return xor;
    }
}
```

# Longest SubArray with Sum K
Time Complexity = O(n);
Sapce Complexity = O(n);
Since the loop will always run till the n which is O(n) time and keep storing items in the map until n that is O(n)
```
    public int longestSubarray(int[] arr, int k) {
        HashMap<Integer , Integer> prefixMap = new HashMap<>();
        int sum= 0;
        int maxLength = 0;
        for(int i = 0; i < arr.length ; i++){
            sum += arr[i];
            if(sum == k){
                maxLength = i + 1;
            }
            if(prefixMap.containsKey(sum - k)){
                maxLength = Math.max(maxLength ,i - prefixMap.get(sum - k));
            }
            if(!prefixMap.containsKey(sum)){
                prefixMap.put(sum, i);
            }
        }
        return maxLength;
    }
}
```

# Two Sum
Time Complexity = O(n)
Space Complexity = O(n)
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer , Integer> map = new HashMap<>();
        for(int i = 0 ; i < nums.length; i ++){
            int comp = target - nums[i];
            if(map.containsKey(comp)){
               return new int[]{map.get(comp) , i};
        }
         map.put(nums[i] , i);
        }
        return new int[]{-1 , -1};
    }
}
```

# Sort Colors
Ip = [2 , 0, 2, 1, 1, 0]  , OP = [0, 0, 1, 1, 2, 2]
Time Complexiyt : O(n)
Space Complexity : O(1)
```
class Solution {
    public void sortColors(int[] nums) {
        int low = 0;
        int high = nums.length- 1;
        int mid = 0;
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
                int temp = nums[high];
                nums[high] = nums[mid];
                nums[mid] = temp;
                high--;
            }
        }
    }
}
```

# Majority Element
Time Complexity : O(n)
Space Compleixty : O(1)
```
class Solution {
    public int majorityElement(int[] nums) {
        int candi = 0;
        int count  = 0;
        for(int num : nums){
            if(count == 0){
                candi = num;
           }
           if(num == candi){
            count++;
           }
           else{
            count--;
           }
        }
        return candi;
    }
}
```

# Maximum Sub array
Time Complexity  = O(n)
Space Complexity = O(1)
```
class Solution {
    public int maxSubArray(int[] nums) {
        int curr = nums[0];
        int maxSum = nums[0];
        for(int i = 1 ; i < nums.length; i++){
            curr = Math.max(nums[i] , curr + nums[i]);
            maxSum = Math.max(maxSum , curr);
        }
        return maxSum;
    }
}
```



