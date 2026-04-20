## Reverse printing 
```
class A{
    public static void reversePrint(int[] arr){
        for(int i = arr.length - 1 ; i >= 0 ; i--){
            System.out.println(arr[i]+" ");
        }
    }
    public static void main(String args[]){
        int[] arr = {1,2,3,4,5};
        reversePrint(arr);
    }
}
```

## Array Reverse
```
class A{
    public static void reversePrint(int[] arr){
        int left = 0;
        int right = arr.length - 1;
        while(left< right){
            int temp = arr[left];
            arr[left] = arr[right];
            arr[right] = temp;
            left++;
            right--;
        }
    }
    public static void main(String args[]){
        int[] arr = {1,2,3,4,5};
        reversePrint(arr);
        for(int i = 0 ; i < arr.length ; i++){
            System.out.println(arr[i]+" ");
        }
    }
}
```

## Is Array Sorted 
```
class A{
    public static boolean isSorted(int[] arr){
        for(int i = 0 ; i < arr.length - 1 ; i++){
            if(arr[i] > arr[i + 1]){
                return false;
            }
        }
        return true;
    }
    public static void main(String args[]){
        int[] arr = {1,2,3,4};
        System.out.println(isSorted(arr));
    }
}
```

## Missing Number
```
class A{
    public static int miss(int[] arr , int n){
        int total = n * (n + 1) / 2;
        int sum = 0;
        for(int i = 0 ; i < n ; i++){
            sum += arr[i];
        }
        return total - sum;
    }
    public static void main(String args[]){
        int[] arr = {0,1,2,4};
        System.out.println(miss(arr , arr.length));
    }
}
```

## Move Zeroes at the End
```
class A{
    public static void moveZero(int arr[]){
        int j = 0;
        for(int i = 0 ; i < arr.length ;i++){
            if(arr[i] != 0){
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
                j++;
            }
        }
    }
    public static void main(String args[]){
        int[] arr = {0,1,0,3,12};
        moveZero(arr);
        for(int c : arr){
            System.out.println(c);
        }
    }
}
```

## Array Left Rotate By 1
```
class A{
    public static void leftRotate(int arr[]){
        int first = arr[0];
        for(int i = 0 ; i < arr.length - 1; i++){
            arr[i] = arr[i + 1];
        }
        arr[arr.length - 1] = first;
    }
    public static void main(String args[]){
        int arr[] = {1,2,3,4};
        leftRotate(arr);
        for(int x : arr){
            System.out.println(x+" ");
        }
    }
}
```

## Right Rotate Array By 1
```
class A{
    public static void rightRotate(int arr[]){
        int last = arr[arr.length - 1];
        for(int i = arr.length - 1; i > 0 ; i--){
            arr[i] = arr[i - 1];
        }
        arr[0] = last;
    }
    public static void main(String args[]){
        int arr[] = {1,2,3,4};
        rightRotate(arr);
        for(int x : arr){
            System.out.println(x+" ");
        }
    }
}
```

## Two Sum Exist or Not
```
class A{
    public static boolean twoSum(int arr[] , int x){
        for(int i = 0 ; i < arr.length ; i++){
            for(int j = i + 1; j < arr.length ; j++){
                if(arr[i] + arr[j] == x){
                    return true;
                }
            }
        }
        return false;
    }
    public static void main(String args[]){
        int arr[] = {1,2,3,4};
        int x = 5;
        System.out.println(twoSum(arr,x));
    }
}
```

## Three Sum Exit or Not
```
class A{
    public static boolean threeSum(int arr[] , int x){
        for(int i = 0 ; i < arr.length ; i++){
            for(int j = i + 1; j < arr.length ; j++){
                for(int k = j + 1; k < arr.length;k++){
                    if(arr[i]+arr[j]+arr[k] == x){
                        return true;
                    }
                }
            }
        }
        return false;
    }
    public static void main(String args[]){
        int arr[] = {1,2,3,4};
        int x = 6;
        System.out.println(threeSum(arr,x));
    }
}
```


## Find the mAx in an Array
```
class A{
    public static int findMax(int arr[]){
        int max = arr[0];
        for(int i = 1 ;i < arr.length ; i++){
            if(arr[i] > max){
                max = arr[i];
            }
        }
        return max;
    }
    public static void main(String args[]){
        int[] arr = {1,5,2,9};
        System.out.println(findMax(arr));
    }
}
```

## SECOND LARGEST IN AN ARRAY
```
class A{
    public static int secondMax(int arr[]){
        int max = Integer.MIN_VALUE;
        int second = Integer.MIN_VALUE;
        for(int i = 0 ; i < arr.length ; i++){
            if(arr[i] > max){
                second = max;
                max = arr[i];
            }
            else if(arr[i] > second && arr[i] != max){
                second = arr[i];
            }
        }
        if(second == Integer.MIN_VALUE){
            return -1;
        }
        return second;
    }
    public static void main(String args[]){
        int[] arr = {1,5,2,9};
        System.out.println(secondMax(arr));
    }
}
```

## SECOND SMALLEST IN AN ARRAY
```
class A{
    public static int secondMax(int arr[]){
        int min = Integer.MAX_VALUE;
        int second = Integer.MAX_VALUE;
        for(int i = 0 ; i < arr.length ; i++){
            if(arr[i] < min){
                second = min;
                min = arr[i];
            }
            else if(arr[i] < second && arr[i] != min){
                second = arr[i];
            }
        }
        if(second == Integer.MAX_VALUE){
            return -1;
        }
        return second;
    }
    public static void main(String args[]){
        int[] arr = {1,5,2,9};
        System.out.println(secondMax(arr));
    }
}
```

## Insert at a given position
```
class A{
    public static int[] insert(int[] arr,int pos,int val){
        int res[] = new int[arr.length + 1];
        int j = 0;
        for(int i = 0 ; i < res.length ; i++){
            if(i == pos){
                res[i] = val;
            }
            else{
                res[i] = arr[j];
                j++;
            }
        }
        return res;
    }  // 5 6 0 0
    public static void main(String args[]){
        int[] arr = {1,2,3,4};
        int pos = 2;
        int val = 10;
        int[] brr = insert(arr,pos,val);
        for(int x : brr){
            System.out.print(x+" ");
        }
    }
}
```

## Count the Occurence of the given target
```
class A{
    public static int occ(int[] arr , int x){
        int count = 0;
        for(int i = 0 ; i < arr.length ; i++){
            if(arr[i] == x){
                count++;
            }
        }
        return count;
    }
    public static void main(String args[]){
        int arr[] = {1,2,3,2,2,4};
        int x = 2;
        System.out.println(occ(arr,x));
    }
}
```