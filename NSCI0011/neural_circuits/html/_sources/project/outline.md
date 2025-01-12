# Guidance

The aim of this project is to perform a 'motif frequency analysis' of the *Drosophila Melanogaster* connectome. Motif analysis is described in Chapter 8.1 of {cite:p}`fornito2016fundamentals` and you should read this chapter carefully for essential background. Some of the cited articles may also prove useful. 

A motif is a small graph with a specific structure, and motif analysis involves counting the frequency that a particular set of motifs appear as a subgraph of a graph of interest (in our case, a graph representing a brain circuit). You should perform a motif analysis for the motifs of order 3 (as shown in the project brief).

Motif analysis requires us to determine whether two graphs (a motif and a subgraph of the connectome) are 'the same'. In graph theory, two graphs are the same if they are *isomorphic*. Graph isomorphisms are explained in {numref}`graph_isomorphisms_section` of these notes. Checking if two graphs are isomporphic is a [hard](https://en.wikipedia.org/wiki/Graph_isomorphism_problem) computational problem, but fortunately you don't need to write this algorithm yourself since you can make use of a Python library [NetworkX](https://networkx.org/) which contains functions for checking graph isomorphism, as well as other useful functions.

You'll need to determine how to sample subgraphs from a connectome graph. If the connectome graph is small enough, it's possible to sample *every* triplet of nodes but this may be infeasible for larger connectome graphs. In this case a strategy of random sampling might prove more effective.

The graph of the *Drosophila Melanogaster* connectome can be downloaded from https://neuprint.janelia.org/ as a text file. It can be tricky to access it from the web site, so it will also be made available here. You will have to determine how best to interpret the data as a directed graph and how to load it into Python using NetworkX.

Lastly, in order to determine whether any of the motifs appear at a higher or lower frequency than expected, you should build a *null model* which acts as a 'reference' or 'control'. The easiest way to do this is by generating a suitable [random graph](https://en.wikipedia.org/wiki/Random_graph).

## NewtorkX

You will also need to understand how to use the [NetworkX](https://networkx.org/) Python package. Work through the [tutorial](https://networkx.org/documentation/stable/tutorial.html) first.

Check that you understand how to use the NewtorkX function `is_isomorphic`. The following exercise would be good a good (and useful) exercise to get you started.

```{exercise}
Write Python code which uses `NetworkX` to calculate and graph the [node degree histogram](https://mathinsight.org/degree_distribution) of an arbitrary graph.
```

## Motif Frequency Analysis

The core programming task is to develop code which calculates the triplet motif frequency spectrum of a given graph. Think about how to split this problem up into discrete funcions. For example,
1. A function which determines whether a subgraph (identified by a list of nodes) of a given graph (identified by an adjacency list or NetworkX object) is isomorphic to a second given graph. Test your function against a known graph (eg the *C Elegans* Egg-laying circuit). You can use NetworkX to test for graph isomorphism.
2. A function which determines whether a given subgraph of given graph is isomorphic to one of the triplet motifs.

Don't get too stuck with this part! If you're not sure how to proceed then please come to me for guidance.

## Drosophila Connectome Data

The connectome data can be found [here](https://dvid.io/blog/release-v1.2/#downloads). Select the link 'a compact (44MB) data model' to download the dataset. First you'll need to uncompress the file - you may need to download a utility such as 7Zip to do this.

Inside you will find three files `traced-neurons.csv`, `traced-roi-connections.csv` and `traced-total-connections.csv`. `traced-neurons.csv` contains information just about the neurons (the nodes of the graph) and the other two contain the graph connectivity data in edge list form. `traced-roi-connections.csv` contains additional information about each synapse (which are the graph edges) indicating which brain region it resides in.

The Paper {cite:p}`xu2020connectome` describes how the data was collected. The researchers collected a huge amount of data by imaging brain slices, and from this they determined the connectivity data. The paper contains a lot of information about how the data was collected, most of which you do not need to read in any detail; however you should definitely read Section 1 (Introduction) which contains useful background.

The complete graph is gigantic so I suggest that you pick a single brain region to analyse. The file `traced-roi-connections.csv` breaks down the graph by brain region.

The data files are in `csv` ('comma separated values') format. You should open the files in a text editor to understand how they are formatted. Your computer might try to open then in Excel or another spreadsheet program --- avoid this and instead use a text editor so that you can view the raw data.

The easiest way to import the data into Python is to use the `Pandas` Library. Use the function `Pandas.read_csv` to import the data as a DataFrame, then `NetworkX` has a function `from_pandas_dataframe` which will convert it to a graph.

You will notice that the data contains a column called 'weight'. This column describes the strength of each synaptic connection, so you'll have to decide how best to handle this value (perhaps by setting a threshold).

## Null Models

A *null model* serves as a reference to which we can compare the statistics calculated from the *drosophila* connectome. By comparing the motif frequency histograms of the connectome data and the null model, we can begin to establish which motifs appear more (or less) frequently than chance. The simplest null model is a random graph with the same number of nodes and edges as the graph derived from the connectome data. You should start off by constructing a [random graph](https://en.wikipedia.org/wiki/Erd%C5%91s%E2%80%93R%C3%A9nyi_model) matched by number of nodes and edges, but could consider more sophisticated null models. Read Chapter 10 of {cite:p}`fornito2016fundamentals` for more details.

## Schedule

You should expect to spend no more than 1 or 2 weeks developing code to calculate the motif frequency spectrum. Understanding how to convert the *drosophila* data into a graph might take another week, and the rest of the time should be spent generating results and writing your report.

## References

```{bibliography}
```
