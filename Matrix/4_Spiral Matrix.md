
## Spiral Matrix 1
```
 class A{
    public static void main(String args[]){
        int arr[][] ={ 
            {1, 2, 3},
            {4, 5, 6},
            {7, 8, 9}
        };
        int top = 0;
        int bottom = arr.length - 1;
        int left = 0;
        int right = arr[0].length - 1;
        while(left <= right && top <= bottom){
            for(int i = left ; i <= right ; i++){
                System.out.print(arr[top][i]+" ");
            }
            top++;
            
            for(int i = top ; i <= bottom ; i++){
                System.out.print(arr[i][right]+" ");
            }
            right--;
            
            if(top <= bottom){
                for(int i = right ; i >= left ; i--){
                    System.out.print(arr[bottom][i]+" ");
                }
                bottom--;
            }
            
            if(left<=right){
                for(int i = bottom ; i >= top ; i--){
                    System.out.print(arr[i][left]);
                }
                left++;
            }
        }
    }
}
```
## Spiral Matrix 4 (You are given a linked list and two integers `m` and `n`.   Create an `m x n` matrix and fill it in **spiral order** using values from the linked list).
👉 If the linked list ends early, fill remaining cells with `-1`.)
```
class Solution {
    public int[][] spiralMatrix(int m, int n, ListNode head) {
        int[][] mat = new int[m][n];
        for(int i = 0 ; i < m ; i++){
            Arrays.fill(mat[i],-1);
        }
        int top = 0;
        int bottom = m - 1;
        int left = 0;
        int right = n - 1;
        ListNode curr = head;
        while(curr != null){
            for(int i = left ; i <= right && curr!=null ; i++){
                mat[top][i] = curr.val;
                curr = curr.next;
            }
            top++;

            for(int i = top ; i <= bottom && curr != null; i++){
                mat[i][right] = curr.val;
                curr = curr.next;
            }
            right--;

            for(int i = right ; i >= left && curr != null; i--){
                mat[bottom][i] = curr.val;
                curr = curr.next;
            }
            bottom--;

            for(int i = bottom ; i >= top && curr != null; i--){
                mat[i][left] = curr.val;
                curr = curr.next;
            }
            left++;
        }
        return mat;
    }
}
```

## Spiral matrix 2 (Given an integer `n`, create an `n x n` matrix and fill it with numbers from `1` to `n²` in **spiral order (clockwise)** starting from the top-left corner.)
```
class Solution {
    public int[][] generateMatrix(int n) {
        int[][] res = new int[n][n];
        int top = 0;
        int bottom = n - 1;
        int left = 0;
        int right = n - 1;
        int num = 1;
        while (top <= bottom && left <= right) {
            for (int i = left; i <= right; i++) {
                res[top][i] = num;
                num++;
            }
            top++;
            for (int i = top; i <= bottom; i++) {
                res[i][right] = num;
                num++;
            }
            right--;
            if (top <= bottom) {
                for (int i = right; i >= left; i--) {
                    res[bottom][i] = num;
                    num++;
                }
                bottom--;
            }
            if (left <= right) {
                for (int i = bottom; i >= top; i--) {
                    res[i][left] = num;
                    num++;
                }
                left++;
            }
        }
        return res;
    }
}
```