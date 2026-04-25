**Kadane’s Algorithm** is used to:
👉 Find the **maximum sum subarray** (contiguous)  
👉 Works when **subarray size is NOT fixed** 

**MAX SUM SUBARRAY**

```
class A{
    public static void main(String args[]){
        int arr[] = {-2, 1, -3, 4, -1, 2, 1, -5, 4};
        System.out.println(solve(arr));
    }
    
    public static int solve(int arr[]){
        int sum = arr[0];
        int maxsum = arr[0];
        for(int i = 0 ; i < arr.length ; i++){
            if(sum < 0){
                sum = arr[i];
            }
            else{
                sum += arr[i];
            }
            maxsum = Math.max(maxsum , sum);
        }
        return maxsum;
    }
}
```

**MAX Product in a Sub array**
Normal day, positive numbers:
maxP = 3, minP = 1, next number = 2
3 × 2 = 6 → still max ✅
1 × 2 = 2 → still min ✅
Makes sense right?
Now next number is -2:
3 × -2 = -6 → now it's the MIN
1 × -2 = -2 → now it's the MAX
Max became min. Min became max.
So before multiplying, just swap them!
```
class A{
    public static int solve(int arr[]){
        int maxP = arr[0];
        int minP = arr[0];
        int res = arr[0];
        for(int i = 1; i < arr.length ; i++){
            if(arr[i] < 0){
                int temp = maxP;
                maxP = minP;
                minP = temp;
            }
            maxP = Math.max(arr[i],maxP * arr[i]);
            minP = Math.min(arr[i],minP * arr[i]);
            res = Math.max(res,maxP);
        }
        return res;
    }
    public static void main(String args[]){
        int arr[] = {2,3,-2,4};
        System.out.println(solve(arr));
    }
}
```

## Maximum Circular Sub Array
```
class A{
    public static int solve(int arr[]){
        int total = 0;
        int curMax = arr[0] , maxSum = arr[0];
        int curMin = arr[0] , minSum = arr[0];
        for(int i = 0 ; i < arr.length ; i++){
            total = total + arr[i];
            
            //Case1: Normal Kdanes
            if(curMax < 0){
                curMax = arr[i];
            }
            else{
                curMax += arr[i];
            }
            maxSum = Math.max(maxSum , curMax);
            
            //Case2: Kdane for min
            if(curMin > 0){
                curMin = arr[i];
            }
            else{
                curMin += arr[i];
            }
            minSum = Math.min(minSum , curMin);
        }
        if(maxSum < 0){
            return maxSum;
        }
        return Math.max(maxSum , total - minSum);
    }
    public static void main(String args[]){
        int arr[] = {5,-3,5};
        System.out.println(solve(arr));
    }
}
```

## Maximum Absolute Sum of Any Subarray
Input: nums = [1,-3,2,3,-4]
Output: 5
Explanation: The subarray [2,3] has absolute sum = abs(2+3) = abs(5) = 5.

```
class A{
    public static int solve(int arr[]){
        int currMax = arr[0] , maxSum = arr[0];
        int currMin = arr[0] , minSum = arr[0];
        for(int i = 1; i < arr.length ; i++){
            if(currMax < 0){
                currMax = arr[i];
            }
            else{
                currMax += arr[i];
            }
            maxSum = Math.max(maxSum , currMax);
            
            if(currMin > 0){
                currMin = arr[i];
            }
            else{
                currMin += arr[i];
            }
            minSum = Math.min(minSum , currMin);
        }
        return Math.max(Math.abs(maxSum),Math.abs(minSum));
    }
    public static void main(String args[]){
        int arr[] = {1,-3,2,3,-4};
        System.out.println(solve(arr));
    }
}
```