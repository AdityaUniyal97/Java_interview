## // Longest part of the string where you use at most K different Characters 

```
// Longest part of the string where you use at most K different Characters
import java.util.*;
class A{
    public static int solve(String s , int k){
        int left = 0;
        HashMap<Character,Integer> freq = new HashMap<>();
        int res = 0;
        for(int right = 0 ; right < s.length() ; right++){
            char c = s.charAt(right);
            freq.put(c,freq.getOrDefault(c,0) + 1);
            while(freq.size() > k){
                char leftchar = s.charAt(left);
                freq.put(leftchar,freq.get(leftchar) - 1);
                if(freq.get(leftchar) == 0){
                    freq.remove(leftchar);
                }
                left++;
            }
            res = Math.max(res , right - left + 1);
        }
        return res;
    }
    public static void main(String args[]){
        String s = "eceba";
        int k = 2;
        System.out.println(solve(s,k));
    }
}
```


## Numbers 

```
import java.util.*;
class A{
    public static int longest(int arr[] , int k){
        HashMap<Integer,Integer> map = new HashMap<>();
        int left = 0;
        int res = 0;
        for(int right = 0 ; right < arr.length ; right++){
            map.put(arr[right],map.getOrDefault(arr[right],0) + 1);
            while(map.size() > k){
                map.put(arr[left],map.get(arr[left]) - 1);
                if(map.get(arr[left]) == 0){
                    map.remove(arr[left]);
                }
                left++;
            }
            res = Math.max(res , right - left + 1);
        }
        return res;
    }
    
    public static void main(String args[]){
        int arr[] = {1,2,1,3,2};
        int k = 2;
        System.out.println(longest(arr , k));
    }
} talk like hardest man on the erath train me
```


## Maximum Sum 
```
import java.util.*;
class A{
    public static int mss(int arr[] , int k){
        HashMap<Integer,Integer> map = new HashMap<>();
        int sum = 0;
        int ms = 0;
        int left = 0;
        for(int right = 0 ; right < arr.length ; right++){
            sum += arr[right];
            map.put(arr[right],map.getOrDefault(arr[right],0) + 1);
            while(map.size() > k){
                sum -= arr[left];
                map.put(arr[left],map.get(arr[left]) - 1);
                if(map.get(arr[left]) == 0){
                    map.remove(arr[left]);
                }
                left++;
            }
            ms = Math.max(ms , sum);
        }
        return ms;
    }
    public static void main(String args[]){
        int arr[] = {1,2,1,3,2};
        int k = 2;
        System.out.println(mss(arr , k));
    }
}
```

## Fruits into the Basket 
```
import java.util.*;
class A{
    public static int fruits(int arr[]){
        int left = 0;
        int ms = 0;
        Map<Integer,Integer> map = new HashMap<>();
        for(int right = 0 ; right < arr.length ; right++){
            map.put(arr[right],map.getOrDefault(arr[right],0) + 1);
            while(map.size() > 2){
                map.put(arr[left],map.get(arr[left]) - 1);
                if(map.get(arr[left]) == 0){
                    map.remove(arr[left]);
                }
                left++;
            }
            ms = Math.max(ms , right - left + 1);
        }
        return ms;
    }
    public static void main(String args[]){
        int arr[] = {1,0,1,4,1,4,1,2,3};
        System.out.println(fruits(arr));
    }
}
```


## Longest Substring with At Most 2 Distinct Characters

```
import java.util.*;
class A{
    public static int lss(String s){
        HashMap<Character,Integer> map = new HashMap<>();
        int ms = 0;
        int left = 0;
        for(int right = 0 ; right < s.length() ; right++){
            char rs = s.charAt(right);
            map.put(rs,map.getOrDefault(rs,0) + 1);
            while(map.size() > 2){
                char ls = s.charAt(left);
                map.put(ls,map.get(ls) - 1);
                if(map.get(ls) == 0){
                    map.remove(ls);
                }
                left++;
            }
            ms = Math.max(ms , right - left + 1);
        }
        return ms;
    }
    public static void main(String args[]){
        String s = "ccaabbb";
        System.out.println(lss(s));
    }
}
```


## Integer array. At most K distinct. Longest subarray. 
```
import java.util.*;
class A{
    public static int lss(int arr[] , int k){
        HashMap<Integer,Integer> map = new HashMap<>();
        int left = 0;
        int res = 0;
        for(int right = 0 ; right < arr.length ; right++){
            map.put(arr[right],map.getOrDefault(arr[right],0) + 1);
            while(map.size() > k){
                map.put(arr[left],map.get(arr[left]) - 1);
                if(map.get(arr[left]) == 0){
                    map.remove(arr[left]);
                }
                left++;
            }
            res = Math.max(res , right - left + 1);
        }
        return res;
    }
    public static void main(String args[]){
        int arr[] = {1,2,1,2,3};
        int k = 2;
        System.out.println(lss(arr,k));
    }
}
```


## Longest Substring without repeating charccters
```
class Solution {
    public int lengthOfLongestSubstring(String s) {
        HashSet<Character> set = new HashSet<>();
        int left = 0;
        int res = 0;
        for(int right = 0 ; right < s.length() ; right++){
            while(set.contains(s.charAt(right))){
                set.remove(s.charAt(left));
                left++;
            }
            set.add(s.charAt(right));
            res = Math.max(res, set.size());
        }
        return res;
    }
}
```

## Given a string, find the longest substring where no character repeats MORE THAN 2 times. Input: s = "aaabcde" Output: 6 ("aabcde") - wait 'a' appears twice, valid

```
import java.util.*;
class A{
    public static int lss(String s){
        HashMap<Character,Integer> map = new HashMap<>();
        int left = 0;
        int res = 0;
        for(int right = 0 ; right < s.length() ; right++){
            char rs = s.charAt(right);
            map.put(rs,map.getOrDefault(rs,0) + 1);
            while(map.get(rs) > 2){
                char ls = s.charAt(left);
                map.put(ls,map.get(ls) - 1);
                if(map.get(ls) == 0){
                    map.remove(ls);
                }
                left++;
            }
            res = Math.max(res , right - left + 1);
        }
        return res;
    }
    public static void main(String args[]){
        String s = "aaabcde";
        System.out.println(lss(s));
    }
}
```


## 1004 MAX consecutive Ones III after fliping 
```
class Solution {
    public int longestOnes(int[] nums, int k) {
        int left = 0;
        int zero = 0;
        int res = 0;
        for(int i = 0 ; i < nums.length ;i ++){
            if(nums[i] == 0){
                zero++;
            }
            while(zero > k){
                if(nums[left] == 0){
                    zero--;
                }
                left++;
            }
            res = Math.max(res , i - left + 1);
        }
        return res;
    }
}
```