## BFS
```
import java.util.*;
class A{
    public static void main(String args[]){
        int v = 4;
        ArrayList<ArrayList<Integer>> adj = new ArrayList<>();
        for(int i = 0 ; i < v ; i++){
            adj.add(new ArrayList<>());
        }
        adj.get(0).add(1);
        adj.get(2).add(3);
        bfs(adj,v);
    }
    
    public static void bfs(ArrayList<ArrayList<Integer>> adj , int v){
        boolean[] visited = new boolean[v];
        for(int i = 0 ; i < v ; i++){
            if(!visited[i]){
                Queue<Integer> q = new LinkedList<>();
                q.add(i);
                visited[i] = true;
                while(!q.isEmpty()){
                    int node = q.poll();
                    System.out.print(node+" ");
                    for(int nei : adj.get(node)){
                        if(!visited[nei]){
                            visited[nei] = true;
                            q.add(nei);
                        }
                    }
                }
            }
        }
    }
}
```
## Count the Nodes in the Graph
```
import java.util.*;
class A{
    public static void main(String args[]){
        int v = 4;
        ArrayList<ArrayList<Integer>> adj = new ArrayList<>();
        for(int i = 0 ; i < v ; i ++){
            adj.add(new ArrayList<>());
        }
        adj.get(0).add(1);
        adj.get(2).add(3);
        bfs(adj,v);
    }
    public static void bfs(ArrayList<ArrayList<Integer>> adj , int v){
        boolean[] visited = new boolean[v];
        int count = 0;
        for(int i = 0 ; i < v ; i++){
            if(!visited[i]){
                count++;
                Queue<Integer> q = new LinkedList<>();
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
        System.out.println(count);
    }
}
}
```

## Is Graph COnnected or Not 
```
 public static void check(ArrayList<ArrayList<Integer>> adj , int v){
        boolean[] visited = new boolean[v];
        int count = 0;
        for(int i = 0 ; i < v ; i++){
            if(!visited[i]){
                count++;
                Queue<Integer> q = new LinkedList<>();
                q.add(i);
                visited[i] = true;
                while(!q.isEmpty()){
                    int node = q.poll();
                    for(int nei : adj.get(node)){
                        visited[nei] = true;
                        q.add(nei);
                    }
                }
            }
        }
        if(count == 1){
            System.out.println("Connected");
        }
        else{
            System.out.println("Not Connected");
        }
    }
```

## Shortes Path(Using BFS)
```
 public static void shorted(ArrayList<ArrayList<Integer>> adj , int v){
        int[] dist = new int[v];
        Arrays.fill(dist,-1);
        Queue<Integer> q = new LinkedList<>();
        q.add(0);
        dist[0] = 0;
        while(!q.isEmpty()){
            int node = q.poll();
            for(int nei : adj.get(node)){
                if(dist[nei] == -1){
                    dist[nei] = dist[node] + 1;
                    q.add(nei);
                }
            }
        }
        for(int i = 0 ; i < v ; i++){
            System.out.println(i+"->"+dist[i]);
        }
    }
```