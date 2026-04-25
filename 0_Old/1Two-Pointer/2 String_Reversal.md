# Reverse the String
```
class A {
    public static void reverse(char arr[]) {
        int left = 0;
        int right = arr.length - 1;

        while (left < right) {
            // swap
            char temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;

            left++;
            right--;
        }
    }

    public static void main(String[] args) {
        String str = "hello";

        char arr[] = str.toCharArray();

        reverse(arr);

        System.out.println(new String(arr));
    }
}
```

## Reverse the Vowel in the String 

```
class Solution {
    public static boolean isVowel(char ch){
        ch = Character.toLowerCase(ch);
        return ch =='a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u';
    }
    public String reverseVowels(String s) {
        char[] ch = s.toCharArray();
        int left = 0;
        int right = ch.length - 1;
        while(left < right){
            while(left < right && !isVowel(ch[left])){
                left++;
            }
            while(left < right && !isVowel(ch[right])){
                right--;
            }
            char temp = ch[left];
            ch[left] = ch[right];
            ch[right] = temp;
            left++;
            right--;
        }
        return new String(ch);
    }
}
```

## Reverse the word
```
class Solution {
    public String reverseWords(String s) {
        String word[] = s.trim().split("\\s+");
        int left = 0;
        int right = word.length - 1;
        while(left < right){
            String temp = word[left];
            word[left] = word[right];
            word[right] = temp;
            left++;
            right--;
        }
        return String.join(" ",word);
    }
}
```

## Reverse the word and character in the word 
```
import java.util.*;
class A{
    public static void main(String agrs[]){
        String s = "hello world";
        System.out.println(solve(s));
    }
    public static String reverse(String s){
        char[] ch = s.toCharArray();
        int low = 0;
        int right = ch.length - 1;
        while(low < right){
            char temp = ch[low];
            ch[low] = ch[right];
            ch[right] = temp;
            low++;
            right--;
        }
        return new String(ch);
    }
    public static String solve(String s){
        String word[] = s.trim().split("\\s+");
        int low = 0;
        int right = word.length - 1;
        while(low < right){
            String temp = word[low];
            word[low] = word[right];
            word[right] = temp;
            low++;
            right--;
        }
        for(int i = 0 ; i < word.length ; i++){
            word[i] = reverse(word[i]);
        }
        return String.join(" ",word);
    }
}
```

## Palindomic substring
****Input:** s = "aaa"
**Output:** 6
**Explanation:** Six palindromic strings: "a", "a", "a", "aa", "aa", "aaa".**
```
class Solution {
    int count = 0;
    public int countSubstrings(String s) {
       for(int i = 0 ; i < s.length(); i++){
            makepal(s,i,i);
            makepal(s,i,i+1);
       }
       return count;
    }

    public void makepal(String s , int l , int r){
        while(l >= 0 && r < s.length() && s.charAt(l) == s.charAt(r)){
            count++;
            l--;
            r++;
        }
    }
}
```


## Longest Plaindrome Substring
```
class Solution {
    String ans = "";
    private void makepal(String s , int l , int r){
        while(l >= 0 && r < s.length() && s.charAt(l) == s.charAt(r)){
            if(r - l + 1 > ans.length()){
                ans = s.substring(l,r+1);
            }
            l--;
            r++;
        }
    }
    public String longestPalindrome(String s) {
        for(int i = 0 ; i < s.length() ; i++){
            makepal(s,i,i);
            makepal(s,i,i+1);
        }
        return ans;
    }
}
```