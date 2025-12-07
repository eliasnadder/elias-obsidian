Given a graph, we can use the O(**V**+**E**) DFS (Depth-First Search) or BFS (Breadth-First Search) algorithm to traverse the graph and explore the features/properties of the graph. Each algorithm has its own characteristics, features, and side-effects that we will explore in this visualization.


This visualization is rich with a lot of DFS and BFS variants (all run in O(**V**+**E**)) such as:

1. Topological Sort algorithm (both DFS and BFS/Kahn's algorithm version),
2. Bipartite Graph Checker algorithm (both DFS and BFS version),
3. Cut Vertex & Bridge finding algorithm,
4. Strongly Connected Components (SCC) finding algorithms  
    (both Kosaraju's and Tarjan's version), and
5. 2-SAT Checker algorithm.

## 2. Visualization
When the chosen graph traversal algorithm is running, the animation will be shown here.

We use vertex + edge color (the color scheme will be elaborated soon) and occasionally the extra text under the vertex (in red font) to highlight the changes.

All graph traversal algorithms work on directed graphs (this is the default setting, where each edge has an arrow tip to indicate its direction) but the **Bipartite Graph Check** algorithm and the **Cut Vertex & Bridge** finding algorithm requires the undirected graphs (the conversion is done automatically by this visualization).

## 3. Specifying an input graph
There are three different sources for specifying an input graph:

1. **Edit Graph**: You can draw a new graph or edit an example unweighted directed graph as the input graph (to draw bidirectional edge (u, v), you can draw two directed edges u → v and v → u; or click 'Include Reverse Edges' button to do this for all directed edges).
2. **Input Graph**: You can specify Edge List/Adjacency Matrix/Adjacency List information and VisuAlgo will propose a 2D graph drawing layout of that graph.
3. **Example Graphs**: You can select from the list of our selected example graphs to get you started.