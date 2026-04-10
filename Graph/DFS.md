
## template
```
import java.util.*;
class A{
    public static void dfs(int node , boolean[] visited , ArrayList<ArrayList<Integer>> adj){
        visited[node] = true;
        System.out.print(node+" ");
        for(int neih : adj.get(node)){
            if(!visited[neih]){
                dfs(neih,visited,adj);
            }
        }
    }
    public static void main(String args[]){
        int v = 5;
        ArrayList<ArrayList<Integer>> adj = new ArrayList<>();
        for(int i = 0 ; i < v ; i++){
            adj.add(new ArrayList<>());
        }
        adj.get(0).add(1);
        adj.get(1).add(0);
        adj.get(0).add(2);
        adj.get(2).add(0);
        boolean[] visited = new boolean[v];
        dfs(0,visited,adj);
    }
}
```

