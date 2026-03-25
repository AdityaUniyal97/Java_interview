### Add 5 to every number in matrix
# Matrix diagnol sum
```
class Solution {
    public int diagonalSum(int[][] mat) {
        int sum = 0;
        for(int i = 0 ; i < mat.length ; i++){
            for(int j = 0 ; j < mat.length ; j++){
                if(i + j == mat.length - 1 || i == j){
                    sum += mat[i][j];
                }
            }
        }
        return sum;
    }
}
```
# Rotate the Image
```
class Solution {
    public void rotate(int[][] matrix) {
        for(int i = 0 ; i < matrix.length ; i++){
            for(int j = i + 1; j < matrix.length ; j++){
                int temp = matrix[i][j];
                matrix[i][j] = matrix[j][i];
                matrix[j][i] = temp;
            }
        }
        for(int i = 0 ; i < matrix.length ; i++){
            int low = 0;
            int right = matrix.length - 1;
            while(low < right){
                int temp = matrix[i][low];
                matrix[i][low] = matrix[i][right];
                matrix[i][right] = temp;
                low++;
                right--;
            }
        }
    }
}
```
# Rotate 90 Anti clockwise 
1 2 3  
4 5 6  
7 8 9
👉 Output:
3 6 9  
2 5 8  
1 4 7

## Spiral Order Printing

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


# Set Matrix Zero
```
class Solution {
    public void setZeroes(int[][] matrix) {
        int rows = matrix.length;
        int cols = matrix[0].length;
        boolean[] row = new boolean[rows];
        boolean[] col = new boolean[cols];
        for(int i = 0 ; i < rows ; i++){
            for(int j = 0 ; j < cols ; j++){
                if(matrix[i][j] == 0){
                    row[i] = true;
                    col[j] = true;;
                }
            }
        }
        for(int i = 0 ; i < rows ; i++){
            for(int j = 0 ; j < cols ; j++){
                if(row[i] || col[j]){
                    matrix[i][j] = 0;
                }
            }
        }
    }
}
```

## Product Except Itself 
```
class Solution {
    public int[] productExceptSelf(int[] nums) {
        int n = nums.length;
        int ans[] = new int[n];
        ans[0] = 1;
        for(int i = 1; i < n ; i++){
            ans[i] = ans[i - 1] * nums[i - 1];
        }

        int right = 1;
        for(int i = n - 1; i >= 0 ; i--){
            ans[i] = ans[i] * right;
            right = right * nums[i];
        }
        return ans;
    }
}
```

## Is Anagram
```
class Solution {
    public boolean isAnagram(String s, String t) {
        if(s.length() != t.length()){
            return false;
        }
        int count[] = new int[26];
        for(int i = 0 ; i < s.length(); i++){
            count[s.charAt(i)-'a']++;
            count[t.charAt(i)-'a']--;
        }

        for(int i = 0 ; i < 26 ; i++){
            if(count[i] != 0){
                return false;
            }
        }
        return true;
    }
}
```

