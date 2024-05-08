# Graph



<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}



## 1. Intro:

# Traversal in graph:
There are two main type of traversal technique in the graph:
1. BFS: Breadth First Search
2. DFS: Depth First Search

### BFS:
in this traversal technique the traversal will be breadthwise
```c++
// bfs of graph
// 0 based indexing
// gfg ques

// vector<int> adj[]  -> adjacency list
vector<int> bfsOfGraph(int V, vector<int> adj[])
{
    // Code here
    int vis[V] = {0}; // visited arrray mark all element initially zero
    vis[0] = 1;       // marked visted  for 0
    queue<int> q;
    q.push(0);       // pushing starting node in the queue
    vector<int> bfs; // to store the bfs traversal of the graph
    while (!q.empty())
    {
        int node = q.front();
        q.pop();
        bfs.push_back(node); // store the node in bfs

        // pushing the neighbors of the node in the queue if not visited
        for (auto i : adj[node])
        {
            if (!vis[i])
            {
                vis[i] = 1; // mark visited
                q.push(i);  // push the node in the queue
            }
        }
    }
    return bfs;
// space complexicity = O(3N) --> O(N)
// time complexicity = O(N) + O(2E)
}


```

### DFS: 
It's a recursive technique here the traversal will be depthwise
```c++

// Function to return a list containing the DFS traversal of the graph.

void dfs(int node, vector<int> adj[], int vis[], vector<int> &ls)
{

    vis[node] = 1;      // mark node visited
    ls.push_back(node); // list to store dfs traversal

    // traverse all its neighbours of the node
    for (auto i : adj[node])
    {
        // if non visited call dfs again
        if (!vis[i])
        {
            // recursive call
            dfs(i, adj, vis, ls);
        }
    }
}
vector<int> dfsOfGraph(int V, vector<int> adj[])
{
    // Code here
    int vis[V] = {0}; // visited array
    int start = 0;
    vector<int> ls; // list to store dfs traversal
    dfs(start, adj, vis, ls);
    return ls;
}
```
### conversion from adjacency matrix to adjancency list
```c++
// conversion from adjacency matrix to adjancency list
vector<int> adjList[V];
for (int i = 0; i < V; i++)
{
    for (int j = 0; j < V; j++)
    {
        if (adj[i][j] == 1 && i != j)
        {
            adjList[i].push_back(j);
            adjList[j].push_back(i);
        }
    }
}
```

### edges are given making the adjacency list
```c
// given: vector<vector<int>> &edges
    // Code here
    vector<pair<int, int>> adj[n + 1];
    for (auto it : edges)
    {
        adj[it[0]].push_back({it[1], it[2]});
        adj[it[1]].push_back({it[0], it[2]});
    }

```

### detect cycle in undirected graph

```c
// detect cycle in undirected graph
bool detect(int src , vector<int> adj[], int vis[]){
    vis[src] = 1;
    queue<pair<int, int> q;
    q.push({src , -1});

    while(!q.empty()){
        int node = q.front().first;
        int parent = q.front().second;
        q.pop();

        for(auto adjnode : adj[node]){
            if(!vis[adjnode]){
                vis[adjnode] = 1;
                q.push({adjnode , node});
            }
            else if(parent != adjnode){
                return true;
            }
        }
    }
    return false;
}
bool iscysle(int v, vector<int> adj[]){
    int vis[v] = {0};
    for(int i=0; i<v; i++){
        if(!vis[i]){
            if(detect(i,adj,vis)){
                return true;
            }
        }
    }
    return false;
}

```
### Detect cycle in directed graph:
```c
// detect cycle in directed graph
// gfg: https://www.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1
bool dfs(vector<int> adj[] , int vis[] , int pathvis[] , int node){
        vis[node] = 1;
        pathvis[node] = 1;
        
        // traverse the adjacent ndoes
        for(auto it : adj[node]){
            if(!vis[it]){
                if(dfs(adj , vis , pathvis , it)){
                    return true;
                }
            }
            
            // if the node has been previously visited
            // but it has to be visited on the same path
            
            else if(pathvis[it]){
                return true;
            }
        }
        
        pathvis[node] = 0;
        return false;
    }
    bool isCyclic(int V, vector<int> adj[]) {
        // code here
        int vis[V]= {0};
        int pathvis[V] = {0};
        
        for(int i =0; i< V; i++){
            if(!vis[i]){
                if(dfs(adj , vis , pathvis , i)){
                    return true;
                }
            }
        }
        return false;
    }
```
### Rotten Oranges:

