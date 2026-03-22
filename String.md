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
Reverse the Vowel in the String 

```
class A {

    public static boolean isVowel(char c) {
        c = Character.toLowerCase(c);
        return c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u';
    }

    public static void reverseVowels(char arr[]) {
        int left = 0;
        int right = arr.length - 1;

        while (left < right) {

            // move left until vowel
            while (left < right && !isVowel(arr[left])) {
                left++;
            }

            // move right until vowel
            while (left < right && !isVowel(arr[right])) {
                right--;
            }

            // swap vowels
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

        reverseVowels(arr);

        System.out.println(new String(arr));
    }
}
```