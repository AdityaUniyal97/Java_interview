## Is Happy 
```
class Solution {
    public boolean isHappy(int n) {
        int slow = n;
        int fast = next(n);
        while(fast != 1 && fast != slow){
            slow = next(slow);
            fast = next(next(fast));
        }
        return fast == 1;
    }
    private int next(int a){
        int res = 0;
        while(a != 0){
            int ld = a % 10;
            res += ld * ld;
            a = a / 10;
        }
        return res;
    }
}
```

## LL cycle 
```
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
```

## LL cycle II find the starting point of the circle 
```
public class Solution {
    public ListNode detectCycle(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
            if(slow == fast){
                slow = head;
                while(fast != slow){
                    slow = slow.next;
                    fast = fast.next;
                }
                return slow;
            }
        }
        return null;
    }
}
```

## Issubsiquence 
```
class Solution {
    public boolean isSubsequence(String s, String t) {
        int i = 0;
        int j = 0;
        while(i < s.length() && j < t.length()){
            if(s.charAt(i) == t.charAt(j)){
                i++;
            }
            j++;
        }
        return i == s.length();
    }
}
```

## Middle of the LL
```
class Solution {
    public ListNode middleNode(ListNode head) {
        ListNode slow = head;
        ListNode fast = head;
        while(fast != null && fast.next != null)
        {
            slow = slow.next;
            fast = fast.next.next;
        }
        return slow;
    }
}
```

## Rmeove the Nth node from the End of the LL 
```
 public ListNode removeNthFromEnd(ListNode head, int n) {
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode fast = dummy;
        ListNode slow = dummy;
        for(int i = 0 ; i < n ; i++){
            fast = fast.next;
        }
        while(fast.next != null){
            slow = slow.next;
            fast = fast.next;
        }
        slow.next = slow.next.next;
        return dummy.next;
    }
}
```


## Delete the Middle of the 
```
class Solution {
    public ListNode deleteMiddle(ListNode head) {
        if(head.next == null){
            return null;
        }
        ListNode slow = head;
        ListNode prev = null;
        ListNode fast = head;
        while(fast != null && fast.next != null){
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }
        prev.next = slow.next;
        return head;
    }
}
```


## Sad Number
**// A number is sad if it never reaches 1 (gets stuck in cycle). Return the cycle start number!**
**// Input  = 2
// Output = 4  
// Cycle  = 4 → 16 → 37 → 58 → 89 → 145 → 42 → 20 → 4**
```
class A{
    static class Node{
        Node next;
        int value;
        Node (int value){
            this.next = null;
            this.value = value;
        }
    }
    public static int isSad(int n){
        int slow = n;
        int fast = next(n);
        while(fast != 1 && fast != slow){
            slow = next(slow);
            fast = next(next(fast));
        }
        if(fast == 1) return -1;
        slow = n;
        while(slow != fast){
            slow = next(slow);
            fast = next(fast);
        }
        return slow;
    }
    public static int next(int a){
        int res = 0;
        while(a != 0){
            int ld = a % 10;
            res += ld * ld;
            a = a / 10;
        }
        return res;
    }
    
    public static void main(String args[]){
        int number = 2;
        System.out.println(isSad(number));
    }
}
```


## Palindrome LL
```
 public boolean isPalindrome(ListNode head) {
        if(head == null || head.next == null) return true;
        ListNode slow = head;
        ListNode fast = head;
        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
        }

        ListNode prev = null;
        while(slow != null){
            ListNode next = slow.next;
            slow.next = prev;
            prev = slow;
            slow = next;
        }

        ListNode left = head;
        ListNode right = prev;
        while(right != null){
            if(left.val != right.val){
                return false;
            }
            left = left.next;
            right = right.next;
        }
        return true;
    }
```

## remove the Given Element from the lL
```
public ListNode removeElements(ListNode head, int val) {
        ListNode dummy = new ListNode(0);
        dummy.next = head;
        ListNode curr = dummy;
        while(curr.next != null){
            if(curr.next.val == val){
                curr.next = curr.next.next;
            }
            else{
                curr = curr.next;
            }
        }
        return dummy.next;
    }
```

## Add two Numbers in LL
```
 public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        int carry = 0;
        while(l1 != null || l2 != null || carry != 0){
            int sum = carry;
            if(l1 != null){
                sum += l1.val;
                l1 = l1.next;
            }
            if(l2 != null){
                sum += l2.val;
                l2 = l2.next;
            }
            carry = sum / 10;
            sum = sum % 10;
            curr.next = new ListNode(sum);
            curr = curr.next;
        }
        return dummy.next;
    }
```

## Sort the LL
```
public ListNode sortList(ListNode head) {
        if(head == null || head.next == null) return head;
        ListNode slow = head;
        ListNode fast = head;
        ListNode prev = null;
        while(fast != null && fast.next != null){
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }
        prev.next = null;
        ListNode left = sortList(head);
        ListNode right = sortList(slow);
        return merge(left,right);
    }
    public ListNode merge(ListNode l1 , ListNode l2){
        ListNode dummy = new ListNode(0);
        ListNode curr = dummy;
        while(l1 != null && l2 != null){
            if(l1.val < l2.val){
                curr.next = l1;
                l1 = l1.next;
                curr = curr.next;
            }
            else{
                curr.next = l2;
                l2 = l2.next;
                curr = curr.next;
            }
        }
        if(l1 != null){
            curr.next = l1;
        }
        else{
            curr.next = l2;
        }
        return dummy.next;
    }
```