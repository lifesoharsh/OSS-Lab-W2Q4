C++ program of Kruskal's algorithm to find the Minimum Spanning Tree (MST) of a given connected, undirected, and weighted graph.

V and E: Represent the number of vertices and edges in the graph, respectively.
edges: A vector of pairs, where each pair represents an edge with a weight and a pair of vertices (w, {u, v}).

Constructor (Graph(int V, int E)): Initializes the number of vertices and edges.
addEdge(int u, int w, int v): Adds an edge to the graph, where u and v are vertices and w is the weight of the edge.
kruskalMST(): Calculates the Minimum Spanning Tree using Kruskal's algorithm.

parent: An array representing the parent of each element in the disjoint set.
rnk: An array used to keep the rank (or depth) of each tree.
n: The number of elements in the disjoint set.

Constructor (DisjointSets(int n)): Initializes the parent and rank arrays. Each element is its own parent initially, and the rank is set to 0.
find(int u): Finds the representative of the set containing u with path compression to speed up future operations.
merge(int x, int y): Merges two sets containing x and y. It uses union by rank to keep the tree shallow.

Steps in kruskalMST:
1. Initialize MST Weight (mst_wt): Starts the MST weight at 0.
2. Sort Edges: Sorts the edges in increasing order based on their weight.
3. Create Disjoint Sets: Initializes a disjoint set structure for the vertices.
4. Iterate Over Edges:
   *For each edge, it finds the sets (or parents) of the vertices.
    *If the vertices are in different sets (i.e., adding the edge does not form a cycle), it includes the edge in the MST,
    updates the MST weight, and merges the sets.
