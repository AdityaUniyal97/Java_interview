# Sorting

# Selection Sort ?
*Selection SOrt is a sorting algorithm where we find the smallest element or the largest element based upon the sorting order than we place them one by one in unsorted part of the array . 
Time Complexity = O(n^2) 
Space Complexity = O(1) (No extra memeory is used)*
```
class Solution {
    void selectionSort(int[] arr) {
        int n = arr.length;
        for(int i = 0 ; i <n ; i++){
            int MI = i;
            for(int j = i+1 ; j < n ; j++){
                if(arr[j] < arr[MI]){
                    MI = j;
                }
            }

            int swap = arr[MI];
            arr[MI] = arr[i];
            arr[i] = swap;
        }
    }
}
```

# What is Bubble Sort ?
*Bubble Sort is a sorting algorithm which repeatedly compares the adjacent element  int the array . Swap them if they are in the wrong order . this process repeat until the array is fully sorted
Tme-Complexity = O(n^2)
Space-Complexity = O(1) (no extra memory is used)*
```
class Solution {
    public static void bubbleSort(int arr[]) {
        int n = arr.length;
        for(int i =0 ; i < n ; i ++){
            boolean swap = true;
            for(int j = 0 ; j < n - i - 1; j++){
                if(arr[j] > arr[j + 1]){
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swap = true;
                }
            }
            if(swap == false){
                break;
            }
        }
    }
}
```
# Insertion Sort ?
*In Insert Sort we Divide our array into two Parts Sorted and Unsorted Part , SO we pick the first element from the unsorted part and put it in its specific position at the sorted part . Repeating this process until the array is completely sorted
Time Complexity 
**BEST CASE** When the entire array is Sorted in that case the while loop will never run and only outer loop will run until n to check  in that case **O(n)**
**Worst Case** When the entire array is sorted in reverse . this means we have to travel the whole loop and also the while loop will also run on every element that will be **O(n^2)**
**Space Complexity = O(1) Since it does not Require Additional Space***
```
class Solution {
    public void insertionSort(int arr[]) {
        int n = arr.length;
        for(int i = 1 ; i < n ; i ++){
            int key = arr[i];
            int j = i - 1;
            while(j >= 0 && arr[j] > key){
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }
    }
}
```

# Merge Sort ?
Merge Sort is  a divide-and-conquer sorting algorithm that:
1. Divide
   - Split the array into two halves left and right
2. Conquer
   - Recursively sort the left and right halves.
3. Combine
   - Merge the two sorted halves into a single sorted array. 
```
class Solution {

    void mergeSort(int arr[], int l, int r) {
        if(l < r){
        int mid = l + (r - l) / 2;
        mergeSort(arr , l , mid);
        mergeSort(arr , mid + 1, r);
        merge(arr , l , mid , r);
       }
    }
    
    private void merge(int[] arr , int left , int mid , int right){
        int n1 = mid - left + 1;
        int n2 = right - mid;
        int[] LA = new int[n1];
        int[] RA = new int[n2];
        for(int i =0 ; i < n1; i++){
            LA[i] = arr[left +  i];
        }
        for(int j = 0 ; j < n2 ; j++){
            RA[j] = arr[mid + 1 + j];
        }
        int i = 0;
        int j = 0;
        int k = left;
        while(i < n1 && j < n2){
            if(LA[i] <= RA[j]){
                arr[k] = LA[i];
                i++;
            }
            else{
                arr[k] = RA[j];
                j++;
            }
            k++;
        }
        while(i < n1){
            arr[k] = LA[i];
            i++;
            k++;
        }
        while(j < n2){
            arr[k] = RA[j];
            j++;
            k++;
        }
    }
```

#  Quick_Sort?
Quick Sort is a divide and conquer shorting algorithm . Where we choose the pivot element and divide the array such that those array element which are lesser than the pivot comes one side and those greter than the pivot comes other side . Function name as the Partition_Function which mantian the order 
```
class Solution {
    static void quickSort(int arr[], int low, int high) {
        if(low < high){
            int pi = partition(arr , low , high);
            quickSort(arr , low , pi - 1);
            quickSort(arr , pi + 1 , high);
        }
    }
    static int partition(int arr[], int low, int high) {
        int pivot = arr[high];
        int i = low - 1;
        for(int j = low ; j < high ; j++){
            if(arr[j] < pivot){
                i++;
                swap(arr , i , j);
            }
        }
        swap(arr , i + 1 , high);
        return i + 1;
    }
    static void swap(int arr[] , int i , int j){
        int temp = arr[i];
        arr[i] = arr[j]; 
        arr[j] = temp;
    }
```