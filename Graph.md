# Graphs

## Tutorials
[freeCodeCamp.org](https://www.youtube.com/watch?v=09_LlHjoEiY)

## Nomenclature
* Graphs (typically undirected (bi directional))
* Directed Graphs (DiGraph)
* Tree (undirected graph no cycles)
* Rooted Tree (tree with a designated root node (away or toward)
* Arborescence (out-tree) edges point away from the root
* Directed Acyclic Graphs (DAG) 

## Representations
1. Adjacency matrix: 
>>>       A  B  C  D 
>>>      ____________
>>>   A | 0 -4  1  9      Edge B -> C  has weight 5
>>>   B | 3  0  5  8
>>>   C | 4  1  0  2
>>>   D | 6  7 -3  0

   Pros | Space efficient for dense graphs
        | Edge lookup in O(1)
   Cons | Requires O(V^2) space
        | Iterating over edges in O(V^2)

2. Adjacency List

>>> A -> [(B,-4), (C, 1), (D, 9)]
>>> B -> [(A, 3), (C, 5), (D, 8)]      Node B can reach Nodes A, C, D

   Pros | Space efficient for sparse graphs
        | Iterating over edges is efficient
   Cons | Less space efficient for dense graphs 
        | Edge lookup in O(E)

3. Edge List (Rarely used)

>>> [ (A, B, -4), (A, C, 1), (A, D, 9)]

   Pros | Space efficient for sparse graphs
        | Simple for some handful algorithms 
        | Iterating over edges is efficient
   Cons | Lacks structure
        | Edge lookup in O(E)


## Algorithms
* Depth first search
* Breath first search
* Shortest path (A*, Dijkstra, Single Source Shortest Path)
* Topological Ordering (on DAGs only)
* Negative cycles (Bellman-Ford, Floyd-Warshall) [Arbitrage]
* Strongly connected components (SCC) [self-contained cycles inside a graph] (Tarja or Kosaraju)
* Traveling Salesman (Held-Karp, Branch and Bound)
* Bridges [Edges whose removal increases the number of connected components, weakness in the graph]()
* Articulation Points [Nodes whose removal increases the number of connected components, weakness in the graph]()
* Minimum Spanning Tree [Subset of edges that connects the tree without cycles and minimum total edge weights] (Kruskal, Prim, Boruvka)
* Max Flow [Maximum flow through the network] (Ford-Fulkerson, Edmonds-Karp, Dinic)

## Depth First Search (DFS)
* Runs in `O(V+E)`
* Used for Connected Components, Finding Bridges and Articulations

>>> n = # nodes in graph
>>> g = adjacency list of the graph 
>>> visited_nodes = [ false, false, ..., false] 
>>>
>>> function dfs(at):
>>>   if visited_nodes[at]: return
>>>   visited_nodes[at] = true
>>>   neighbors = graph[at]
>>>   for next in neighbors:
>>>      dfs(next)


* Uses:
  + Minimum Spanning Tree
  + Cycles in Graphs
  + If Graph is ByPartite
  + Strongly Connected Components
  + Topologically sort nodes in a graph
  + Find Bridges and Articulation Points
  + Find Augmenting Paths in a Flow Network
  + Generate Mazes


## Breadth First Search (BFS)
* Runs in O(V+E)
>>> n = # nodes in graph
>>> g = adjacency list of the graph 
>>>
>>> function bfs(start_node, end_node):
>>>    # Do a Search at node s (returns the parent of every node visited)
>>>    previous_nodes = solve(start_node)
>>>    # reconstruct the path from start_node to end_node
>>>    return reconstructPath(start_node, end_node, previous_nodes)
>>> 
>>> function solve(start_node):
>>>    q = queue (with enqueue and dequeue)
>>>    q.enqueue(start_node)
>>>    visited_nodes = [false, false, ..., false] # all nodes
>>>    visited_nodes[start_node] = true
>>>
>>>    previous_nodes = [ null, null, ..., null] # all nodes
>>>    while !q.isEmpty():
>>>        node = q.dequeue()
>>>        neighbors = g.get(node)
>>>        for (next : neighbors):
>>>           if !visited_nodes[next]:
>>>             q.enqueue(next)
>>>             visited_nodes[next] = true
>>>             previous_nodes[next] = node
>>>    return previous_nodes
>>>
>>>  function reconstructPath(start_node, end_node, previous_nodes):
>>>     # reconstruct path going backward from end_node
>>>     path = []
>>>     for (at = end_node, at != null, at = previous_nodes[at]):
>>>       path.add(at)
>>>     path.reverse()
>>>     # if start_node and end_node are connected return the path
>>>     if (path[0] == start_node):
>>>       return path
>>>     return []
* Best uses:
  + Shortest Path

### Tricks with grids
Use as many queues as the dimensions of the grid (2 for 2-d, 3 for 3-d) to avoid having to store the connected links but only the blockers

# Topological Sort (Top Sort)
Determine the ordering on the graph (only works on DAG)
Example: How to compile elements based on dependencies
_Algorithm_ Depth First Search on unvisited nodes, in the dfs recursion, store current node in reverse order

# Shortest/Longest Paths on DAGs
Rem: With negative weight Dijkstra algo may not work
##Single Source Shortest Path (SSSP) 
Leverages topological ordering
Convert shortest to longest path (invert the sign of the edge weights) 
## Dijstra's O(E*log(V))
Rem: requires non negative weights. 
Can speed it up using a D-Heap where D is the average connectivity of nodes (E/V)
