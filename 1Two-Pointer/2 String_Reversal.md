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