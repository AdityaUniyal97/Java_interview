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
Time = O(n) , Space = O(1)

## String Reverse II
Reverse String II  
s = "abcdefg", k = 2  
Rule: First k reverse → ab → ba Next k skip → cd Next k reverse → ef → fe Remaining → g  
Final: bacdfeg

**Pattern**  
Jump = 2k Reverse = k Skip = k

**Time Complexity**  
O(n)

**Space Complexity**  
O(n)

**Memory Line**  
2k jump, k reverse, k skip
```
class Solution {
    public String reverseStr(String s, int k) {
        char arr[] = s.toCharArray();
        for(int i = 0 ; i < arr.length ; i = i + 2*k){
            int left = i;
            int right = i + k - 1;
            if(right >= arr.length){
                right = arr.length - 1;
            }
            while(left < right){
                char temp = arr[left];
                arr[left] = arr[right];
                arr[right] = temp
                left++;
                right--;
            }
        }
        return new String(arr);
    }
}
```

---

## Reverse Vowels of a String

s = "hello"
Rule: Move left → find vowel Move right → find vowel Swap them Continue until pointers meet
Example: e ↔ o → holle
Final: holle

**Pattern**
Two pointer Left finds vowel Right finds vowel Swap

**Time Complexity**
O(n)

**Space Complexity**
O(n)

**Memory Line**
Find vowel left, find vowel right, swap

```java
class Solution {
    public String reverseVowels(String s) {
        char[] arr = s.toCharArray();

        int left = 0;
        int right = arr.length - 1;

        while(left < right){

            if(!isVowel(arr[left])){
                left++;
                continue;
            }

            if(!isVowel(arr[right])){
                right--;
                continue;
            }

            char temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;

            left++;
            right--;
        }

        return new String(arr);
    }

    public boolean isVowel(char c){
        return "aeiouAEIOU".indexOf(c) != -1;
    }
}
```


---

## Reverse Words in a String

s = "the sky is blue"  
Rule: Remove extra spaces Split words Reverse order Join with single space  
Example: ["the","sky","is","blue"] → ["blue","is","sky","the"]  
Final: blue is sky the

**Pattern**  
Trim Split Reverse Join

**Time Complexity**  
O(n)

**Space Complexity**  
O(n)

**Memory Line**  
Trim, split, reverse, join

```java
class Solution {
    public String reverseWords(String s) {
        String[] words = s.trim().split("\\s+");

        String result = "";

        for(int i = words.length - 1; i >= 0; i--){
            result += words[i];

            if(i != 0){
                result += " ";
            }
        }

        return result;
    }
}
```

---

## Reverse Words in a String III

s = "Let's take LeetCode contest"
Rule: Each word reverse Words order same
Example: "Let's" → "s'teL" "take" → "ekat"
Final: s'teL ekat edoCteeL tsetnoc

**Pattern**
Split Reverse each word Join

**Time Complexity**
O(n)

**Space Complexity**
O(n)

**Memory Line**
Word same, inside reverse

```java
class Solution {
    public String reverseWords(String s) {
        String[] words = s.split(" ");

        for(int i = 0; i < words.length; i++){
            words[i] = reverse(words[i]);
        }

        String result = "";

        for(int i = 0; i < words.length; i++){
            result += words[i];

            if(i != words.length - 1){
                result += " ";
            }
        }

        return result;
    }

    public String reverse(String str){
        char[] arr = str.toCharArray();

        int left = 0;
        int right = arr.length - 1;

        while(left < right){
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

---

## Reverse Only Letters

s = "a-bC-dEf-ghIj"  
Rule: Only letters reverse Non-letters stay same position  
Example: letters → abC dEf ghIj → reverse → jIh gfE dCba  
Final: j-Ih-gfE-dCba

**Pattern**  
Two pointer Skip non-letters Swap letters

**Time Complexity**  
O(n)

**Space Complexity**  
O(n)

**Memory Line**  
Skip non-letter, swap letter

```java
class Solution {
    public String reverseOnlyLetters(String s) {
        char[] arr = s.toCharArray();

        int left = 0;
        int right = arr.length - 1;

        while(left < right){

            if(!Character.isLetter(arr[left])){
                left++;
                continue;
            }

            if(!Character.isLetter(arr[right])){
                right--;
                continue;
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

---

## Valid Palindrome

s = "A man, a plan, a canal: Panama"  
Rule: Ignore non-letters Ignore case Check same from both sides  
Example: amanaplanacanalpanama → palindrome  
Final: true

**Pattern**  
Two pointer Skip non-letter Compare lower case

**Time Complexity**  
O(n)

**Space Complexity**  
O(n)

**Memory Line**  
Skip, lower, compare

```java
class Solution {
    public boolean isPalindrome(String s) {
        char[] arr = s.toCharArray();

        int left = 0;
        int right = arr.length - 1;

        while(left < right){

            if(!Character.isLetterOrDigit(arr[left])){
                left++;
                continue;
            }

            if(!Character.isLetterOrDigit(arr[right])){
                right--;
                continue;
            }

            if(Character.toLowerCase(arr[left]) != Character.toLowerCase(arr[right])){
                return false;
            }

            left++;
            right--;
        }

        return true;
    }
}
```

---

## Valid Palindrome II

s = "abca"  
Rule: One mismatch allowed Remove either left or right and check palindrome  
Example: remove 'c' → aba → palindrome  
Final: true

**Pattern**  
Two pointer Compare On mismatch try skip left or skip right

**Time Complexity**  
O(n)

**Space Complexity**  
O(n)

**Memory Line**  
One delete allowed

```java
class Solution {
    public boolean validPalindrome(String s) {
        int left = 0;
        int right = s.length() - 1;

        while(left < right){
            if(s.charAt(left) != s.charAt(right)){
                return check(s, left+1, right) || check(s, left, right-1);
            }
            left++;
            right--;
        }
        return true;
    }

    public boolean check(String s, int left, int right){
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