# Graph



<!--more-->

{{< admonition type=note title="Note" open=true >}}
_Use the table of contents to navigate to the portion that you are interested in._
{{< /admonition >}}



# Intro:

# Traversal in graph:
### Bfs:

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

### Dfs: 
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
# conversion from adjacency matrix to adjancency list


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
                    q.push({{i, j} , 0});
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
                    q.push({{nrow,ncol}, t+1});
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

