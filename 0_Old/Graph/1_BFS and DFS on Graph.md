## Find if the Path Exist in Graph from src to dest
```
class Solution {

    public boolean dfs(int node , int dst , boolean[] visited , ArrayList<ArrayList<Integer>> adj){
        if(node == dst) return true;
        visited[node] = true;
        for(int neigh : adj.get(node)){
            if(!visited[neigh]){
                if(dfs(neigh,dst,visited,adj)){
                    return true;
                }
            }
        }
        return false;
    }

    public boolean validPath(int n, int[][] edges, int source, int destination) {
        ArrayList<ArrayList<Integer>> adj = new ArrayList<>();
        for(int i = 0 ; i < n ; i++){
            adj.add(new ArrayList<>());
        }
        for(int[] e : edges){
            adj.get(e[0]).add(e[1]);
            adj.get(e[1]).add(e[0]);
        }
        boolean[] visited = new boolean[n];
        return dfs(source , destination , visited , adj);
    }
}
```

## Keys and Rooms
**Input: rooms = [[1],[2],[3],[]]
Output: true(we have vsitied every room)**
```
class Solution {

    public void dfs(int room , List<List<Integer>> rooms , boolean[] visited){
        visited[room] = true;
        for(int key : rooms.get(room)){
            if(!visited[key]){
                dfs(key,rooms,visited);
            }
        }
    }

    public boolean canVisitAllRooms(List<List<Integer>> rooms) {
        boolean[] visited = new boolean[rooms.size()];
        dfs(0,rooms,visited);
        for(boolean v : visited){
            if(!v) return false;
        }
        return true;
    }
}
```