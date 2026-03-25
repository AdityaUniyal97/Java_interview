**Kadane’s Algorithm** is used to:

👉 Find the **maximum sum subarray** (contiguous)  
👉 Works when **subarray size is NOT fixed** 

## Maximum SUbarray sum
```
 class A{
    public static int ms(int arr[]){
        int ms = arr[0];
        int sum = arr[0];
        for(int i = 1 ; i < arr.length ; i++){
            sum = Math.max(sum , arr[i] + sum);
            ms = Math.max(sum , ms);
        }
        return ms;
    }
    public static void main(String args[]){
        int arr[] = {-1, -2, -3, -4};
    System.out.println(ms(arr));
    }
}

```


## Maximum Circular Sub array
```
class A{
    public static int ms(int arr[]){
        int sum = arr[0];
        int ms = arr[0];
        for(int i = 1; i < arr.length ; i++){
            sum = Math.max(sum , arr[i] + sum);
            ms = Math.max(sum , ms);
        }
        return ms;
    }
    public static int mins(int arr[]){
        int diff = arr[0];
        int ms = arr[0];
        for(int i =  1 ; i < arr.length ; i++){
            diff = Math.min(diff , diff + arr[i]);
            ms = Math.min(ms , diff);
        }
        return ms;
    }
    public static int mc(int arr[]){
        int total = 0;
        for(int x : arr){
            total += x;
        }
        int maxs = ms(arr);
        int mins = mins(arr);
        if(total == mins){
            return maxs;
        }
        return Math.max(maxs , total - mins);
    }
    public static void main(String args[]){
        int arr[] = {5,-3,5};
        System.out.println(mc(arr));
    }
}
```

# Maximum subarray 
```
class A{
    public static int ms(int arr[]){
        int sum = arr[0];
        int ms = arr[0];
        for(int i = 0 ; i < arr.length ; i++){
            sum = Math.max(sum , arr[i] + sum);
            ms = Math.max(ms , sum);
        }
        return ms;
    }
    public static void main(String args[]){
        int arr[] = {-2,1,-3,4,-1,2,1,-5,4};
        System.out.println(ms(arr));
    }
}
```
