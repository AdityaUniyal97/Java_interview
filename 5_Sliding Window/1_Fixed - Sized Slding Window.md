
## Find the Max Average Sum
```
 public double findMaxAverage(int[] nums, int k) {
        int n = nums.length;
        int sum = 0;
        for(int i = 0 ; i < k ; i++){
            sum += nums[i];
        }
        int maxsum = sum;
        for(int i = k ; i < n ; i++){
            sum += nums[i];
            sum -= nums[i - k];
            maxsum = Math.max(sum , maxsum);
        }
        return (double)maxsum  / k;
    }
```

## Find subarray of size k with MAX SUM
**Input:
arr = [2, 1, 5, 1, 3, 2] , k = 3
 Output:
 [5, 1, 3]
 **
 ```
 class A{
    public static void solve(int arr[] , int k){
        int low = 0;
        int start = 0;
        int ms = 0;
        int sum = 0;
        for(int right = 0 ;right < arr.length ; right++){
            sum = sum + arr[right];
            if(right - low + 1 > k){
                sum -= arr[low];
                low++;
            }
            if(right - low + 1 == k){
                if(sum > ms){
                    ms = sum;
                    start = low;
                }
            }
        }
        for(int i = start ; i < start + k ; i ++){
            System.out.print(arr[i]+" ");
        }
    }
 ```

## Contains Dupplciate II More then the K
**Input:
nums = [1,2,3,1], k = 3
Check:
1 at index 0 and 3 → distance = 3
Since 3 <= k → true
Output:
true**
```
class Solution {
    public boolean containsNearbyDuplicate(int[] nums, int k) {
        HashSet<Integer> set = new HashSet<>();
        for(int i = 0 ; i < nums.length ; i++){
            if(set.contains(nums[i])){
                return true;
            }
            set.add(nums[i]);
            if(set.size() > k){
                set.remove(nums[i - k]);
            }
        }
        return false;
    }
}
```

## Find the MAX Elemement in every Subarray containing dupplicates
```
import java.util.*;
class A{
    public static void solve(int arr[] , int k){
        HashSet<Integer> set = new HashSet<>();
        int low = 0;
        for(int i = 0 ; i < arr.length ; i++){
            set.add(arr[i]);
            if(i - low + 1 > k){
                set.remove(arr[low]);
                low++;
            }
            if(i - low + 1 == k){
                int me = Integer.MIN_VALUE;
                for(int right=low;right<=i;right++){
                    if(arr[right] > me){
                        me = arr[right];
                    }
                }
                System.out.println(me);
            }
        }
    }
    public static void main(String args[]){
        int arr[] = {1,2,1,3,4,2,3};
        int k = 3;
        solve(arr , k);
    }
}
```
## Longest Subbarray Sum == K
```
class A{
    public static int maxSub(int arr[] , int k){
        int sum = 0;
        for(int i = 0 ; i < k ; i++){
            sum += arr[i];
        }
        int ms = sum;
        for(int i = k ; i < arr.length ; i++){
            sum += arr[i];
            sum -= arr[i - k];
            ms = Math.max(ms , sum);
        }
        return ms;
    }
    public static void main(String args[]){
        int arr[] = {2,1,5,1,3,2};
        int k = 3;
        System.out.println(maxSub(arr,k));
    }
}
```

## Max Sum subarray of size K
```
import java.util.*;
class A{
    public static int call(int arr[] , int k){
        int sum = 0;
        int msum = 0;
        for(int i = 0 ; i < k ; i++){
            sum += arr[i];
        }
        msum = sum;
        for(int i = k ; i < arr.length ; i++){
            sum += arr[i];
            sum -= arr[i - k];
            msum = Math.max(msum , sum);
        }
        return msum;
    }
    public static void main(String args[]){
        int arr[] = {2,1,5,1,3,2};
        int k = 3;
        System.out.println(call(arr,k));
    }
}
```


## Substring of Size Three with Distinct Characters
**Input: s = "xyzzaz"
Output: 1
Explanation: There are 4 substrings of size 3: "xyz", "yzz", "zza", and "zaz". 
The only good substring of length 3 is "xyz".**
```
class Solution {
    public int countGoodSubstrings(String s) {
        int count = 0;
        for(int i = 0 ; i <= s.length() - 3 ; i++){
            char a = s.charAt(i);
            char b = s.charAt(i + 1);
            char c = s.charAt(i + 2);
            if(a != b && b != c && a !=c){
                count++;
            }
        }
        return count;
    }
}
```

