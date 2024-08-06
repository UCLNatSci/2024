# Epidemic Simulation

## Background

In this project you will develop a simulation which models the spread of a viral infection through a population. Individuals in the population are assumed to be distributed in a grid of cells which might represent a geographical area such as a city or country, and are assigned various states which describe their exposure to the virus. As the simulation progresses, individuals transition between states according to probabilistic rules (see {numref}`fig_project_epidemic`).

```{figure} sample_epidemic.png
---
width: 800px
name: fig_project_epidemic
---
Simulation results for the spread of the infection in a population. The colour of each cell represents its state of infection. Reprinted from {cite}`ghosh2021computational`.
```