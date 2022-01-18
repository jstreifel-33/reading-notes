# DSA - Graphs

Source: [Code Fellows: Graphs](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/graphs.html)

A graph is a **non-linear** data structure. It is a collection of **vertices** (nodes) potentially connected by segments named **edges**.

Terms to know:

* **Vertex** - also called a node, this is a data object that can have zero or more adjacent vertices.
* **Edge** - the connection between two vertices.
* **Neighbor** - vertices adjacent to a given vertex, connected by an edge.
* **Degree** - number of edges connected to a vertex.

## Types of graphs

* **Undirected** - In an undirected graph, each edge is bidirectional. Edges are used to simply connect vertices, rather than direct flow.
* **Directed (Digraph)** - Every edge is directed. Each node is directed to a next node, with a specific notion of what node is "next."
* **Complete** - A graph where all vertices are connected to every other vertex.
* **Connected** - All vertices have at least one edge.
* **Disconnected** - Some vertices may not have edges. It is possible to have standalone vertices or edges.
* **Acyclic** - A graph without cycles. A directed acyclic graph is also called a DAG (a tree being an example of a DAG)
* **Cyclic** - A graph that has cycles. A cycle is defined as a positive length that starts and ends at the same vertex.

## Graph Representation

### Adjacency Matrix

An **adjacency matrix** is a 2-dimentional array representation of a graph. With `n` vertices, an `n * n` boolean matrix is created, where 1 represents an edge between two vertices.

In a adjacency matrix, an undirected graph will always be symmetric.

* **sparse** graph -> few connections
* **dense** graph -> many connections

(arbitrary I guess idk)

### Adjacency List

An **adjacency list** is the most common representation of graphs, and is a collection of linked lists or arrays listing all connected vertices for each vertex.

While linked lists are great for this, and array of arrays serves just as well. Maybe even a dictionary in Python, honestly.

## Weighted Graphs

**Weighted graphs** have numbers assigned to each edge, called weights.

These can be used to make a **weight matrix** where the weights are used in place of the boolean `1`.

Similarly, adjacency lists for weighted graphs must include both weight and name in each entry, as paired values (tuples would be great here).

## Traversals

### Breadth First

Breadth first traversal uses a Queue system, starting with the "first" vertex, specified when beginning traversal.

In addition to Enqueueing neighbors of each vertex as we Dequeue, we must also track which vertices have been visited using a `visited` set or similar method. This allows us to avoid infinite loops in the case of cyclic graphs.

Reading breadth first pseudo:

```pseudo
ALGORITHM BreadthFirst(vertex)
    DECLARE nodes <-- new List()
    DECLARE breadth <-- new Queue()
    DECLARE visited <-- new Set()

    breadth.Enqueue(vertex)
    visited.Add(vertex)

    while (breadth is not empty)
        DECLARE front <-- breadth.Dequeue()
        nodes.Add(front)

        for each child in front.Children
            if(child is not visited)
                visited.Add(child)
                breadth.Enqueue(child)   

    return nodes;

```

### Depth First

Depth first graph traversal will use a stack, as well as a set or similar for tracking visited vertices. The general flow is:

1. Push root vertex to stack
2. Start while loop while stack not empty
3. Peek top vertex of stack
4. If top vertex has unvisited children, push unvisited children to stack
5. If top vertex has no unvisited children, pop from stack
6. Repeat until stack is empty and loop terminates.

It's *a little weird.*

No pseudo this time, but the provided steps make it pretty clear (I hope) what needs to happen.

## Conclusion

That's it! Feel smart? Good. Graph seems complicated but are used all over, thanks to their relational and flexible nature.

Now go learn some more stuff about graphs. Something something Dijikstra's algorithm.
