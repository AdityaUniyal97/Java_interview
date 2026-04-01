**Problem:**
**Given integer n, repeat:**
**Example:**
**Input: 3**
**Output: 3 10 5 16 8 4 2 1**

```
import java.util.*;
class A{
    public static void main(String args[]){
        Scanner sc = new Scanner(System.in);
        int n =sc.nextInt();
        while(n != 1){
             System.out.print(n+" ");
            if(n % 2 == 0){
                n = n / 2;
            }
            else{
                n = n * 3 + 1;
            }
        }
         System.out.print(1);
    }
}
```

## Missing Number
```
import java.util.*;
class A{
    public static void main(String args[]){
        Scanner sc = new Scanner(System.in);
        int n =  sc.nextInt();
        int arr[] = new int[n];
        for(int i = 0 ; i < n - 1; i++){
            arr[i] = sc.nextInt();
        }
        int sum = 0;
        int total = 0;
        for(int i = 0 ; i < n - 1; i++){
            sum = sum + arr[i];
        }
        
        for(int i = 1 ; i <= n; i++){
            total = total + i;
        }
        
        System.out.println(total - sum);
    }
}
```

## Longest Repeted Characters in a String
Ip = ATTCGGGA
Op= 3
```
import java.util.*;
class A{
    public static void main(String agrs[]){
        Scanner sc = new Scanner(System.in);
        String s = sc.next();
        int count = 1;
        int mc = 0;
        for(int i = 1; i < s.length() ; i++){
            if(s.charAt(i) == s.charAt(i - 1)){
                count++;
            }
            else{
                count = 1;
            }
            if(mc < count){
                mc = count;
            }
        }
        System.out.println(mc);
    }
}
```

## **Problem:**
Given an array, make it non-decreasing (`a[i] ≥ a[i-1]`) by only increasing elements by 1. Find minimum moves.
**Example:**
Input: `5 | 3 2 5 1 7`
Output: `5`
```
import java.util.*;
class A{
    public static void main(String args[]){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for(int i = 0 ; i < n ; i++){
            arr[i] = sc.nextInt();
        }
        int diff = 0;
        for(int i = 1 ; i < n ; i++){
            if(arr[i] < arr[i - 1]){
                diff += arr[i - 1] - arr[i];
                arr[i] = arr[i - 1];
            }
        }
        System.out.println(diff);
    }
}
```

## **Problem:**
Construct a permutation of `1…n` such that no two adjacent elements differ by `1`. If not possible, print `"NO SOLUTION"`.
**Example:**
Input: `5`
Output: `4 2 5 3 1`
Input: `3`
Output: `NO SOLUTION`

```
import java.util.*;
class A{
    public static void main(String agrs[]){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        if(n == 2 || n == 3){
            System.out.println("No SOlution");
            return;
        }
        for(int i = 2 ; i <= n ; i+=2){
            System.out.print(i+" ");
        }
        for(int i = 1 ; i <= n ; i+=2){
            System.out.print(i+" ");
        }
    }
}
```