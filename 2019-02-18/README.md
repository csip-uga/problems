---
title: "Greed is Good"
date: 2019-02-18
---

# Greed is Good

A greedy algorithm is a simple, intuitive algorithm that is used in optimization problems. True to it's name - a greedy algorithm always makes the choice that appears to be the best at that moment. The hope is that a locally-optimal solution will lead us to a globally-optimal solution.

```
Finding the largest integer using greedy choices (marked with an x)
                    ----
                     7x
                   /   \
                  3      12x
                /   \      \
               1     2      19x
```


Greedy algorithms work well when you have a problem that needs to be optimized (either maximized or minimized) at a given point. At each decision, the greedy algorithm has only **one** chance to make a decision so it never goes back and reverses the decision. You will notice this is very different than backtracking or dynamic programming! Due to this behaviour, a greedy strategy can often result in the wrong solution as seen in the example below:

```
Finding the largest integer using greedy choices (marked with an x)
                    ----
                     7x
                   /     \
                  3       12x
                /   \    /   \
              99     2  5     6x
```

Obviously the correct value should be **99** but the greedy algorithm fails to find the largest sum. This error is due to it making decisions only based on information available on a given step rather than evaluating the problem as a whole. With that being said, greedy algorithms are really successful with other types of problems such as Huffman encoding, used for data compression, and Dijkstra's Shortest Path Algorithm.

# Minimum Spanning Trees

One classic problem in Computer Science with a greedy solution is to find the minimum spanning tree of a connected graph.

More precisely, a connected graph is one where a path exists from one node to any other node (i.e. there are no "islands" of nodes that are disconnected from the rest), and a tree is a connected graph without cycles. A spanning tree of a connected graph is a subgraph that reaches all nodes without forming a cycle. And the *minimum* spanning tree is a spanning tree of a connected graph which has the lowest sum of weights.

The figure below shows a connected weighted graph and highlights its minimum spanning tree.

![A connected graph and its minimum spanning tree](https://upload.wikimedia.org/wikipedia/commons/d/d2/Minimum_spanning_tree.svg)

Your task is to find the minimum spanning tree of a given graph.

## Input

You will be given a list of edges representing the graph. Each edge consists of three integers `(A, B, W)` where `A` and `B` are IDs for the nodes connected by the edge and `W` is the weight of the edge. Since these are undirected graphs, the relative order of `A` and `B` doesn't matter. For the sake of standardization, we'll say that `A` will always be less than `B`.

## Output

The output is like the input, a list of edges. But the output should only contain the edges which form the minimum spanning tree.

## Example

After assigning integers to each of the nodes, the graph above can be represented by this edge-list:

```
[
    [0, 1, 6],  [0, 2, 3],  [0, 3, 9],
    [1, 2, 4],  [1, 4, 2],  [1, 5, 9],
    [2, 4, 2],  [2, 3, 9],  [2, 6, 9],
    [3, 6, 8],  [3, 7, 18], [4, 5, 9],
    [4, 6, 8],  [5, 6, 7],  [5, 8, 4],
    [5, 9, 5],  [6, 7, 10], [6, 9, 9],
    [7, 8, 4],  [7, 9, 3],  [8, 9, 1]
]
```

The output are just those edges which form the minimum spanning tree:

```
[
    [0, 2, 3],
    [1, 4, 2],
    [2, 4, 2],
    [3, 6, 8],
    [4, 6, 8],
    [5, 6, 7],
    [5, 8, 4],
    [7, 9, 3],
    [8, 9, 1]
]
```

The relative order of edges is irrelevant in both the input and output.


# Solutions

As usual, [sample solutions][csip-uga/archive] are posted on GitHub.

[csip-uga/archive]: https://github.com/csip-uga/archive