```c++
int orangesRotting(vector<vector<int>>& grid) {
        // Code here
        int n = grid.size();
        int m = grid[0].size();
        queue<pair<pair<int , int> , int>> q;
        
        int vis[n][m];
        for(int i =0; i < n ; i++){
            
            for(int j =0; j<m ; j++){
                if(grid[i][j] == 2){
                    q.push({i, j} , 0});
                    vis[i][j] = 2;
                }
                else{
                    vis[i][j] = 0;
                }
            }
        }
        
        int tm =0;
        int drow[] = {-1,0,+1,0};
        int dcol[] = { 0 , +1 , 0 , -1};
        while(!q.empty()){
            int r = q.front().first.first;
            int c = q.front().first.second;
            int t = q.front().second;
            tm = max(tm , t);
            q.pop();
            for(int i =0; i < 4 ; i++){
                int nrow = r+drow[i];
                int ncol = c + dcol[i];
                if(nrow >= 0 && nrow < n && ncol >=0 && ncol < m &&vis[nrow][ncol] == 0 && grid[nrow][ncol] == 1){
                    q.push({nrow,ncol}, t+1);
                    vis[nrow][ncol] = 2;
                }
            }
        }
        
        for(int i =0; i<n ; i++){
            for(int j =0 ; j<m ; j++){
                if(vis[i][j] != 2 && grid[i][j] == 1){
                    return -1;
                }
            }
        }
        return tm;
    }
```
### No of islands:


```c++
// Function to find the number of islands.
    
    void dfs(int i,int j,vector<vector<char>> &grid){
        if(i>=grid.size() || j>=grid[0].size() || grid[i][j]=='0' || i<0 || j<0){
        return;
        }
        grid[i][j]='0';
        dfs(i,j-1,grid);
        dfs(i-1,j,grid);
        dfs(i,j+1,grid);
        dfs(i+1,j,grid);
        dfs(i-1,j-1,grid);
        dfs(i-1,j+1,grid);
        dfs(i+1,j-1,grid);
        dfs(i+1,j+1,grid);
        
    }

 
    int numIslands(vector<vector<char>>& grid) {
        // Code here
        
        int n = grid.size();
        int m = grid[0].size();
        // vector<vector<int>> vis(n , vector<int>(m,0));
        int cnt = 0;
        for(int row= 0 ; row< n;row++){
            for(int col =0; col<m; col++){
                if( grid[row][col] == '1') {
                    cnt++;
                    dfs(row,col, grid);
                }
            }
        }
        return cnt;
    }

```
### No of provinces:


```c++
// dfs function
    
    void dfs(int node, vector<int> adj[], int vis[] ){
        
        vis[node] = 1;        // mark node visited
       
        // traverse all its neighbours of the node
        for(auto i: adj[node]){
            // if non visited call dfs again 
            if(!vis[i]){
                // recursive call 
                dfs(i, adj , vis );
            }
        }
    }
    
    int numProvinces(vector<vector<int>> adj, int V) {
        // code here
        
        // conversion from adjacency matrix to adjancency list
        vector<int> adjList[V];
        for(int i =0; i<V ; i++){
            for(int j=0 ; j< V ;j++){
                if(adj[i][j] == 1 && i != j){
                    adjList[i].push_back(j);
                    adjList[j].push_back(i);
                }
            }
        }
        
        int vis[V] = {0};
        int count = 0;
        for(int i = 0; i< V; i++){
            if(!vis[i]){
                count++;
                dfs(i,adjList,vis);
            }
        }
        
        return count;
        
    }
```



### surrounded regins : Replace O's with X's in a given matrix:


