## Fibonacci 
```
import java.util.*;
class A{
    public static int fib(int dp[] , int n){
        if(n == 0){
            return 0;
        }
        if(n == 1){
            return 1;
        }
        if(dp[n] != -1){
            return dp[n];
        }
        dp[n] = fib(dp,n-1) + fib(dp,n - 2);
        return dp[n];
    }
    
    public static void main(String args[]){
        int n = 4;
        int dp[] = new int[n + 1];
        Arrays.fill(dp,-1);
        System.out.println(fib(dp,n));
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
import java.util.*;
class A{
    public static int reduce(int arr[] , int n , int dp[]){
        if(n <= 1){
            return 0;
        }
        if(dp[n] != -1){
            return dp[n];
        }
        dp[n] = Math.min(
            arr[n-1] + reduce(arr , n - 1, dp), 
            arr[n- 2] + reduce(arr , n - 2, dp)
        );
        return dp[n];
    }
    public static void main(String args[]){
        int arr[] = {10,15,12};
        int n = arr.length;
        int dp[] = new int[n + 1];
        Arrays.fill(dp,-1);
        System.out.println(reduce(arr,n,dp));
    }
}
```

## House Robber (Adacent House Not Allowed)
```
class Solution {
    public int rob(int[] nums) {
        int n = nums.length;
        int dp[] = new int[n + 1];
        Arrays.fill(dp,-1);
        return solve(nums,n,dp);
    }

    public int solve(int[] nums, int n , int[] dp){
        if(n == 0){
            return 0;
        }
        if(n == 1){
            return nums[0];
        }
        if(dp[n] != -1){
            return dp[n];
        }
        dp[n] =  Math.max(nums[n-1]+solve(nums,n-2,dp),
                        solve(nums,n-1,dp)
        );
        return dp[n];
    }
}
```