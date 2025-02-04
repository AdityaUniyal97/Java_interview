# Sorting

# Selection Sort ?
*Selection SOrt is a sorting algorithm where we find the smallest element or the largest element based upon the sorting order than we place them one by one in unsorted part of the array . 
Time Complexity = O(n^2) 
Space Complexity = O(1) (No extra memeory is used)*
```
class Solution {
    void selectionSort(int[] arr) {
        int n = arr.length;
        for(int i = 0 ; i <n ; i++){
            int MI = i;
            for(int j = i+1 ; j < n ; j++){
                if(arr[j] < arr[MI]){
                    MI = j;
                }
            }

            int swap = arr[MI];
            arr[MI] = arr[i];
            arr[i] = swap;
        }
    }
}
```

# What is Bubble Sort ?
*Bubble Sort is a sorting algorithm which repeatedly compares the adjacent element  int the array . Swap them if they are in the wrong order . this process repeat until the array is fully sorted
Tme-Complexity = O(n^2)
Space-Complexity = O(1) (no extra memory is used)*
```
class Solution {
    public static void bubbleSort(int arr[]) {
        int n = arr.length;
        for(int i =0 ; i < n ; i ++){
            boolean swap = true;
            for(int j = 0 ; j < n - i - 1; j++){
                if(arr[j] > arr[j + 1]){
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swap = true;
                }
            }
            if(swap == false){
                break;
            }
        }
    }
}
```
# Insertion Sort ?
*In Insert Sort we Divide our array into two Parts Sorted and Unsorted Part , SO we pick the first element from the unsorted part and put it in its specific position at the sorted part . Repeating this process until the array is completely sorted
Time Complexity 
**BEST CASE** When the entire array is Sorted in that case the while loop will never run and only outer loop will run until n to check  in that case **O(n)**
**Worst Case** When the entire array is sorted in reverse . this means we have to travel the whole loop and also the while loop will also run on every element that will be **O(n^2)**
**Space Complexity = O(1) Since it does not Require Additional Space***
```
class Solution {
    public void insertionSort(int arr[]) {
        int n = arr.length;
        for(int i = 1 ; i < n ; i ++){
            int key = arr[i];
            int j = i - 1;
            while(j >= 0 && arr[j] > key){
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }
    }
}
```

# Merge Sort ?
Merge Sort is  a divide-and-conquer sorting algorithm that:
1. Divide
   - Split the array into two halves left and right
2. Conquer
   - Recursively sort the left and right halves.
3. Combine
   - Merge the two sorted halves into a single sorted array. 
```
class Solution {

    void mergeSort(int arr[], int l, int r) {
        if(l < r){
        int mid = l + (r - l) / 2;
        mergeSort(arr , l , mid);
        mergeSort(arr , mid + 1, r);
        merge(arr , l , mid , r);
       }
    }
    
    private void merge(int[] arr , int left , int mid , int right){
        int n1 = mid - left + 1;
        int n2 = right - mid;
        int[] LA = new int[n1];
        int[] RA = new int[n2];
        for(int i =0 ; i < n1; i++){
            LA[i] = arr[left +  i];
        }
        for(int j = 0 ; j < n2 ; j++){
            RA[j] = arr[mid + 1 + j];
        }
        int i = 0;
        int j = 0;
        int k = left;
        while(i < n1 && j < n2){
            if(LA[i] <= RA[j]){
                arr[k] = LA[i];
                i++;
            }
            else{
                arr[k] = RA[j];
                j++;
            }
            k++;
        }
        while(i < n1){
            arr[k] = LA[i];
            i++;
            k++;
        }
        while(j < n2){
            arr[k] = RA[j];
            j++;
            k++;
        }
    }
```

#  Quick_Sort?
*Quick Sort is a divide and conquer shorting algorithm . Where we choose the pivot element and divide the array such that those array element which are lesser than the pivot comes one side and those greter than the pivot comes other side . Function name as the Partition_Function which mantian the order*
**Time Complexity**
- *Best case(O (n log n)) = When the perfect pivot is choosen such that the array is completely  divided in halfes , such that array gets half every time which means  = **log n** ,  and the loop will run complete and do **n** comparison , recursion log n dpeth  so space = O(log n)
- *Average case(O(n log n)) = Random input will also divide the array in halves so same time complexity like best case*
- *Worst Case(O(n<sup>2</sup>)) = when every time the pivot is either the smallest or either the largest  , Which means the loop everytime just get one element smaller and loop will run ***n** times , and the total comparisons will be O(n<sup>2</sup>) . , Space O(n)* 
```
class Solution {
    static void quickSort(int arr[], int low, int high) {
        if(low < high){
            int pi = partition(arr , low , high);
            quickSort(arr , low , pi - 1);
            quickSort(arr , pi + 1 , high);
        }
    }
    static int partition(int arr[], int low, int high) {
        int pivot = arr[high];
        int i = low - 1;
        for(int j = low ; j < high ; j++){
            if(arr[j] < pivot){
                i++;
                swap(arr , i , j);
            }
        }
        swap(arr , i + 1 , high);
        return i + 1;
    }
    static void swap(int arr[] , int i , int j){
        int temp = arr[i];
        arr[i] = arr[j]; 
        arr[j] = temp;
    }
}    
```

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

