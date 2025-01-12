# Prototype

Submit your answers to the following questions to the 'Prototype' link in the Assessments section of Moodle.

(prototype_part_1)=
## Part 1: Background

The list `x` is the adjacency list of an undirected graph:

```
x = [[3], [11, 6, 5], [4, 11, 5], [0], [2, 6, 6], [12, 19, 2, 1],
    [4, 17, 1, 4, 8], [14, 11], [6], [], [15, 11], [10, 2, 1, 16, 15, 7],
    [5], [], [7], [10, 11], [11], [6, 19], [], [5, 17]]
```

Write Python code to determine the answers to the following questions.

1\. The adjacency list of an undirected graph has the property that for any two nodes `i` and `j`, if `i` is a neighbour of `j` then `j` is a neighbour of `i`. Show that `x` is the adjacency list of an undirected graph.

2\. Find a pair of nodes that are not connected by a path.

3\. Determine the node pair(s) with the maximum path distance in the graph.

4\. Determine all connected components in the graph (full marks if you use a technique which would work for *any* undirected graph regardless of size).

*NB while it might be possible to answer these questions using pen and paper, you should determine your answers using Python code and the computational techniques studied in class. Full marks will be given for answers which use techniques which could work for an undirected graph of ANY size (not just `x`). You should include sufficient text (in the form of Python comments) to explain how your code determines the answer to each question.*

Submit your answers to Part 1 as a single `.py` file.

 **[5 marks]**

(prototype_part_2)=
## Part 2: Prototype

### Step 1

The provided file `sample_neural_circuit.csv` defines the graph of a sample neural circuit, where each row represents a synapse connecting two neurons from `bodyId_pre` to `bodyId_post`. 

Generate a NetworkX object representing the directed graph, then use NetworkX to plot a network diagram of the graph.

 **[3 marks]**

### Step 2

Write Python code to generate the two [degree distributions](https://mathinsight.org/degree_distribution) of a general directed graph. Then plot histograms of the in-degree and out-degree distributions of the sample circuit.

 **[3 marks]**

### Step 3

Write Python code which calculates the motif-frequency spectrum of a general directed graph. For example, write a function which given a NetworkX graph object `G` returns an array of motif frequencies.

Suggested steps:

1. Determine adjacency matrices of the 13 distinct order-3 connected graphs.
2. Write a function `motif_number(H)` which checks whether graph `H` is isomorphic to any of the 13 order-3 graphs, and if so returns its motif number.
3. Write a function `motif_spectrum(G)` which samples all order-3 subgraphs of `G`, determines the motif number of each, then returns the motif frequency spectrum.

Plot the motif-frequency spectrum of the sample circuit.

 **[6 marks]**

### Step 4

Generate a [random graph](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93R%C3%A9nyi_model) with the same number of edges and vertices as the sample circuit. Plot its two degree histograms and its motif frequency spectrum.

 **[3 marks]**

## What to submit

1. For {ref}`prototype_part_1` submit a single `.py` file.
2. For {ref}`prototype_part_2` submit code file(s) and documentation, ideally as a single `.zip` file (in Windows: right click, *Send to > Compressed (zipped) folder*). Key functions should be documented, and you should include clear instructions so that the reader can easily execute and verify your code. You do not need to separately include code outputs, because your code should produce the outputs when executed.

There are 20 marks available for this submission.



