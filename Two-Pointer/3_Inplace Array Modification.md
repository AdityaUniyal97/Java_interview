-

## Remove Dupplicates from the Array 
```
class Solution {
    public int removeDuplicates(int[] nums) {
        int slow = 1;
        for(int i = 1 ; i < nums.length ; i++){
            if(nums[i] != nums[i - 1]){
                nums[slow] = nums[i];
                slow++;
            }
        }
        return slow;
    }
}
```

## Move zeros at end
```
class Solution {
    public void moveZeroes(int[] nums) {
        int left = 0;
        for(int right = 0 ; right < nums.length ; right++){
            if(nums[right] != 0){
                int temp = nums[right];
                nums[right] = nums[left];
                nums[left] = temp;
                left++;
            }
        }
    }
}
```

## Sort the Colors 
```
class Solution {
    public void sortColors(int[] nums) {
        int i = 0;
        int j = nums.length - 1;
        int k = 0;
        while(k <= j){
            if(nums[k] == 0){
                int temp = nums[i];
                nums[i] = nums[k];
                nums[k] = temp;
                i++;
                k++;
            }
            else if(nums[k] == 1){
                k++;
            }
            else{
                int temp = nums[j];
                nums[j] = nums[k];
                nums[k] = temp;
                j--;
            }
        }
    }
}
```


## LL cycle 

```
public class Solution {
    public boolean hasCycle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
            if(slow == fast){
                return true;
            }
        }
        return false;
    }
}
```


## Find the Dupplicate element 
```
class Solution {
    public int findDuplicate(int[] nums) {
       HashSet<Integer> set = new HashSet<>();
       for(int i = 0 ; i < nums.length ; i++){
        if(set.contains(nums[i])){
            return nums[i];
        }
        else{
            set.add(nums[i]);
        }
       }
       return -1; 
    }
}
```

## Remove the Nth Node from the End of LL 
```
class Solution {
    public ListNode removeNthFromEnd(ListNode head, int n) {
       ListNode dummy = new ListNode(0);
       dummy.next = head;
       ListNode slow = dummy;
       ListNode fast = dummy;
       for(int i = 0 ; i < n ; i++){
        fast = fast.next;
       } 
       while(fast.next != null){
        fast = fast.next;
        slow = slow.next;
       }
       slow.next = slow.next.next;
       return dummy.next;
    }
}
```


## Find the Intersecton between two arrays
```
class Solution {
    public int[] intersection(int[] nums1, int[] nums2) {
        Set<Integer> set = new HashSet<>();
        Set<Integer> res = new HashSet<>();
        for(int n : nums1){
            set.add(n);
        }
        for(int n : nums2){
            if(set.contains(n)){
                res.add(n);
            }
        }
        int ans[] = new int[res.size()];
        int i = 0;
        for(int n : res){
            ans[i] = n;
            i++;
        }
        return ans;
    }
}
```

## Minimum steps to swap black and white ball 
```
class Solution {
    public long minimumSteps(String s) {
        int slow = 0;
        long steps = 0;
        for(int right = 0 ; right < s.length() ;right++){
            if(s.charAt(right) == '0'){
                steps += (right - slow);
                slow++;
            }
        }
        return steps;
    }
}
```

## Remove Dupplicate from sorted Array (only 2 allowed)
```
class Solution {
    public int removeDuplicates(int[] nums) {
        int slow = 0;
        for(int fast = 0 ; fast < nums.length ; fast++){
            if(slow < 2 || nums[fast] != nums[slow - 2]){
                nums[slow] = nums[fast];
                slow++;
            }
        }
        return slow;
    }
}
```

## Sort Colors
```
class Solution {
    public void sortColors(int[] nums) {
        int i = 0;
        int j = nums.length - 1;
        int k = 0;
        while(k <= j){
            if(nums[k] == 0){
                swap(nums,i,k);
                i++;
                k++;
            }
            else if(nums[k] == 1){
                k++;
            }
            else{
                swap(nums,j,k);
                j--;
            }
        }
    }

    private void swap(int nums[] , int a , int b){
        int temp = nums[a]; 
        nums[a] = nums[b];
        nums[b] = temp;
    }
}
```