```c++
// replace O's with X's in a given matrix
// gfg: https://www.geeksforgeeks.org/problems/replace-os-with-xs0052/1

void dfs(int row, int col, vector<vector<int>> &vis, vector<vector<char>> &mat)
{
    // mark visited
    vis[row][col] = 1;

    // check for all 4 direction up ,right, down, left
    int delrow[] = {-1, 0, +1, 0};
    int delcol[] = {0, +1, 0, -1};

    int n = mat.size();    // row size
    int m = mat[0].size(); // column size

    // traverse in all 4 direction
    for (int i = 0; i < 4; i++)
    {
        // new row and new column
        int nrow = row + delrow[i];
        int ncol = col + delcol[i];

        if (nrow >= 0 && nrow < n && ncol >= 0 && ncol < m && !vis[nrow][ncol] && mat[nrow][ncol] == 'O')
        {
            // recursive call
            dfs(nrow, ncol, vis, mat);
        }
    }
}

vector<vector<char>> fill(int n, int m, vector<vector<char>> mat)
{
    // code here
    // n-> rows;
    // m-> col
    vector<vector<int>> vis(n, vector<int>(m, 0));
    // vector<vector<char>> temp = mat;

    // check first row and last row
    for (int j = 0; j < m; j++)
    {

        // first row
        if (mat[0][j] == 'O' && vis[0][j] == 0)
        {
            // call dfs
            dfs(0, j, vis, mat);
        }

        // last row
        if (mat[n - 1][j] == 'O' && vis[n - 1][j] == 0)
        {
            // call dfs
            dfs(n - 1, j, vis, mat);
        }
    }

    // check first and last column
    for (int i = 0; i < n; i++)
    {

        // first col
        if (mat[i][0] == 'O' && vis[i][0] == 0)
        {
            // call dfs
            dfs(i, 0, vis, mat);
        }

        // last col
        if (mat[i][m - 1] == 'O' && vis[i][m - 1] == 0)
        {
            // call dfs
            dfs(i, m - 1, vis, mat);
        }
    }

    // after checking boundaries mark all remaining Os with Xs in the matrix
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < m; j++)
        {
            if (mat[i][j] == 'O' && !vis[i][j])
            {
                mat[i][j] = 'X';
            }
        }
    }

    return mat;
}

```
## 2. Topological Sort Algo : TOPO Sort
It is applicable only on `DAG` (directed acyclic graph).
only linear ordering of vertices such that if there is an edge between u and v , u always appear before v in ther ordering.

### DFS
`using stack and array`

Apporach:
* Call dfs recursively and reach to the last node.
* Mark it visited.
* Return and push the node into the stack after completion of dfs for that node.
* Pop the stack one by one and store into ans array


```c
void dfs(int node , int vis[] , stack<int>&st , vector<int> adj[]){
    vis[node] = 1;
    for(auto i : adj[node]){
        if(!vis[i]){
            dfs(i,vis,st, adj);
        }
    }
    st.push(node);
}

vector<int> toposort(int v, vector<int> adj[]){
    int vis[v] = {0};
    stack<int> st;
    for(int i =0 ; i< v ; i++){
        if(!vis[i]){
            dfs(i,vis , st , adj);
        }
    }

    vector<int>ans;
    while(!st.empty()){
        ans.push_back(st.top());
        st.pop();
    }
    return ans;
}

```
### KAHN'S Algo : BFS
`queue and array`

Approach:
* insert all nodes with indegree zero in the queue.
* Take them out of the queue and reduce the indegree of the adjacent nodes.

// BFS
// TC: O(V+E)
// V: no of nodes and E: no of edges
```c
vector<int> toposort(int v, vector<int> adj[])
{

    int indegree[v] = {0};
    for (int i = 0; i < v; i++)
    {
        for (auto it : adj[i])
        {
            indegree[it]++;
        }
    }

    queue<int> q;
    for (int i = 0; i < v; i++)
    {
        if (indegree[i] == 0)
        {
            q.push(i);
        }
    }

    vector<int> topo;
    while (!q.empty())
    {
        int node = q.front();
        q.pop();
        topo.push_back(node);
        for (auto it : adj[node])
        {
            indegree[it]--;
            if (indegree[it] == 0)
            {
                q.push(it);
            }
        }
    }
    return topo;
}

```
## 3. Dijkstra Algo
shortesrt path algorythm
it is used for finding the shortest path from one node to another node in the given graph
it can be implemented by three methods
1. using queue(bad)
2. using priority queue(good)
3. using set(better)

