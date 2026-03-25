```
import java.util.*;

public class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        long MOD = 1000000007;
        
        int n = sc.nextInt();
        long[] A = new long[n];
        for(int i = 0; i < n; i++) {
            A[i] = sc.nextLong();
        }
        
        int q = sc.nextInt();
        long total = 0;
        
        while(q-- > 0) {
            int type = sc.nextInt();
            int l = sc.nextInt();
            int r = sc.nextInt();
            
            if(type == 1) {
                long base = A[l];
                for(int i = l; i <= r; i++) {
                    A[i] = ((i - l + 1) * base) % MOD;
                }
            } else {
                for(int i = l; i <= r; i++) {
                    total = (total + A[i]) % MOD;
                }
            }
        }
        
        System.out.println(total);
    }
}
```


```
import java.util.*;
class A {
    public static void main(String args[]) {
        Scanner sc = new Scanner(System.in);
        
        int n = sc.nextInt();
        int k = sc.nextInt();
        int[] A = new int[n];
        for(int i = 0; i < n; i++) {
            A[i] = sc.nextInt();
        }
        
        Map<Integer, Integer> map = new HashMap<>();
        long maxSum = 0; // empty subarray = 0
        long sum = 0;
        int left = 0;
        
        for(int right = 0; right < n; right++) {
            // right element window mein daalo
            map.put(A[right], map.getOrDefault(A[right], 0) + 1);
            sum += A[right];
            
            // distinct > k ho gaya → left badhao
            while(map.size() > k) {
                map.put(A[left], map.get(A[left]) - 1);
                if(map.get(A[left]) == 0) map.remove(A[left]); // freq 0 → remove
                sum -= A[left];
                left++;
            }
            
            // valid window hai → max check karo
            maxSum = Math.max(maxSum, sum);
        }
        
        System.out.println(maxSum);
    }
}
```


```
import java.util.*;
class A{
    public static void main(String args[]){
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int c = sc.nextInt();
        int[] arr = new int[n];
        for(int i = 0 ; i < n ; i++){
            arr[i] = sc.nextInt();
        }
        int x = 0;
        int tank = 0;
        for(int i = 0 ; i < n ; i++){
            if(arr[i] == -1){
                if(tank == 0){
                    x++;
                }
                else{
                    tank--;
                }
            }
            else{
                if(tank < c){
                    tank++;
                }
            }
        }
        System.out.println(Math.min(x , c));
    }
}
```


