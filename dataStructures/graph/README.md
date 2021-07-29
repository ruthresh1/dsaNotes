## Graph

* a graph is a set of nodes that are connected to each other via edges in the form of a network
* a finite set of vertices and edges
* nodes are also called vertices, edges are also called arcs.
* applications
  * map navigation - shortest path between two places
  * social networking - friend suggestion
  * operating system - process dependencies

### Definitions
* node - structre for storing data in a graph, also called a vertex
* edge - a pair(x, y) indicating that node x is connected to node y, it may contain a weight or cost associated with traversing from x to y.
* degree - of a node, is the total number of edges connected to a node
  * in-degree - total number of incoming edges connected to a graph
  * out-degree - total number of outgoing edges connected to a graph
* loop - an edge that goes from and to the same node is called a loop, also called self loop. Eg. pair(A, A)

### Graph types
* undirected - the edges are bi-directional. For example the edge pair(A, B), denotes that the edge connects A to B and B to A.
* directed - the edges are uni-directional. For example, the edge pair(A, B), denotes that edge A connects to B but not vice-versa.

### Graph representation
* #### Adjacency maxtrix
* #### Adjacency list