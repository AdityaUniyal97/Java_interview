## Flood Fill

**Input:** image = [[1,1,1],[1,1,0],[1,0,1]], sr = 1, sc = 1, color = 2
**Output:** [[2,2,2],[2,2,0],[2,0,1]]
**Explanation:**
![](https://assets.leetcode.com/uploads/2021/06/01/flood1-grid.jpg)
```
class Solution {
    public int[][] floodFill(int[][] image, int sr, int sc, int Newcolor) {
        int old = image[sr][sc];
        if(old == Newcolor) return image;
        fill(image , sr , sc , old , Newcolor);
        return image;
    }

    public void fill(int[][] image , int i , int j , int old , int Newcolor){
        if(i < 0 || j < 0 || i >= image.length || j >= image[0].length || image[i][j] != old){
            return;
        }
        image[i][j] = Newcolor;
        fill(image , i + 1 , j , old , Newcolor);
        fill(image , i - 1 , j , old , Newcolor);
        fill(image , i , j + 1 , old , Newcolor);
        fill(image , i , j - 1 , old , Newcolor);
    }
}
```

## MAX Area of Island
![](https://assets.leetcode.com/uploads/2021/05/01/maxarea1-grid.jpg)

**Input:** grid = [[0,0,1,0,0,0,0,1,0,0,0,0,0],[0,0,0,0,0,0,0,1,1,1,0,0,0],[0,1,1,0,1,0,0,0,0,0,0,0,0],[0,1,0,0,1,1,0,0,1,0,1,0,0],[0,1,0,0,1,1,0,0,1,1,1,0,0],[0,0,0,0,0,0,0,0,0,0,1,0,0],[0,0,0,0,0,0,0,1,1,1,0,0,0],[0,0,0,0,0,0,0,1,1,0,0,0,0]]
**Output:** 6
**Explanation:** The answer is not 11, because the island must be connected 4-directionally.
```
class Solution {
    public int maxAreaOfIsland(int[][] grid) {
        int maxA = 0;
        for(int i = 0 ; i < grid.length ; i++){
            for(int j = 0 ; j < grid[0].length ; j++){
                if(grid[i][j] == 1){
                    int area = dfs(grid,i,j);
                    maxA = Math.max(maxA , area);
                }
            }
        }
        return maxA;
    }
    public int dfs(int[][] grid , int i , int j){
        if(i < 0 || j < 0 || i >= grid.length || j >= grid[0].length || grid[i][j] == 0){
            return 0;
        }
        grid[i][j] = 0;
        return 1 + dfs(grid,i+1,j) + 
                   dfs(grid,i-1,j) +
                   dfs(grid,i,j+1) +
                   dfs(grid,i,j-1);
    }
}
```

