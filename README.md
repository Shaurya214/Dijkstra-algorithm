# Dijkstra-algorithm
# Graph and Dijkstra's Algorithm Documentation

## `vertex` Class

- **Purpose**: Represents a node in the graph.

- **Data Members**:
  - `int numAdj`: Number of adjacent vertices (edges).
  - `vertex* prev`: Pointer to the previous vertex in the shortest path.
  - `int dist`: Shortest distance from the source vertex.
  - `vector<pair<vertex*, int>> adjList`: List of adjacent vertices and edge weights.

- **Constructor**:
  - `vertex()`: Initializes `numAdj` to 0.

- **Member Function**:
  - `void addEdge(vertex *v, int w)`: Adds an edge to the adjacency list connecting this vertex to `v` with weight `w`.

---

## `comp` Class

- **Purpose**: Comparator for the priority queue used in Dijkstra’s algorithm.

- **Member Function**:
  - `int operator() (const vertex* u, const vertex* v)`: Compares two vertices by their distances, prioritizing the vertex with the smaller distance.

---

## `graph` Class

- **Purpose**: Represents the graph and performs operations like adding vertices, edges, and running Dijkstra’s algorithm.

- **Data Members**:
  - `int numVertex`: Number of vertices in the graph.
  - `int numEdges`: Number of edges in the graph.
  - `vector<vertex*> vertices`: List of all vertices in the graph.

- **Constructor**:
  - `graph()`: Initializes `numVertex` and `numEdges` to 0.

- **Member Functions**:
  - `void addVertex(vertex &u)`: Adds a vertex to the graph.
  - `void addEdge(vertex &u, vertex &v, int w)`: Adds an edge between vertices `u` and `v` with weight `w`.
  - `void dijkstra(vertex &s)`: Runs Dijkstra’s algorithm starting from vertex `s` to find shortest paths.

- **Private Member Functions**:
  - `void initSS(vertex* s)`: Initializes distances to all vertices as infinity and sets the source vertex’s distance to 0.
  - `void relax(vertex *u, vertex *v, int w)`: Updates the distance to vertex `v` if a shorter path is found through vertex `u`.

---

## How Each Function Works

- **`vertex::addEdge`**:
  - Adds an edge with a specified weight to the current vertex’s adjacency list.

- **`comp::operator()`**:
  - Used to order vertices in the priority queue based on their shortest known distance.

- **`graph::addVertex`**:
  - Adds a vertex to the graph.

- **`graph::addEdge`**:
  - Connects two vertices with an edge of a given weight.

- **`graph::dijkstra`**:
  - Calculates shortest paths from the source vertex using Dijkstra’s algorithm. Initializes distances, processes vertices in order of shortest distance, and updates distances to neighboring vertices.

- **`graph::initSS`**:
  - Prepares the graph for Dijkstra’s algorithm by setting initial distances and previous pointers.

- **`graph::relax`**:
  - Updates the distance to a vertex if a shorter path is found through another vertex.
