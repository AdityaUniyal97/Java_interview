## Fibonacci 
```
class A{
    public static int fib(int n){
        if(n == 1){
            return 1;
        }
        if(n == 2){
            return 2;
        }
        int prev2 = 2;
        int prev1 = 1;
        for(int i = 3 ; i <= n ; i++){
            int curr = prev2 + prev1;
            prev2 = prev1;
            prev1 = curr;
        }
        return prev1;
    }
    public static void main(String agrs[]){
        int n = 3;
        System.out.println(fib(n));
    }
}
```

## Total step to reach the N
```
import java.util.*;
class A{
    public static int path(int n , int[] dp){
        if(n <= 1){
            return 1;
        }
        if(dp[n] != -1){
            return dp[n];
        }
        dp[n] = path(n-1,dp) + path(n-2,dp);
        return dp[n];
    }
    public static void main(String args[]){
        int n = 3;
        int[] dp = new int[n  +1];
        Arrays.fill(dp,-1);
        System.out.println(path(n,dp));
    }
}
```

## Minimum Cost Climbing Stair

cost = [10, 15, 20]
Answer = 15
```
class A{
    public static void main(String agrs[]){
        int cost[] = {10,30,20};
        System.out.println(minCost(cost));
    }
    
    public static int minCost(int cost[]){
        int n = cost.length;
        if(n == 1){
            return cost[0];
        }
        int prev2 = cost[0];
        int prev1 = cost[1];
        for(int i = 3 ; i < n ; i++){
            int curr = cost[i] + Math.min(prev2 , prev1);
            prev2 = prev1;
            prev1 = curr;
        }
        return Math.min(prev2 , prev1);
    }
}
```

## House Robber (Adacent House Not Allowed)
```
class A{
    public static int fib(int arr[]){
        int n = arr.length;
        if(n == 1){
            return arr[0];
        }
        int prev2 = arr[0];
        int prev1 = Math.max(arr[0],arr[1]);
        for(int i = 2 ; i < n ; i++){
            int curr = Math.max(arr[i]+prev2,prev1);
            prev2 = prev1;
            prev1 = curr;
        }
        return prev1;
    }
    public static void main(String agrs[]){
        int[] arr = {2,7,9,3,1};
        System.out.println(fib(arr));
    }
}
```

## Pascal traingle
```
class Solution {
    public List<List<Integer>> generate(int numRows) {
        List<List<Integer>> result = new ArrayList<>();
        for(int i = 0 ; i < numRows; i++){
            List<Integer> row = new ArrayList<>();
            for(int j = 0 ; j <= i ; j++){
                if(j == 0 || j == i){
                    row.add(1);
                }
                else{
                    row.add(result.get(i-1).get(j-1) + result.get(i - 1).get(j));
                }
            }
            result.add(row); 
        }
        return result;
    }
}
```