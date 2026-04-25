## Reverse the String 
```
class Solution {
    public void reverseString(char[] s) {
        int left = 0;
        int right = s.length - 1;
        while(left < right){
            char temp = s[left];
            s[left] = s[right];
            s[right] = temp;
            left++;
            right--;
        }
    }
}
```

## Reverse the Prefix of Word
**Input: word = "abcdefd", ch = "d"
Output: "dcbaefd"**
```
class Solution {
    public String reversePrefix(String word, char ch) {
        int idx = -1;
        for(int i = 0 ; i < word.length() ; i++){
            if(word.charAt(i) == ch){
                idx = i;
                break;
            }
        }
        if(idx == -1) return word;
        char[] arr = word.toCharArray();
        int left = 0;
        int right = idx;
        while(left < right){
            char temp =arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
            left++;
            right--;
        }
        return new String(arr);
    }
}
```

## Revese the Vowel of the String
```
class Solution {
    public boolean isVowel(char c){
        return c=='a'||c=='e'||c=='i'||c=='o'||c=='u'||
        c=='A'||c=='E'||c=='I'||c=='O'||c=='U';
    }
    public String reverseVowels(String s) {
        char[] arr = s.toCharArray();
        int left = 0;
        int right = arr.length - 1;
        while(left < right){
            while(left < right && !isVowel(arr[left])){
                left++;
            }
            while(left < right && !isVowel(arr[right])){
                right--;
            }
            char temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
            left++;
            right--;
        }
        return new String(arr);
    }
}
```

## Reverse The Word in a String
```
class Solution {
    public String reverseWords(String s) {
        String[] words = s.trim().split("\\s+");
        String result = "";
        for(int i = words.length - 1; i >= 0 ; i--){
            result = result + words[i];
            if(i != 0){
                result = result + " ";
            }
        }
        return result;
    }
}
```

## Reverse the Word in String III
**Input: s = "Mr Ding"
Output: "rM gniD"**
```
class Solution {
    public String reverseWords(String s) {
        String words[] = s.split(" ");
        String result = "";
        for(int i = 0 ; i < words.length ; i++){
            String word = words[i];
            String rev = "";
            for(int j = word.length()-1;j>=0;j--){
                rev = rev + word.charAt(j);
            }
            result = result + rev;
            if(i != words.length- 1){
                result = result + " ";
            }
        }
        return result;
    }
}
```

## Valid Palindrome 
**Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.**

```
class Solution {
    public boolean isPalindrome(String s) {
        s = s.toLowerCase().replaceAll("[^a-z0-9]","");
        int left = 0;
        int right = s.length() - 1;
        while(left < right){
            if(s.charAt(left) != s.charAt(right)){
                return false;
            }
            left++;
            right--;
        }
        return true;
    }
}
```

## valid Palindrome II
**Example 1:
Input: s = "aba"
Output: true

**Example 2:
Input: s = "abca"
Output: true
Explanation: You could delete the character 'c'.**
```
class Solution {
    public boolean validPalindrome(String s) {
        int left = 0;
        int right = s.length() - 1;
        while (left < right) {
            //If Not match the move forward
            if (s.charAt(left) != s.charAt(right)) {
                return check(s, left + 1, right) || check(s, left, right - 1);
            }
            left++;
            right--;
        }
        return true;
    }
    private boolean check(String s, int l, int r) {
        while (l < r) {
            if (s.charAt(l) != s.charAt(r)) {
                return false;
            }
            l++;
            r--;
        }
        return true;
    }
}
```

## Lexicographically Smallest Palindrome
**s = "egcfe"
compare:
e vs e → same  
g vs f → take smaller → f  
result = "efcfe"**
### Logic = if left is smaller than right than overide the right with the left character nad in else if both are same than interchange doesnt make any big change , if right is smaller than overide left also handled by else
```
class Solution {
    public String makeSmallestPalindrome(String s) {
        char[] arr = s.toCharArray();
        int left = 0;
        int right = arr.length - 1;
        while(left < right){
            if(arr[left] < arr[right]){
                arr[right] = arr[left];
            }
            else{
                arr[left] = arr[right];
            }
            left++;
            right--;
        }
        return new String(arr);
    }
}
```


