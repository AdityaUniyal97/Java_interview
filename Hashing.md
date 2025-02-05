# Count Distinct Elements from the Array
Time Complexity = O(n)
Sapce Complexity = O(n)
```
    static int countDistinct(int arr[] , int n){
        Set<Integer> hs = new HashSet<Integer>();
        for(int i = 0 ; i < n ; i++){
            hs.add(arr[i]);
        }
        return hs.size();
    }
```

# Count Frequnecy of item in Array
Time Complexity = O(n)
Space Complexity = O(n)
```
static void countfreq(int arr[] , int n){
    Map<Integer , Integer> hmp = new HashMap<Integer,Integer>();
       for(int i = 0 ; i < n ; i++){
           int key = arr[i];
           if(hmp.containsKey(arr[i]) == true){
               hmp.put(arr[i] , hmp.get(arr[i]) + 1);
           }
           else{
               hmp.put(arr[i] , 1);
           }
       }
       for(Map.Entry<Integer , Integer> itr : hmp.entrySet())
           System.out.println(itr.getKey()+" "+itr.getValue());
   }
```

# Common Element from Two Array
Time Complexity = O(m + n)
Sapce Complexity = O(n)
```
public static void intersect(int[] a, int[] b, int m, int n) {
        HashSet<Integer> s = new HashSet<>();
        for (int num : b) {
            s.add(num);
        }
        for (int i = 0; i < m; i++) {
            if (s.contains(a[i])) {
                System.out.print(a[i] + " ");
            }
        }
        System.out.println();
    }

```
# Distinct Elements from Two Array
Time Complexity = O(m + n)
Space Complexity = O(m + n)
```
static int unionSize(int arr1[] , int arr2[] , int m , int n){
        Set<Integer> hs= new HashSet<Integer>();
        for(int i = 0 ; i < m ; i++){
            hs.add(arr1[i]);
        }
        for(int i = 0 ; i < n ; i++){
            hs.add(arr2[i]);
        }
        return hs.size();
    }
```

# Pair with the given Sum
Time-Complexity = O(n)
Space-OCmplexity = O(n)
```
static int pairs(int arr[] , int n , int x){
        HashSet<Integer> us = new HashSet<Integer>();
        for(int i = 0 ; i < n ; i ++){
            if(us.contains(x - arr[i])){
                return 1;
            }
            else{
                us.add(arr[i]);
            }
        }
        return 0;
    }
```

# Sub array with Sum as 0
Time Complexity = O(n) 
Space Complexity = O(n)
```
static int zero(int arr[] , int n){
        HashSet<Integer> us = new HashSet<Integer>();
        int pre = 0;
        us.add(0);
        for(int i = 0 ; i < n ; i++){
            pre += arr[i];
            if(us.contains(pre) == true){
                return 1;
            }
            else{
                us.add(pre);
            }
        }
        return 0;
    }