## Transpose of a matrix
```
class Solution {
    public int[][] transpose(int[][] matrix) {
        int m = matrix.length;
        int n = matrix[0].length;
        int[][] res = new int[n][m];
        for(int i = 0 ; i < m ; i++){
            for(int j = 0 ; j < n ; j++){
                res[j][i] = matrix[i][j];
            }
        }
        return res;
    }
}
```

## Rotate Image 
Input: matrix = [[1,2,3],
            [4,5,6],
            [7,8,9]]
Output: [  [7,4,1],
        [8,5,2],
        [9,6,3]]

```
class Solution {
    public void rotate(int[][] matrix) {
        for(int i = 0 ; i < matrix.length ; i++){
            for(int j =  i + 1 ; j < matrix[0].length ; j++){
                int temp = matrix[i][j];
                matrix[i][j] = matrix[j][i];
                matrix[j][i] = temp;
            }
        }

        for(int i = 0 ; i < matrix.length ; i++){
            int left = 0;
            int right = matrix.length - 1;
            while(left < right){
                int temp = matrix[i][left];
                matrix[i][left] = matrix[i][right];
                matrix[i][right] = temp;
                left++;
                right--;
            }
        }
    }
}
```

## 1886 Determine wheather can be obtained be rotating it 0,90 , 180,270,360 
```
class Solution {
    public boolean findRotation(int[][] mat, int[][] target) {
        for (int k = 0; k < 4; k++) {
            boolean same = true;
            for (int i = 0; i < mat.length; i++) {
                for (int j = 0; j < mat.length; j++) {
                    if (mat[i][j] != target[i][j]) {
                        same = false;
                        break;
                    }
                }
                if (!same) {
                   break;
                }
            }
            if(same){
                return true;
            }
            for(int i = 0 ; i < mat.length ; i++){
                for(int j = i + 1; j < mat.length ; j++){
                    int temp = mat[i][j];
                    mat[i][j] = mat[j][i];
                    mat[j][i] = temp;
                }
            }
            for(int i = 0 ; i < mat.length ; i++){
                int left = 0;
                int right = mat.length - 1;
                while(left < right){
                    int temp = mat[i][left];
                    mat[i][left] = mat[i][right];
                    mat[i][right] = temp;
                    left++;
                    right--;
                }
            }
        }
        return false;
    }
}
```

## Rotate Array K times 
```
class Solution {
    public void reverse(int nums[] , int left , int right){
        while(left < right){
            int temp = nums[left];
            nums[left] = nums[right];
            nums[right] = temp;
            left++;
            right--;
        }
    }
    public void rotate(int[] nums, int k) {
        k = k % nums.length;
        reverse(nums,0,nums.length-1);
        reverse(nums,0,k-1);
        reverse(nums,k,nums.length - 1);
    }
}
```