## Merge Alternatively
**Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"**
```
class Solution {
    public String mergeAlternately(String word1, String word2) {
        String res = "";
        int i = 0;
        while(i < word1.length() && i < word2.length()){
            res = res + word1.charAt(i);
            res = res + word2.charAt(i);
            i++;
        }
        while(i < word1.length()){
            res = res + word1.charAt(i);
            i++;
        }
        while(i < word2.length()){
            res = res + word2.charAt(i);
            i++;
        }
        return res;
    }
}
```

## Largest Merge of two String(Merge the Largest Character)

**Input: word1 = "cabaa", word2 = "bcaaa"
Output: "cbcabaaaaa"**

```
class Solution {
    public String largestMerge(String word1, String word2) {
        String res = "";
        int i = 0 , j = 0;
        while(i < word1.length() && j < word2.length()){
            if(word1.substring(i).compareTo(word2.substring(j)) > 0){
                res = res + word1.charAt(i);
                i++;
            }
            else{
                res = res + word2.charAt(j);
                j++;
            }
        }
        while(i < word1.length()){
            res += word1.charAt(i++);
        }
        while(j < word2.length()){
            res += word2.charAt(j++);
        }
        return res;
    }
}
```

## Shortest Distance to a Character

**Input: s = "loveleetcode", c = "e"
Output: [3,2,1,0,1,0,0,1,2,2,1,0] Choose the target which is closer**
```
class Solution {
    public int[] shortestToChar(String s, char c) {
        int n = s.length();
        int[] ans = new int[n];
        int prev = -1000;
        //check Left
        for(int i = 0 ; i < n ; i++){
            if(s.charAt(i) == c){
                prev = i;
            }
            ans[i] = i - prev;
        }

        //Check Right
        prev = 1000;
        for(int i =  n ; i >= 0 ; i--){
            if(s.charAt(i) == c){
                prev = i;
            }
            ans[i] = Math.min(ans[i],prev- i);
        }
        return ans;
    }
}
```

## di String Match
**A permutation perm of n + 1 integers of all the integers in the range [0, n] **

**Input: s = "IDID"
Output: [0,4,1,3,2]**
*Because permuatiton says that n + 1size means (0 - 4) *
```
class Solution {
    public int[] diStringMatch(String s) {
        int n = s.length();
        int low = 0;
        int high = n;
        int[] ans = new int[n + 1];
        for(int i = 0 ; i < n ; i++){
            if(s.charAt(i)=='I'){
                ans[i] = low;
                low++;
            }
            else{
                ans[i] = high;
                high--;
            }
        }
        //At last both left and right become same so put any of them
        ans[n] = high;
        return ans;
    }
}
```


## Make string s Subsequence Using Cyclic Increment

**s1 ko change karke s2 banana hai**
**s1 = "abc"
s2 = "ad"
👉 a → a ✅
👉 b → c → d ✅ (2 steps allowed)
👉 possible → true**
```
class Solution {
    public boolean canMakeSubsequence(String s1, String s2) {
        int i = 0 , j = 0;
        while(i < s1.length() && j < s2.length()){
            char c1 = s1.charAt(i);
            char c2 = s2.charAt(j);
            if(c1 == c2){
                i++;
                j++;
            }
            // Next Character ko Nikal rahe ahi or check kar rhe hai
            else if((c1 + 1 - 'a') % 26 + 'a' == c2){
                i++;
                j++;
            }
            else{
                i++;
            }
        }
        return j == s2.length();
    }
}
```

## Minimum Length of String After Deleting Similar Ends

**Agar start aur end same hai, dono side se delete karte jao**
```
Input: s = "cabaabac"
Output: 0
Explanation: An optimal sequence of operations is:
- Take prefix = "c" and suffix = "c" and remove them, s = "abaaba".
- Take prefix = "a" and suffix = "a" and remove them, s = "baab".
- Take prefix = "b" and suffix = "b" and remove them, s = "aa".
- Take prefix = "a" and suffix = "a" and remove them, s = "".
```
Code
```
class Solution {
    public int minimumLength(String s) {
        int left = 0;
        int right = s.length() - 1;
        while(left < right && s.charAt(left) == s.charAt(right)){
            char ch = s.charAt(left);
            while(left <= right && s.charAt(left) == ch){
                left++;
            }
            while(left <= right && s.charAt(right) == ch){
                right--;
            }
        }
        return right - left + 1;
    }
}
```