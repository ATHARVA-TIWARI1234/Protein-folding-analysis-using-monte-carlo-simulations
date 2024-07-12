Monte Carlo Simulation of Protein Folding
Overview
This project involves the implementation of Monte Carlo simulations to study the folding dynamics of proteins on both 2D and 3D lattices. The simulations aim to understand energy transitions and structural behaviors, focusing on the influence of interaction energy distributions and temperature-dependent changes.

Objectives
Simulate protein folding transitions in two and three dimensions.
Analyze the impact of interaction energy distributions on equilibrium states and metastability.
Investigate the temperature-dependent changes in protein size using statistical metrics.
Methodology
Protein Model
2D and 3D Lattice Representation: Proteins are represented on a simple cubic lattice with each amino acid occupying a lattice site.
Interaction Energies: The interaction energies $J_{i, j}$ between non-covalently bonded amino acids are represented in a $20 \times 20$ matrix, randomly varying within a specific range to mimic real biological interactions.
Simulation Process
Initial State: Define a primary structure by randomly selecting $N$ integers from 1 to 20, representing the amino acids.
Monte Carlo Steps:
Select a random amino acid chain link.
Generate a new state by moving the selected amino acid to a neighboring lattice site, ensuring no covalent bond is broken.
Calculate the energy of the new state.
Accept the move if it lowers the energy; otherwise, accept it with a probability determined by the Boltzmann factor.
Metrics
Total Energy: Calculated as
𝐸
=
∑
<
𝑚
,
𝑛
>
𝛿
𝑚
,
𝑛
𝐽
𝐴
(
𝑚
)
,
𝐴
(
𝑛
)
E= 
<m,n>
∑
​
 δ 
m,n
​
 J 
A(m),A(n)
​
 

where $\delta_{m, n}=1$ for non-covalently bonded nearest neighbors.
Mean-Square Size:
Δ
≡
⟨
∣
𝑟
⃗
𝑖
−
𝑟
⃗
𝑐
𝑚
∣
2
⟩
Δ≡⟨∣ 
r
  
i
​
 − 
r
  
cm
​
 ∣ 
2
 ⟩

where $\vec{r}i$ is the position of the $i$-th amino acid and $\vec{r}{cm}$ is the center of mass.
End-to-End Distance: Distance between the first and last amino acid in the chain.
Results
The simulation reveals that proteins tend to stay in a highly folded and stable state at low temperatures.
A phase transition in energy and end-to-end distance is observed as temperature changes, independent of the number of amino acids.
At high temperatures, energy and end-to-end distance approach the results of a self-avoiding random walk system, indicating dominance of thermal fluctuations.
Code Implementation
Requirements
Python 3.x
Numba
NumPy
