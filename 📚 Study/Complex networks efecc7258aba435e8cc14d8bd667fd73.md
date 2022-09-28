# Complex networks

Credits: 5
Notes: No
Status: Studying
Year: 4

[MyCourses](https://mycourses.aalto.fi/course/view.php?id=37047&section=2)

[Zulip](https://complex-networks-2022.zulip.aalto.fi)

Exam structure:

- 70%: 8 Assignments
- 30%: 1 Project

## Schedule

- Lecture 1: 2h
    - Assignment 1 6h
- [ ]  Lecture 2: ~2h
    - Assignment 2 6h
- [ ]  Lecture 3
    - Assignment 3 7h

## Submission Checklist

- one .pdf file
- one .zip file containing Python code
- submit in My-Courses (Assignments tab)

## Notes

**Complex system** refers to many elements interacting with each other, e.g. ants and birds

Link = edge, node = vertex, network = graph

**Multigraph** is a network with self-loops and multiple edges

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled.png)

**Degree** (k) is the number of neighborns of a node

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%201.png)

**Average degree** ⟨k⟩ of a network is measured as

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%202.png)

**Degree distribution** (P) measures the probabily that a random node has a certain degree (k), if the distribution is real we consider interval $[k_i, k_{i+1}]$

**Clique** is a subgraph where each node has an edge with each other node

**Edge density** (ρ) is the number of edges compared to a funnly connected network

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%203.png)

**Clustering coefficient** (c) of a node (i, v in the example) is the number of neighborns (k, 4 in the example) connected together (E, 1 in the example)

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%204.png)

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%205.png)

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%206.png)

**Transitivity** measures the clustering coefficient globabally, but it’s not exactly the average clusering coefficient

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%207.png)

**Walk** (path) is a sequence of vertices where each consecutive pair is connected by an edge

**Path** (self-avoiding walk/simple path) is a walk where vertices are never repeated

**Diameter** (d) of a network is the maximum distance found in it, where each node is checked for the shortest path

**Coponents** of a not-connected graph are the maximal connected subgraphs

**Tree** is a connected graph with no loops

**K-regular graphs** are networks where all nodes have degree k

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%208.png)

## Lecture 2

## Lecture 3

**Hubs** are notes with very high degree, for instance a big airport

Different ways of writing the expected value

$\langle f(x) \rangle = \sum f(x)p(x)) = E(f(x))$

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%209.png)

Because k is going to infinity then if the power is <0 then it’s a constant, otherwise infinite

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%2010.png)

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%2011.png)

If we have money it means we are going to make more money, a big city is likely to attract more people

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%2012.png)

![Untitled](Complex%20networks%20efecc7258aba435e8cc14d8bd667fd73/Untitled%2013.png)