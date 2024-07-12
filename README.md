# Monte Carlo Simulation of Protein Folding

## Overview

This project involves the implementation of Monte Carlo simulations to study the folding dynamics of proteins on both 2D and 3D lattices. The simulations aim to understand energy transitions and structural behaviors, focusing on the influence of interaction energy distributions and temperature-dependent changes.

## Objectives

- Simulate protein folding transitions in two and three dimensions.
- Analyze the impact of interaction energy distributions on equilibrium states and metastability.
- Investigate the temperature-dependent changes in protein size using statistical metrics.

## Methodology

### Protein Model

- **2D and 3D Lattice Representation**: Proteins are represented on a simple cubic lattice with each amino acid occupying a lattice site.
- **Interaction Energies**: The interaction energies $J_{i, j}$ between non-covalently bonded amino acids are represented in a $20 \times 20$ matrix, randomly varying within a specific range to mimic real biological interactions.

### Simulation Process

1. **Initial State**: Define a primary structure by randomly selecting $N$ integers from 1 to 20, representing the amino acids.
2. **Monte Carlo Steps**:
   - Select a random amino acid chain link.
   - Generate a new state by moving the selected amino acid to a neighboring lattice site, ensuring no covalent bond is broken.
   - Calculate the energy of the new state.
   - Accept the move if it lowers the energy; otherwise, accept it with a probability determined by the Boltzmann factor.

### Metrics

- **Total Energy**: Calculated as
  <p align="center"><img src="https://latex.codecogs.com/svg.latex?E=\sum_{\langle&space;m,&space;n&space;\rangle}&space;\delta_{m,&space;n}&space;J_{A(m),&space;A(n)}" /></p>
  where \(\delta_{m, n} = 1\) for non-covalently bonded nearest neighbors.

- **Mean-Square Size**: 
  <p align="center"><img src="https://latex.codecogs.com/svg.latex?\Delta&space;\equiv&space;\langle&space;\left|&space;\vec{r}_i&space;-&space;\vec{r}_{\text{cm}}&space;\right|^2&space;\rangle" /></p>
  where \(\vec{r}_i\) is the position of the \(i\)-th amino acid and \(\vec{r}_{\text{cm}}\) is the center of mass.

- **End-to-End Distance**: Distance between the first and last amino acid in the chain.




## Results

- The simulation reveals that proteins tend to stay in a highly folded and stable state at low temperatures.
- A phase transition in energy and end-to-end distance is observed as temperature changes, independent of the number of amino acids.
- At high temperatures, energy and end-to-end distance approach the results of a self-avoiding random walk system, indicating dominance of thermal fluctuations.

## Code Implementation

### Requirements

- Python 3.x
- Numba
- NumPy
