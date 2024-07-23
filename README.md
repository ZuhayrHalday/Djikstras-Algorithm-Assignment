Here's a GitHub README for your project that includes a detailed description of the program, its functionality, and how to use it:

---

# Shortest Path Algorithms in Java

## Overview

This Java project implements several algorithms for finding the shortest path in a graph. It supports unweighted shortest paths, weighted shortest paths using Dijkstra's algorithm, and shortest paths in graphs with negative weights using the Bellman-Ford algorithm. Additionally, it handles acyclic graphs for shortest path calculations.

## Features

- **Unweighted Shortest Path**: Calculates the shortest path in an unweighted graph using Breadth-First Search (BFS).
- **Weighted Shortest Path**: Calculates the shortest path in a graph with non-negative weights using Dijkstra's algorithm.
- **Negative Weighted Shortest Path**: Calculates the shortest path in graphs with negative weights using the Bellman-Ford algorithm, with detection for negative cycles.
- **Acyclic Graph Shortest Path**: Calculates the shortest path in a Directed Acyclic Graph (DAG) with negative weights.

## Classes

- `Graph`: Contains methods to add edges, run shortest path algorithms, and print paths.
- `Vertex`: Represents a vertex in the graph, including adjacency lists, distance, previous vertex, and a scratch variable used for algorithms.
- `Edge`: Represents an edge between two vertices in the graph.
- `DijkstraPath`: Represents an entry in the priority queue used in Dijkstra's algorithm.
- `GraphException`: Custom exception class for signaling violations of preconditions in the graph algorithms.

## Usage

### Adding Edges

Use the `addEdge` method to add edges to the graph. Each edge is specified by a source vertex, a destination vertex, and a cost.

```java
g.addEdge("A", "B", 5.0);
```

### Running Algorithms

1. **Unweighted Shortest Path**:

   ```java
   g.unweighted("A");
   ```

2. **Weighted Shortest Path (Dijkstra's Algorithm)**:

   ```java
   g.dijkstra("A");
   ```

   Optionally, specify invalid paths to be ignored during the algorithm:

   ```java
   String[][] invalidPaths = { {"A", "B"}, {"B", "C"} };
   g.dijkstra("A", invalidPaths);
   ```

3. **Negative Weighted Shortest Path (Bellman-Ford Algorithm)**:

   ```java
   g.negative("A");
   ```

4. **Acyclic Graph Shortest Path**:

   ```java
   g.acyclic("A");
   ```

### Printing Paths

To print the shortest path to a destination vertex:

```java
g.printPath("B");
```

You can also use `StringBuilder` to capture the output:

```java
StringBuilder output = new StringBuilder();
g.printPath("B", output);
System.out.println(output.toString());
```

## Error Handling

- `GraphException`: Thrown if the graph contains negative edges (for Dijkstra's algorithm) or if a negative cycle is detected (for Bellman-Ford).
- `NoSuchElementException`: Thrown if a specified vertex is not found in the graph.

## Example

Below is a simple example demonstrating how to use the `Graph` class:

```java
public class Example {
    public static void main(String[] args) {
        Graph g = new Graph();
        
        // Add edges
        g.addEdge("A", "B", 5.0);
        g.addEdge("A", "C", 10.0);
        g.addEdge("B", "C", 3.0);
        g.addEdge("C", "D", 1.0);
        
        // Run Dijkstra's algorithm
        g.dijkstra("A");
        
        // Print the shortest path from A to D
        g.printPath("D");
    }
}
```

## Files

- `Graph.java`: Main class file containing the implementation of the graph and algorithms.
- `Vertex.java`: Represents vertices in the graph.
- `Edge.java`: Represents edges between vertices.
- `DijkstraPath.java`: Used for priority queue entries in Dijkstra's algorithm.
- `GraphException.java`: Custom exception for graph-related errors.
