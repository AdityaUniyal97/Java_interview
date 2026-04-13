**A graph is a non-linear data structure used to represent connections between objects, consisting of nodes (vertices) and edges (lines connecting them).**
Graph is use to solve the problem where we need to go from source to destination among many paths (like go from A , to B)
- Edge = which conects vertex
- Vertex = point like (point A , point B)
- Weight = like a cost , time , distance etc from vertex A to B using a edge
-  Direction = We have two types of Graphs  Directed graph(one way direction) , undirected Graph(two way Direction)
- **Cycle and Connected Componenets** = Cycle means if we start from begning point and at the end we reach at start only and it should always be closed loop , not a straight line , Connected graph means all the vertex is being connected with or without forming the cycle 
- Any tree is Graph  ,,,   but any graph may or may not be a tree(because tree dont allow cycle and many or two children has only one parent) 
## Representation of Graph

We have Two Ways:
- Adjacency Matrix = Not necessary 0 or 1 in weighted graph can have values , space = (n * n) , Take huge space
- Adajcency List = Here the List of List if created and it contains node and to which , which it is connected , the problem with the list is sequentail access  ex go to index and than start travelling 0: -> -> -> ->....... travelling itself takes O(n)

## Breadth First Search
- Using Queue(FIFO)( add from rear and remove from front)
- we generally make a node as source than we start doing its bfs

### (Leetcode 547)Number of Provinces
```
class Solution {
    public int findCircleNum(int[][] adj) {
        int count = 0;
        int n = adj.length;
        boolean[] isVisited = new boolean[n];
        for(int i = 0 ; i < n ; i++){
            if(!isVisited[i]){
                count++;
                isVisited[i] = true;
                Queue<Integer> q = new LinkedList<>();
                q.add(i);
                while(!q.isEmpty()){
                    int node = q.poll();
                    for(int j = 0 ; j < n ; j++){
                        if(adj[node][j] == 1 && !isVisited[j]){
                            isVisited[j] = true;
                            q.add(j);
                        }
                    }
                }
            }
        }
        return count;
    }
}
```

Time Complexity = O(n^2) for loop in worst case(adjacency List) , O(c + 2E)(Adajcency List)

## Keys and Rooms 
**Input:** rooms = [[1,3],[3,0,1],[2],[0]]
**Output:** false
**Input:** rooms = [[1],[2],[3],[]]
**Output:** true
**Since the Queestion says distinct we will not use bfs on everytime like we are doing above isntead just call on the source and through its neig mark them true , if any neighbour left out false than return false because givie in adjancecy list form**
```
class Solution {
    public boolean canVisitAllRooms(List<List<Integer>> rooms) {
        int n = rooms.size();
        boolean[] isVisited = new boolean[n];
        Queue<Integer> q = new LinkedList<>();
        q.add(0);
        isVisited[0] = true;
        while (!q.isEmpty()) {
            int node = q.poll();
            for (int nei : rooms.get(node)) {
                if (!isVisited[nei]) {
                    isVisited[nei] = true;
                    q.add(nei);
                }
            }
        }
        for (int i = 0; i < n; i++) {
            if (isVisited[i] == false) {
                return false;
            }
        }
        return true;
    }
}
```

## Find if Path Exisits in Graph
```
class Solution {
    public boolean validPath(int n, int[][] edges, int source, int destination) {
        ArrayList<ArrayList<Integer>> adjency = new ArrayList<>();
        for(int i = 0 ; i < n ; i++){
            adjency.add(new ArrayList<>());
        }
        for(int[] e : edges){
            int u = e[0];
            int v = e[1];
            adjency.get(u).add(v);
            adjency.get(v).add(u);
        }
        boolean[] visited = new boolean[n];
        Queue<Integer> queue = new LinkedList<>();
        queue.add(source);
        visited[source] = true;
        while(!queue.isEmpty()){
            int node = queue.poll();
            if(node == destination){
                return true;
            }
            for(int neighbours : adjency.get(node)){
                if(!visited[neighbours]){
                    visited[neighbours] = true;
                    queue.add(neighbours);
                }
            }
        }
        return false;
    }
}
```