# Hashing
# Count Distinct Elements from the Array
Time Complexity = O(n)
Sapce Complexity = O(n)
```
    static int countDistinct(int arr[] , int n){
        Set<Integer> hs = new HashSet<Integer>();
        for(int i = 0 ; i < n ; i++){
            hs.add(arr[i]);
        }
        return hs.size();
    }
```

# Count Frequnecy of item in Array
Time Complexity = O(n)
Space Complexity = O(n)
```
static void countfreq(int arr[] , int n){
    Map<Integer , Integer> hmp = new HashMap<Integer,Integer>();
       for(int i = 0 ; i < n ; i++){
           int key = arr[i];
           if(hmp.containsKey(arr[i]) == true){
               hmp.put(arr[i] , hmp.get(arr[i]) + 1);
           }
           else{
               hmp.put(arr[i] , 1);
           }
       }
       for(Map.Entry<Integer , Integer> itr : hmp.entrySet())
           System.out.println(itr.getKey()+" "+itr.getValue());
   }
```

# Common Element from Two Array
Time Complexity = O(m + n)
Sapce Complexity = O(n)
```
public static void intersect(int[] a, int[] b, int m, int n) {
        HashSet<Integer> s = new HashSet<>();
        for (int num : b) {
            s.add(num);
        }
        for (int i = 0; i < m; i++) {
            if (s.contains(a[i])) {
                System.out.print(a[i] + " ");
            }
        }
        System.out.println();
    }

```
# Distinct Elements from Two Array
Time Complexity = O(m + n)
Space Complexity = O(m + n)
```
static int unionSize(int arr1[] , int arr2[] , int m , int n){
        Set<Integer> hs= new HashSet<Integer>();
        for(int i = 0 ; i < m ; i++){
            hs.add(arr1[i]);
        }
        for(int i = 0 ; i < n ; i++){
            hs.add(arr2[i]);
        }
        return hs.size();
    }
```

# Pair with the given Sum
Time-Complexity = O(n)
Space-OCmplexity = O(n)
```
static int pairs(int arr[] , int n , int x){
        HashSet<Integer> us = new HashSet<Integer>();
        for(int i = 0 ; i < n ; i ++){
            if(us.contains(x - arr[i])){
                return 1;
            }
            else{
                us.add(arr[i]);
            }
        }
        return 0;
    }
```

# Sub array with Sum as 0
Time Complexity = O(n) 
Space Complexity = O(n)
```
static int zero(int arr[] , int n){
        HashSet<Integer> us = new HashSet<Integer>();
        int pre = 0;
        us.add(0);
        for(int i = 0 ; i < n ; i++){
            pre += arr[i];
            if(us.contains(pre) == true){
                return 1;
            }
            else{
                us.add(pre);
            }
        }
        return 0;
    }
```
# Dynamic Programming

# LeetCode 70: Climbing Stairs
**Input:** n = 3
**Output:** 3
**Explanation:** There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)

```
class Solution {
    public int climbStairs(int n) {
        if(n <= 1){
            return 1;
        }
        int f = 1;
        int s = 1;
        for(int i = 2 ; i <= n ; i++){
            int ans = f + s;
            f = s;
            s = ans;
        }
        return s;
    }
}
```

# Leetcode 509 Fibonacci Number
**Input:** n = 2
**Output:** 1
**Explanation:** F(2) = F(1) + F(0) = 1 + 0 = 1.
- **Time Complexity:** **O(n)**
- **Space Complexity:** **O(n)**

MEMOISATION(RECURSIVE)
```
class Solution {
    private int[] memo;
    public int fib(int n) {
        memo = new int[n + 1];
        Arrays.fill(memo, -1);
        return fibhelp(n);
    }
    public int fibhelp(int n){
        if(memo[n] != -1){
            return memo[n];
        }
        if(n == 0 || n == 1){
            return n;
        }
        memo[n] = fibhelp(n-1) + fibhelp(n-2);
        return memo[n];
    }
}
```

<u>Tabulation</u>  **Time Complexity: O(n)**  **Space Complexity: O(n)** 
```
class Solution {
    public int fib(int n) {
        if(n == 0){
            return 0;
        }
        if(n == 1){
            return 1;
        }
        int f[]= new int[n+1];
        f[0] = 0;
        f[1] = 1;
        for(int i = 2;  i <= n ; i++){
            f[i] = f[i - 1] + f[i - 2];
        }
        return f[n];
    }
}
```

<u>Optimised Approch</u> **Time Complexity: O(n)**  **Space Complexity: O(1)**
```
class Solution {
    public int fib(int n) {
        if(n == 0){
            return 0;
        }
        if(n == 1){
            return 1;
        }  
        int prev2 = 0;
        int prev1 = 1;
        for(int i = 2 ; i <= n ; i++){
            int curr = prev1 + prev2;
            prev2 = prev1;
            prev1 = curr;
        }
        return prev1;
    }
}
```