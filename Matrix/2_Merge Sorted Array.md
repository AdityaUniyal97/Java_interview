## Merge Sorted Array 
Input: nums = [-4,-1,0,3,10]
Output: [0,1,9,16,100]
```
class Solution {
    public int[] sortedSquares(int[] nums) {
        int n = nums.length;
        int[] res = new int[n];
        int left = 0;
        int right = n - 1;
        int i = n - 1;
        while(left <= right){
            int lm = nums[left] * nums[left];
            int rm = nums[right] * nums[right];
            if(lm > rm){
                res[i] = lm;
                left++;
                i--;
            }
            else{
               res[i] = rm;
                right--;
                i--;
            }
        }
        return res;
    }
}
```

## Merge Two SOrted Arrays
```
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {
        int i = m - 1;
        int j = n - 1;
        int k = m + n - 1;
        while(i >= 0 && j >= 0){
            if(nums1[i] > nums2[j]){
                nums1[k] = nums1[i];
                i--;
                k--;
            }
            else{
                nums1[k] = nums2[j];
                j--;
                k--;
            }
        }
        while(j >= 0){
            nums1[k] = nums2[j];
            j--;
            k--;
        }
    }
}
```

## Merge two LL
```
public ListNode mergeTwoLists(ListNode list1, ListNode list2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        while(list1 != null && list2 != null){
            if(list1.val <= list2.val){
                curr.next = list1;
                list1 = list1.next;
                curr = curr.next;
            }
            else{
                curr.next = list2;
                list2 = list2.next;
                curr = curr.next;
            }
        }

        while(list1 != null){
            curr.next = list1;
            list1 = list1.next;
            curr = curr.next;
        }

         while(list2 != null){
            curr.next = list2;
            list2 = list2.next;
            curr = curr.next;
        }
        return dummy.next;
    }
```