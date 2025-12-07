## 1. Graph
A graph is made up of _vertices_/nodes and _edges_/lines that connect those vertices.

A graph may be undirected (meaning that there is no distinction between the two vertices associated with each bidirectional edge) or a graph may be directed (meaning that its edges are directed from one vertex to another but not necessarily in the other direction).

A graph may be weighted (by assigning a weight to each edge, which represent numerical values associated with that connection) or a graph may be unweighted (either all edges have unit weight 1 or all edges have the same constant weight).
***
### 1-1. Simple graph
In a simple graph, there is no _(self-)loop_ edge (an edge that connects a vertex with itself) and no _multiple_/_parallel_ edges (edges between the same pair of vertices). In another word: There can only be up to one edge between a pair of distinct vertices.

The number of edges **E** in a simple graph can only range from 0 to O(**$V^2$**).

Graph algorithms on simple graphs are easier than on non-simple graphs.
***
### 1-2. Terminologies, Part 1
An undirected edge **e**: (**u**, **v**) is said to be incident with its two end-point vertices: **u** and **v**. Two vertices are called adjacent (or neighbor) if they are incident with a common edge. For example, edge (0, 2) is incident to vertices 0+2 and vertices 0+2 are adjacent.

Two edges are called adjacent if they are incident with a common vertex. For example, edge (0, 2) and (2, 4) are adjacent.

The degree of a vertex **v** in an undirected graph is the number of edges incident with vertex **v**. A vertex of degree 0 is called an isolated vertex. For example, vertex 0/2/6 has degree 2/3/1, respectively.

A subgraph **G'** of a graph **G** is a (smaller) graph that contains subset of vertices and edges of **G**. For example, a triangle {0, 1, 2} is a subgraph of the currently displayed graph.
***
### 1-3. Terminologies, Part 2
![[Screenshot 2025-12-07 212319.png]]
A path (of length **n**) in an (undirected) graph **G** is a sequence of vertices ${v_0, v_1, ..., v_{n-1}, v_n}$ such that there is an edge between **vi** and $vi+1$ $∀i∈ [0..n-1]$ along the path.

If there is no repeated vertex along the path, we call such path as a simple path.

For example, {0, 1, 2, 4, 5} is one simple path in the currently displayed graph.
***
### 1-4. Terminologies, Part 3
![[Screenshot 2025-12-07 212648.png]]
An undirected graph **G** is called connected if there is a path between every pair of distinct vertices of **G**. For example, the currently displayed graph is not a connected graph.

An undirected graph **C** is called a connected component of the undirected graph **G** if:  
1). **C** is a subgraph of **G**;  
2). **C** is connected;  
3). no connected subgraph of **G** has **C** as a subgraph and contains vertices or edges that are not in **C** (i.e., **C** is the maximal subgraph that satisfies the other two criteria).

For example, the currently displayed graph have {0, 1, 2, 3, 4} and {5, 6} as its two connected components.

A cut vertex/bridge is a vertex/edge that increases the graph's number of connected components if deleted. For example, in the currently displayed graph, there is no cut vertex, but edge (5, 6) is a bridge.
***
### 1-5. Terminologies, Part 4
![[Screenshot 2025-12-07 212917.png]]
In a directed graph, some of the terminologies mentioned earlier have small adjustments.

If we have a directed edge **e**: (**u** → **v**), we say that **v** is adjacent to **u** but not necessarily in the other direction. For example, 1 is adjacent to 0 but 0 is not adjacent to 1 in the currently displayed directed graph.

In a directed graph, we have to further differentiate the degree of a vertex **v** into in-degree and out-degree. The in-degree/out-degree is the number of edges coming-into/going-out-from **v**, respectively. For example, vertex 1 has in-degree/out-degree of 2/1, respectively.
***
### 1-6. Terminologies, Part 5
In a directed graph, we extend the concept of Connected Component (CC) into _Strongly_ Connected Component (SCC). A directed graph **G** is called strongly connected if there is a path **in each direction** between every pair of distinct vertices of **G**.

A directed graph **SCC** is called a strongly connected component of the directed graph **G** if:  
1. **SCC** is a subgraph of **G**;  
2. **SCC** is **strongly** connected;  
3. no connected subgraph of **G** has **SCC** as a subgraph and contains vertices or edges that are not in **SCCC** (i.e., **SCC** is the maximal subgraph that satisfies the other two criteria).

In the currently displayed directed graph, we have {0}, {1, 2, 3}, and {4, 5, 6, 7} as its three SCCs.
***
### 1-7. Terminologies, Part 6
![[Screenshot 2025-12-07 213314.png]]
A cycle is a path that starts and ends with the same vertex.

An acyclic graph is a graph that contains no cycle.

In an undirected graph, each of its undirected edge causes a _trivial_ cycle (of length 2) although we usually will not classify it as a cycle.

A directed graph that is also acyclic has a special name: Directed Acyclic Graph (DAG), as shown above.
***
### 1-8. Special Graphs
![[Screenshot 2025-12-07 213633.png]]
A graph with specific properties involving its vertices and/or edges structure can be called with its specific name, like Tree (like the one currently shown), Complete Graph, Bipartite Graph, Directed Acyclic Graph (DAG), and also the less frequently used: Planar Graph, Line Graph, Star Graph, Wheel Graph, etc.
***
