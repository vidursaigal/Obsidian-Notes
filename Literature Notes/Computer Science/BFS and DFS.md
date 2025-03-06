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
- In a **directed graph**, each edge has a direction, meaning if \((i, j) \in E\), then the edge goes from vertex \(i\) to vertex \(j\) but not necessarily the other way around.
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
  \[
  m \leq n(n - 1)
  \]
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
