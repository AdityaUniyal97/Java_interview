# LeetCode 70: Climbing Stairs
**Input:** n = 3
**Output:** 3
**Explanation:** There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

- **Time Complexity:** O(n)
- **Space Complexity:** O(1)

```
class Solution {
    public int climbStairs(int n) {
        if(n <= 1){
            return 1;
        }
        int f = 1;
        int s = 1;
        for(int i = 2 ; i <= n ; i++){
            int ans = f + s;
            f = s;
            s = ans;
        }
        return s;
    }
}
```

# Leetcode 509 Fibonacci Number
**Input:** n = 2
**Output:** 1
**Explanation:** F(2) = F(1) + F(0) = 1 + 0 = 1.
- **Time Complexity:** **O(n)**
- **Space Complexity:** **O(n)**

MEMOISATION(RECURSIVE)
```
class Solution {
    private int[] memo;
    public int fib(int n) {
        memo = new int[n + 1];
        Arrays.fill(memo, -1);
        return fibhelp(n);
    }
    public int fibhelp(int n){
        if(memo[n] != -1){
            return memo[n];
        }
        if(n == 0 || n == 1){
            return n;
        }
        memo[n] = fibhelp(n-1) + fibhelp(n-2);
        return memo[n];
    }
}
```

<u>Tabulation</u>  **Time Complexity: O(n)**  **Space Complexity: O(n)** 
```
class Solution {
    public int fib(int n) {
        if(n == 0){
            return 0;
        }
        if(n == 1){
            return 1;
        }
        int f[]= new int[n+1];
        f[0] = 0;
        f[1] = 1;
        for(int i = 2;  i <= n ; i++){
            f[i] = f[i - 1] + f[i - 2];
        }
        return f[n];
    }
}
```

<u>Optimised Approch</u> **Time Complexity: O(n)**  **Space Complexity: O(1)**
```
class Solution {
    public int fib(int n) {
        if(n == 0){
            return 0;
        }
        if(n == 1){
            return 1;
        }  
        int prev2 = 0;
        int prev1 = 1;
        for(int i = 2 ; i <= n ; i++){
            int curr = prev1 + prev2;
            prev2 = prev1;
            prev1 = curr;
        }
        return prev1;
    }
}
```

# Longest Susequence
Tabulation:
- **Time Complexity:** O(n * m)
- **Space Complexity:** O(n * m)
```
static int memo[][];
    static int lcs(String s1, String s2 , int n,  int m){
        if(memo[n][m] != -1){
            return memo[n][m];
        }
        if(n == 0 || m == 0){
            memo[n][m] = 0;
        }
        else{
            if(s1.charAt(n-1) == s2.charAt(m - 1)){
                memo[n][m] = 1 + lcs(s1 , s2 , n - 1 , m - 1);
            }
            else{
                memo[n][m] = Math.max(lcs(s1 , s2 , n - 1 , m), 
                                      lcs(s1 , s2 , n , m -1));
            }
        }
        return memo[n][m];
    }
```
Memoization:
Time Complexity = O(m* n)
Space Complexity = O(m * n)
```
static int lcs(String s1 , String s2){
        int m = s1.length() , n = s2.length();
        int dp[][] = new int[m + 1][n + 1];
        for(int i = 1; i <= m ; i++){
            for(int j = 1; j <= n ; j++){
                if(s1.charAt(i-1) == s2.charAt(j - 1)){
                    dp[i][j] = 1 + dp[i - 1][j - 1];
                }
                else{
                    dp[i][j] = Math.max(dp[i - 1][j],
                                        dp[i][j - 1]);
                }
            }
        }
        return dp[m][n];
    }
```

# Coin Change Problem
Recursive:
```
static int count(int coins[] , int n , int sum){
        if(sum == 0){
            return 1;
        }
        if(sum < 0){
            return 0;
        }
        if(n <= 0){
            return 0;
        }
        return count(coins , n - 1 , sum) +
               count(coins , n , sum - coins[n - 1]);
    }
```