time complexicity : Elog(V)

where E is the no of edges ans V is the number of nodes

we do not use queue because in queue there is unnecessary occurance of distance for the same node due to this it takes a lot of time so it is a bad practice.

we use priority queue because it stores the minimum value at the top (min heap) and we need the minimum distance so it is better choice to use pq.

we use set because it has the ability to erase the entry from the set
set stores the unique values and the smallest at the top in ascending order.

Using priority queue:
```c
// dijkstra algo using priority queue
vector<int> dijkstra(int V, vector<vector<int>> adj[], int S)
{
    // Code here
    // using priority queue to sotre the pair of distance and node.
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;

    vector<int> dist(V);
    for (int i = 0; i < V; i++)
    {
        dist[i] = 1e9;
    }

    dist[S] = 0;
    pq.push({0, S});        // storintg the distance of source node zero from the source node.
    while (!pq.empty())
    {
        int dis = pq.top().first;   // first one denotes the distance from the source 
        int node = pq.top().second;     // second denotes the node
        pq.pop();

        for (auto it : adj[node])
        {
            int edgeweight = it[1];
            int adjnode = it[0];

            if (dis + edgeweight < dist[adjnode])
            {
                dist[adjnode] = dis + edgeweight;
                pq.push({dist[adjnode], adjnode});
            }
        }
    }
    return dist;
}

```
Using set
```c
// dijkstra algo using set
vector<int> dijkstra(int v , vector<vector<int>> adj[] , int s){
    set<pair<int , int>> st;
    vector<int> dist(v, 1e9);

    st.insert({0,s});
    dist[s] = 0;
    while(!q.empty()){
        auto it = *(st.begin());
        int distance = it.first;
        int node = it.second;

        st.erase(it);
        for(auto it : adj[node]){
            int adjnode = it[0];
            int edgeweight = it[1];
            if(distance + edgeweight <  dist[adjnode]){
                // erse if it exist
                if(dist[adjnode] != 1e9){
                    st.erase({dist[adjnode] , adj[node]});
                }
                // update the distance
                dist[adjnode] = distance + edgeweight;
                st.insert({dist[adjnode] , adjnode});
            }
        }
    }
    return dist;
}

```


### Shortes path in undirected weighted graph
using dijkstras algo
```c
vector<int> shortestPath(int n, int m, vector<vector<int>> &edges)
{
    // creating adjacency list from the given the edges pair
    vector<pair<int, int>> adj[n + 1];
    for (auto it : edges)
    {
        adj[it[0]].push_back({it[1], it[2]});
        adj[it[1]].push_back({it[0], it[2]});
    }
    // defining the priority queue a min heap concept
    priority_queue<pair<int, int>, vector<pair<int, int>>, greater<pair<int, int>>> pq;
    //creating a distance array and a parent aray to track the path
    // parent array will tell us the node is come from where
    vector<int> dist(n + 1, 1e9), parent(n + 1);
    for (int i = 1; i <= n; i++)
    {
        parent[i] = i;
    }

    dist[1] = 0;
    pq.push({0, 1});
    while (!pq.empty())
    {
        auto it = pq.top();
        int node = it.second;
        int dis = it.first;
        pq.pop();

        for (auto it : adj[node])
        {
            int adjnode = it.first;
            int edw = it.second;
            if (dis + edw < dist[adjnode])
            {
                dist[adjnode] = dis + edw;
                pq.push({dis + edw, adjnode});
                parent[adjnode] = node;
            }
        }
    }
    if (dist[n] == 1e9)
        return {-1};
    // reconstruct the path
    vector<int> path;
    int node = n;
    while (parent[node] != node)
    {
        path.push_back(node);
        node = parent[node];
    }
    path.push_back(1);
    path.push_back(dist[n]);
    reverse(path.begin(), path.end());

    return path;
}

```
