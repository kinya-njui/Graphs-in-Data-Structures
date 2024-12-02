# Graphs in Data Structures

Graphs are a powerful and versatile data structure widely used in computer science to represent and analyze relationships between entities. This guide will help beginners understand the basics of **graphs**, with a focus on the distinctions between **directed vs. undirected graphs** and **weighted vs. unweighted graphs**.

---

## **What is a Graph?**

A **graph** consists of:
1. **Vertices (Nodes)**: Represent entities or objects (e.g., people, cities, devices).
2. **Edges**: Represent connections or relationships between vertices.

Graphs are used to model real-world scenarios like:
- **Social Networks**: Users (nodes) and their friendships (edges).
- **Transportation Maps**: Cities (nodes) and roads (edges).
- **Communication Networks**: Devices (nodes) and data connections (edges).

---

## **Types of Graphs**

### **1. Directed vs. Undirected Graphs**

#### **Directed Graphs (Digraphs)**

- **Definition**:  
  In a directed graph, edges have a specific direction. A connection goes from one vertex to another, and the order matters.

- **Key Characteristics**:  
  - Direction is indicated using an arrow.
  - Not all relationships are bidirectional.

- **Examples**:  
  - **Twitter**: If User A follows User B, there’s a directed edge from A to B, but not necessarily from B to A.
  - **Road Map**: One-way streets are represented as directed edges.

- **Representation**:

```
A → B → C
```

- **Applications**:  
- Task scheduling (workflows with dependencies).
- Modeling traffic flow or navigation.

---

#### **Undirected Graphs**

- **Definition**:  
In an undirected graph, edges have no direction. The relationship between vertices is bidirectional and mutual.

- **Key Characteristics**:  
- Connections are represented by simple lines without arrows.
- The order of vertices does not matter.

- **Examples**:  
- **Facebook**: If User A is friends with User B, then User B is also friends with User A.
- **Collaboration Networks**: Team members working on projects.

- **Representation**:

```
A — B — C
```

- **Applications**:  
- Modeling undirected communication (e.g., phone lines).
- Representing mutual partnerships or connections.

---

### **2. Weighted vs. Unweighted Graphs**

#### **Weighted Graphs**

- **Definition**:  
Edges in a weighted graph have a value (weight) assigned to them. This weight often represents:
- Distance
- Cost
- Time

- **Key Characteristics**:  
- Each edge is labeled with a weight.
- Weights add extra meaning to connections.

- **Examples**:  
- **Google Maps**: Cities (nodes) are connected by roads (edges), and weights represent distances.
- **Airline Routes**: Airports (nodes) connected by flights with weights as ticket prices or distances.

- **Representation**:

```
A —(5)— B —(3)— C
```

- **Applications**:  
- Shortest path algorithms (e.g., Dijkstra’s Algorithm).
- Network optimization.

---

#### **Unweighted Graphs**

- **Definition**:  
In an unweighted graph, all edges are treated equally, without any assigned weights.

- **Key Characteristics**:  
- Simple connections with no additional cost or value.
- Edges are either present or absent.

- **Examples**:  
- **Social Networks**: Basic friendships where all connections are equal.
- **Simple Communication Networks**: Where devices are either connected or not.

- **Representation**:

```
A — B — C
```

- **Applications**:  
- Analyzing basic connectivity in networks.
- Exploring graph traversals (e.g., Breadth-First Search).

---

## **Graph Representations**

Graphs can be represented in memory using different techniques. The choice of representation depends on the problem being solved.

### **1. Adjacency Matrix**

- **Definition**:  
A 2D array where `matrix[i][j]` is:
- `1` (or the weight) if there’s an edge between vertex `i` and vertex `j`.
- `0` if there’s no edge.

- **Pros**:  
- Simple and easy to implement.
- Efficient for dense graphs (graphs with many edges).

- **Cons**:  
- Uses more memory for sparse graphs.

- **Representation**:

```
A [0, 1, 0] B [1, 0, 1] C [0, 1, 0]
```

---

### **2. Adjacency List**

- **Definition**:  
A collection of lists, where each vertex has a list of its neighbors.

- **Pros**:  
- Space-efficient for sparse graphs.
- Easier to traverse neighbors.

- **Cons**:  
- Less efficient for dense graphs.

- **Example**:

```python
graph = {
    'A': ['B'],
    'B': ['A', 'C'],
    'C': ['B']
}
