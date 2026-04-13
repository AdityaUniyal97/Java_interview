## Number Frequency 
```
import java.util.*;
class A{
    public static void main(String args[]){
        int arr[] = {1,2,2,3,1,2};
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int num : arr){
            map.put(num,map.getOrDefault(num,0) + 1);
        }
        for(Map.Entry<Integer,Integer> entry : map.entrySet()){
            System.out.println(entry.getKey()+" -> "+entry.getValue());
        }
    }
}
```

## character freq
```
import java.util.*;
class A{
    public static void main(String agrs[]){
        String s = "aaaabbbcccccdde";
        char[] ch = s.toCharArray();
        HashMap<Character,Integer> map = new HashMap<>();
        for(char c : ch){
            map.put(c,map.getOrDefault(c,0)+1);
        }
        
        for(Map.Entry<Character,Integer>entry : map.entrySet()){
            System.out.println(entry.getKey()+" "+entry.getValue());
        }
    }
}
```

## first Non repeating character
```
import java.util.*;
class A{
    public static void main(String agrs[]){
        String s = "aaaabbbcccccdde";
        char[] ch = s.toCharArray();
        HashMap<Character,Integer> map = new HashMap<>();
        for(char c : ch){
            map.put(c,map.getOrDefault(c,0)+1);
        }
        
        for(char c : ch){
            if(map.get(c) == 1){
                System.out.println(c);
                break;
            }
        }
    }
}
```

## Count of Unique Element in an Array
```
import java.util.*;
class A{
    public static void main(String args[]){
        int arr[] = {1,2,2,3,1,4};
        HashSet<Integer> set = new HashSet<>();
        for(int num : arr){
            set.add(num);
        }
        
        System.out.println(set.size());
    }
}
```

HashMap
```
class A{
    public static void main(String args[]){
        int arr[] = {1,2,2,3,1,4};
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int num : arr){
            map.put(num,map.getOrDefault(num,0) + 1);
        }
        System.out.println(map.size());
    }
}
```
## Longest Consecutive Sequence in an Array
Input: nums = [100, 4, 200, 1, 3, 2]
Output: 4
Explanation:
The longest sequence of consecutive elements in the array is [1, 2, 3, 4], which has a length of 4. This sequence can be formed regardless of the initial order of the elements in the array.
```
class Solution {
    public int longestConsecutive(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        for(int num : nums){
            set.add(num);
        }
        int maxlength = 0;
        for(int num : set){
            if(!set.contains(num - 1)){
                int curr = num;
                int count = 1;
                while(set.contains(curr + 1)){
                    curr = curr + 1;
                    count++;
                }
                maxlength = Math.max(maxlength , count);
            }
        }
        return maxlength;
    }
}
```

## Two Sum
```
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map = new HashMap<>();
        for(int i = 0 ; i < nums.length() ; i++){
            int sum = target - nums[i];
            if(map.containsKey(sum)){
                return new int[]{map.get(sum),i};
            }
            map.put(nums[i],i);
        }
        return new int[]{-1,-1};
    }
}
```

## Missing Number in an array
```
class Solution {
    public int missingNumber(int[] nums) {
        int n = nums.length;
        int sum = 0;
        for(int num : nums){
            sum += num;
        }
        int total = 0;
        for(int i = 0 ; i <= n ; i++){
            total += i;
        }
        return total - sum;
    }
}
```

## Find all the Dupplicates numbers form the Array
**Input: nums = [4,3,2,7,8,2,3,1]
Output: [2,3]**
```
class Solution {
    public List<Integer> findDuplicates(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        ArrayList<Integer> list = new ArrayList<>();
        for(int num : nums){
            if(set.contains(num)){
                list.add(num);
            }
            else{
                set.add(num);
            }
        }
        return list;
    }
}
```
## Find all the Disappeared Numbers from the Array
```
class Solution {
    public List<Integer> findDisappearedNumbers(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        ArrayList<Integer> list = new ArrayList<>();
        for(int num : nums){
            set.add(num);
        }
        for(int i = 1 ; i <= nums.length ; i++){
            if(!set.contains(i)){
                list.add(i);
            }
        }
        return list;
    }
}
```

## first Positive Missing Number
**Input: nums = [1,2,0]
Output: 3
Explanation: The numbers in the range [1,2] are all in the array.**
```
class Solution {
    public int firstMissingPositive(int[] nums) {
        HashSet<Integer> set = new HashSet<>();
        for(int num : nums){
            set.add(num);
        }
        int i = 1;
        while(true){
            if(!set.contains(i)){
                return i;
            }
            i++;
        }
    }
}
```