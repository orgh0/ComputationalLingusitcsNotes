# Graph Semantics

## Chinese Wishper Algorithm
- CW is a very basic algorithm and yet efficient method to partition a weighted undirected graph
- CW tries to find a group of nodes that broadcast the same message to their neighbours

## Intuitive working of the algorithm
- Works in a bottom up fashion
- All the nodes get different classes first
- Nodes are processed for a small number of iterations and then inherit the class of whose sum of edge weight to the current node is maximal.

## Pseudo-Code
```python
initialisation step :
    for all v belonging to V :
        class(v) = <random>

clustering step :
    while there are changes in node classes:
        for all v in V, selected in random order :
            class(v) = highest ranked class in the neighbourhood of v
            where
                rank(class_i) <-- forAll nodes in neighbourhood of v belonging to class_i:
                                    return sum(weights of edges from nodes to v)
```

##Properties of CW
- Efficiency is linear in the number of edges
- COnvergence of the algorithm is not garunteed as due to random processing of the graph
- Suitable for small world graphs
- Fuzzy Partitioning and hierarchial clustering possible

## Application

### Deriving multiple senses of the same word
- Find the neighbouring subgraph formed by the node of the word
- Run CW on the following sub graph
- Each resultant cluster is a sense cluster 

### Acquisition of POS classes
- Words that co-occur significantly with the same neighbours must have the same POS


