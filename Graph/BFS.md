
## Find if the Path Exist from the Source to Destination
![](https://assets.leetcode.com/uploads/2021/08/14/validpath-ex1.png)

**Input:** n = 3, edges = [[0,1],[1,2],[2,0]], source = 0, destination = 2
**Output:** true
**Explanation:** There are two paths from vertex 0 to vertex 2:
- 0 → 1 → 2
- 0 → 2
```
class Solution {
    public boolean validPath(int n, int[][] edges, int source, int destination) {
        List<List<Integer>> adj = new ArrayList<>();
        for(int i = 0 ; i < n ; i++){
            adj.add(new ArrayList<>());
        }
        for(int[] edge : edges){
            adj.get(edge[0]).add(edge[1]);
            adj.get(edge[1]).add(edge[0]);
        }
        if(source == destination) return true;
        Queue<Integer> q = new LinkedList<>();
        boolean visited[] = new boolean[n];
        q.add(source);
        visited[source] = true;
        while(!q.isEmpty()){
            int node = q.poll();
            for(int nei : adj.get(node)){
                if(node == destination){
                    return true;
                }
                if(!visited[nei]){
                    visited[nei] = true;
                    q.add(nei);
                }
            }
        }
        return false;
    }
}
```


![](https://assets.leetcode.com/uploads/2020/12/24/graph1.jpg)

**Input:** isConnected = [[1,1,0],[1,1,0],[0,0,1]]
**Output:** 2


```
class Solution {
    public int findCircleNum(int[][] isConnected) {
        int n = isConnected.length;
        List<List<Integer>> adj = new ArrayList<>();
        for(int i = 0 ; i < n ; i++){
            adj.add(new ArrayList<>());
        }
        for(int i = 0 ; i < n ; i++){
            for(int j = 0 ; j < n ; j++){
                if(isConnected[i][j] == 1 && i != j){
                    adj.get(i).add(j);
                }
            }
        }
        boolean[] visited = new boolean[n];
        Queue<Integer> q = new LinkedList<>();
        int pro = 0;
        for(int i = 0 ; i < n ; i++){
            if(!visited[i]){
                pro++;
                q.add(i);
                visited[i] = true;
                while(!q.isEmpty()){
                    int node = q.poll();
                    for(int nei : adj.get(node)){
                        if(!visited[nei]){
                            visited[nei] = true;
                            q.add(nei);
                        }
                    }
                }
            }
        }
        return pro;
    }
}

```