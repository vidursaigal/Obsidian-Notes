# Understanding Graphs: Definitions and Properties

A **graph** is a mathematical structure used to model relationships between objects. It consists of:
- **Vertices (V)**: Also called nodes, these represent the individual elements of the graph.
- **Edges (E)**: These are the connections between the vertices.

Formally, we define a graph as:
$$
G = (V, E)
$$
where  $$E \subseteq V \times V \ $$, meaning that edges are pairs of vertices.

---

## Types of Graphs

### 1. Directed vs. Undirected Graphs
- In an **undirected graph**, all edges are bidirectional, meaning if \((i, j) \in E\), then \((j, i) \in E\) as well.
### 2. Graph Connectivity
A **connected graph** is one in which, for any two vertices \( u \) and \( v \), there exists a path between them.

---

## Edge Constraints

The number of edges (\( m \)) in a graph depends on whether it is directed or undirected:

### **Undirected Graph**
- Since each edge is bidirectional, an undirected graph must satisfy:
  $$
  m \leq \frac{n(n-1)}{2}
  $$
  This represents the maximum number of edges in a fully connected undirected graph (i.e., a **complete graph**).

### **Directed Graph**
- In a directed graph, each vertex can have an edge to any other vertex, so:
   $$
  m \leq n(n - 1)
 $$
  This accounts for all possible directed edges between \( n \) vertices.

From this, we can conclude:
 $$
m = O(n^2)
 $$
and
 $$
\log m = O(\log n)
 $$

### **Minimum Edges for Connectivity**
For an **undirected connected graph**, at least \( n - 1 \) edges are required:
 $$
m \geq n - 1
 $$
This corresponds to a **tree**, which is the sparsest possible connected graph.

---

## Sparse vs. Dense Graphs
- A **sparse graph** has relatively few edges, typically on the order of \( \Theta(n) \).
- A **dense graph** has a number of edges approaching the maximum possible, often on the order of  $$\Theta(n^2)  $$
In summary:
- **Sparse graphs:** \( m = O(n) \) (e.g., trees, some real-world networks)
- **Dense graphs:** \( m = O(n^2) \) (e.g., complete graphs)

---

## Key Takeaways
- Graphs consist of **vertices (V)** and **edges (E)**.
- **Undirected graphs** have bidirectional edges, while **directed graphs** have one-way edges.
- The maximum number of edges is **\( O(n^2) \)** in both directed and undirected graphs.
- A **connected undirected graph** must have at least **\( n - 1 \)** edges.
- **Sparse graphs** have fewer edges (\( O(n) \)), while **dense graphs** have many edges (\( O(n^2) \)).

---
![[Pasted image 20250305203425.png]]

Adjacency List: 
- Most space efficient solution for sparse graphs

Step 1: Create a list for each vertex; the first element in that list is that vertex
Step 2: Put all connected neighbors of that vertex in the list (one away)


Adjacency Matrix:
- Storing data regardless of whether or not there is a connection between two nodes 
- Adding an edge or testing for the presence of an edge is much quicker than adjacency list
- The adjacency matrix can check if (i, j) is an edge in G in constant time, whereas the adjacency list representation must iterate through up to deg(i) list entries
- The adjacency matrix takes Θ(n 2 ) space, whereas the adjacency list takes Θ(m + n) space. 
- The adjacency matrix takes Θ(n) operations to enumerate the neighbors of a vertex v since it must iterate across an entire row of the matrix. The adjacency list takes deg(v) time.
- If the graph is dense and the number of edges is nearly n squared, a matrix makes sense

Step 1: Create a mxm matrix where m is a list of the vertices. 
Step 2: Put a 1 where there is a connection between nodes, put a 0 where there is no connection between nodes. 

---
Connectivity: 
Is there a path from s (source node) to t (target node)? 
- BFS and DFS give us two different algorithms to determine this

---
Breadth-First Search:
![[Pasted image 20250305205116.png]]![[Pasted image 20250305205219.png]]

---
Depth-First Search:
![[Pasted image 20250305210616.png]]![[Pasted image 20250305210629.png]]
![[Pasted image 20250305210648.png]]
DFS can be implemented either recursively or using a stack.

