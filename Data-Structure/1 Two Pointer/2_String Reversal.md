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
#### First repeat the k string and than ignorethan agina do swapping o steps
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