## Find all the anagrams in a String
**Input: s = "cbaebabacd", p = "abc"
Output: [0,6]
Explanation:
The substring with start index = 0 is "cba", which is an anagram of "abc".
The substring with start index = 6 is "bac", which is an anagram of "abc".**
```
class Solution {
    public List<Integer> findAnagrams(String s, String p) {
        List<Integer> res = new ArrayList<>();
        int[] count = new int[26];
        int[] wcount = new int[26];
        for(char ch : p.toCharArray()){
            count[ch - 'a']++;
        }
        int left = 0;
        for(int right = 0 ; right < s.length() ; right++){
            wcount[s.charAt(right) - 'a']++;
            if(right - left + 1 > p.length()){
                wcount[s.charAt(left) - 'a']--;
                left++;
            }
            if(right - left + 1 == p.length()){
                if(isSame(count,wcount)){
                    res.add(left);
                }
            }
        }
        return res;
    }
    public boolean isSame(int[] a , int [] b){
        for(int i = 0 ; i < 26;  i++){
            if(a[i] != b[i]){
                return false;
            }
        }
        return true;
    }
}
```

## Permuations in a String
**Input: s1 = "ab", s2 = "eidbaooo"
Output: true
Explanation: s2 contains one permutation of s1 ("ba").**
```
class Solution {
    public boolean checkInclusion(String s1, String s2) {
        int[] count = new int[26];
        int[] wcount = new int[26];
        for(char ch : s1.toCharArray()){
            count[ch - 'a']++;
        }
        int left = 0;
        for(int right  = 0 ; right < s2.length() ; right++){
            wcount[s2.charAt(right)-'a']++;
            if(right - left + 1 > s1.length()){
                wcount[s2.charAt(left)-'a']--;
                left++;
            }
            if(right - left + 1 == s1.length()){
                if(isSame(count,wcount)){
                    return true;
                }
            }
        }
        return false;
    }

    public boolean isSame(int[] a , int[] b){
        for(int i = 0 ; i < 26 ; i++){
            if(a[i] != b[i]){
                return false;
            }
        }
        return true;
    }
}
```


## Check If a String Contains All Binary Codes of Size K
**Input: s = "00110110", k = 2
Output: true
Explanation: The binary codes of length 2 are "00", "01", "10" and "11". They can be all found as substrings at indices 0, 1, 3 and 2 respectively.**
```
class Solution {
    public boolean hasAllCodes(String s, int k) {
        HashSet<String> set = new HashSet<>();
        int low = 0;
        for(int right = 0 ; right < s.length() ; right++){
            if(right - low + 1 > k){
                low++;
            }
            if(right - low + 1 == k){
                set.add(s.substring(low,right+1));
            }
        }
        int total = 1;
        for(int i = 0 ; i < k ; i++){
            total = total * 2;
        }
        return set.size() == total;
    }
}
```

## Maximum Number of Vowels in a Substring of Given Length
**Input: s = "abciiidef", k = 3
Output: 3
Explanation: The substring "iii" contains 3 vowel letters.**
```
class Solution {
    public int maxVowels(String s, int k) {
        int left = 0;
        int count = 0;
        int max = 0;
        for(int right = 0 ; right < s.length() ; right++){
            if(isVowel(s.charAt(right))){
                count++;
            }

            if(right - left + 1 > k){
                if(isVowel(s.charAt(left))){
                    count--;
                }
                left++;
            }

            if(right - left + 1 == k){
                max = Math.max(max , count);
            }
        }
        return max;
    }
    public boolean isVowel(char ch){
        return ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u';
    }
}
```

## Maximum Average Sum
**Input: nums = [1,12,-5,-6,50,3], k = 4
Output: 12.75000
Explanation: Maximum average is (12 - 5 - 6 + 50) / 4 = 51 / 4 = 12.75**
```
class Solution {
    public double findMaxAverage(int[] nums, int k) {
        int left = 0;
        int sum = 0;
        int max = Integer.MIN_VALUE;
        for(int right = 0 ; right < nums.length ; right++){
            sum = sum + nums[right];
            if(right - left + 1 > k){
                sum = sum - nums[left];
                left++;
            }
            if(right - left + 1 == k){
                max = Math.max(max , sum);
            }
        }
        return (double)max / k;
    }
}
```


## Number of Sub-arrays of Size K and Average Greater than or Equal to Threshold
**Input: arr = [2,2,2,2,5,5,5,8], k = 3, threshold = 4
Output: 3
Explanation: Sub-arrays [2,5,5],[5,5,5] and [5,5,8] have averages 4, 5 and 6 respectively. All other sub-arrays of size 3 have averages less than 4 (the threshold).**
```
class Solution {
    public int numOfSubarrays(int[] arr, int k, int threshold) {
        int left = 0;
        int sum = 0;
        int count = 0;
        for(int right  = 0 ;right < arr.length ; right++){
            sum = sum + arr[right];
            
            if(right - left + 1 > k){
                sum = sum - arr[left];
                left++;
            }

            if(right - left + 1 == k){
                double avg = (double) sum / k;
                
                if(avg >= threshold){
                    count++;
                }
            }
        }
        return count;
    }
}
```