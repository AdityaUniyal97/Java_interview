Binary Search is a searching algorithm which is used for searching an element in an array in o(nlogn) time it optimised the time of search , inserting and deleting
In Binary Search we search the element in the middle of the array if the elemement is same as the one we are finding than we will stop , if it is smaller than go right , if greter than go left

```
def bsearch(l,x):
    low = 0
    high = len(l) - 1
    while low <= high:
        mid = (low + high) // 2
        if l[mid] == x:
            return mid
        elif l[mid] < x:
            low = mid + 1
        else:
            high = mid - 1
    return -1
l = [10,20,30,40,50,60]
print(bsearch(l,50))
```