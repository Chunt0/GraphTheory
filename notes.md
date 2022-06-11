# Notes

Questions to ask when dealing with a graph problem:
---------------------------------------------------

- Is the graph directed or undirected?

- Are the edges of the graph weighted?

- Is the graph I will encouter likely to be a sparse or dense with edges?

- Should I use an adjacency matrix, adjacency list, and edge list or other structure
    to represent the graph efficiently

---------------------------------------------------

Problem 1: Shortest Path Problem

Given a weighted graph, find the shrotest path of edges from node A to node Been

Algorithms: Breadth First Search (unweight graphs), Dijkstra's Algo, Bellman Ford
Floyd-Warshall, A*

Problem 2: Connectivity
    
Does there exist a path between node A and node Bellman
Typical SOlution: Use union find data structure or any search algorithm

Problem 3: Negative Cycles

Does my weighted digraph have any negative cycles? If so, where?
Algorithms: Bellman-Ford and Floyd-Warshall

Problem 4: Strongly Connected Components

Strongly Connected Components (SCCs) can be thought of as self-contained cycles
within a directed graph where every vertex in a given cycle can reach every 
other vertex in the same cycle
Algorithms: Tarjan's and Kosaraju's algorithm

Problem 5: Traveling Salesman Problem

Given a list of cities and the distance between each pair of cities, what is
the shortest possible route that visits each city exactly once and returns to
the origin city.
Algorithms: Held-Karp, branch and bound and many approximation algorithms

NP-Hard

Problem 6: Bridges

A bridge/cut edge is any edge in a graph whose removal increase the number 
of connected compoenets

Bridges are important in agraph theory because they oft:wq
en hint at weak points,
bottlenecks or vulnerabilities in a graph

Problem 7: Articulation Points
    
Any node in a graph whose removal increase the number of connected components

Good for same as above

Problem 8: Minimum Spanning Tree

Subset of the edge list that connects every node with a minimum cost

Algorithms: Kruskal's, Prim's and Boruvka's Algorithms

Problem 9: Netowrk Flow: Max Flow

Q: With an inifinte input source how much "flow" can we push through the network

Algorithms: Ford-Fulkerson, Edmonds-Karp and Dinic's algorithms

---------------------------------------------------

Depth First Search
------------------
Great for county connected components, finding connectivity, bridges and articulation points

n = number of nodes in the graph
g = adjacency list representing graph
visited = [false,...,false] # size n

func dfs(at):
if visited[at]: return
visited[at] = true

neighbors = graph[at]
for next in neighbors:
dfs(next)

--> Finding connected components
Coloring = Assign a vlaue to each group to be able to tell components apart
Use a DFS algo -> Start a DFS at each node unless it has already been visited.
Mark all reachable nodes as being part of the same components

func findComponents():
for(i = 0; i < n; i++):
if !visited[i]:
count++
dfs(i)
return (count, components)

What else?
- Computed Min Span Tree
- Detect and find cycles
- Check if a graph is bipartite
- Find strongly connected components
- Topologically sort the nodes of a graph
- Find bridges and articulation points
- Find augmenting paths in a flow network
- Generate mazes

---------------------------------------------------

Breadth First Search
--------------------
Useful for one thing: finding the shortest path on an unweighted graph.

A BFS starts at some arbitrary node of a graph and explores the neighbor nodes
first, before moving to the next level neighbors.

priority_queue = null
n = number of nodes
added = [false,...,false] size n
visited = [false,...,false] size n

priority_queue.add(random_node)
added(random_node)

func bfs(priority_queue):
node = priority_queue.pop()
get_neighbors(node)
for neighbor in get_neighbors:
if neighbor !visited && !added:
priority_queue.add(neighbor)
added(node)
visited(node)
bfs(priority_queue)

---------------------------------------------------

Breadth First Search Grid Shortest Path

A grid is an implicit graph.
    
Take a grid and label each cell from [0,n) where n is the number of cells in the grid
Create an Adjacency list and matrix

  
