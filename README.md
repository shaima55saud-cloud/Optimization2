# Metaheuristic Optimization Project (CS467)

## Project Description
This project aims to solve the **Traveling Salesman Problem (TSP)** using two metaheuristic optimization algorithms:

- Simulated Annealing (SA)
- Genetic Algorithm (GA)

The main goal is to compare the performance of both algorithms in terms of:
- Solution quality (tour distance)
- Convergence behavior
- Execution time

A standard benchmark dataset is used, and each algorithm is executed using predefined stopping conditions to ensure a fair and consistent comparison.

---

## Problem Overview: Traveling Salesman Problem (TSP)
The Traveling Salesman Problem is a classic optimization problem.  
Given a set of cities and the distances between them, the objective is to find the **shortest possible tour** that:

- Visits each city exactly once
- Returns to the starting city

TSP is classified as an **NP-hard problem**, meaning that finding the exact optimal solution becomes very difficult as the number of cities increases. Therefore, metaheuristic algorithms are commonly used to find good approximate solutions within reasonable time.

# A. Requirements & Installation

This project was developed and executed entirely using **Google Colab**, so no local installation is required.

The following Python libraries are used:
- numpy
- matplotlib
- random
- math
- tsplib95

The `tsplib95` library is used to load and read TSP datasets in TSPLIB format.

No additional setup, package installation, or environment configuration is needed beyond what Google Colab provides by default.

## Dataset
This project uses a benchmark dataset from **TSPLIB**, which is a well-known library of standard test problems for the Traveling Salesman Problem (TSP).

The dataset represents a set of cities along with the distances between each pair of cities. It is provided in the `.tsp` format, which is commonly used in academic research for evaluating and comparing optimization algorithms.

Using a standard dataset helps ensure that the comparison between Simulated Annealing and Genetic Algorithm is fair and consistent.

Example dataset used in this project:
- `berlin52.tsp`

## Algorithms Used

### Simulated Annealing (SA)
Simulated Annealing is a **single-solution optimization algorithm** inspired by the physical process of annealing metals.

How it works:
- Starts with a random initial tour
- Generates a neighboring solution by modifying the current tour
- Accepts better solutions always
- May accept worse solutions with a probability depending on the current temperature
- Gradually reduces the temperature using a cooling schedule

**Advantages:**
- Simple to implement
- Fast execution
- Able to escape local minima
### Genetic Algorithm (GA)
The Genetic Algorithm is a **population-based optimization algorithm** inspired by natural evolution.

How it works:
- Each solution represents a TSP tour (permutation of cities)
- A population of solutions evolves over generations
- Better solutions are selected to produce new ones

**Main components:**
- Representation: permutation of cities
- Fitness function: based on tour distance
- Selection method: Tournament Selection
- Crossover: Order-1 Crossover
- Mutation: swap-based mutation
- Replacement strategy:
  - Starts with generational replacement
  - Switches to steady-state replacement when no improvement is observed

Tournament Selection is chosen because it is simple, efficient, and reduces premature convergence.

## Stopping Conditions
Each algorithm is executed using predefined stopping conditions to ensure fair comparison.

The execution stops when one of the following conditions is met:
- A maximum number of iterations or generations is reached
- No significant improvement is observed for a predefined number of iterations

## Project Structure
├── Simulated_Annealing.ipynb
├── GA.ipynb
├── README.md
└── dataset/
    └── berlin52.tsp

## How to Run
1. Open the desired notebook in Google Colab:
   - `Simulated_Annealing.ipynb` or
   - `GA with conv graph.ipynb`
2. Upload the dataset file (e.g., `berlin52.tsp`) if required.
3. Run all cells using **Runtime → Run all**.
4. The results and convergence graphs will be displayed automatically.

## Results
The performance of Simulated Annealing and Genetic Algorithm is evaluated based on:
- Best tour distance
- Convergence behavior
- Execution time

In general, Genetic Algorithm achieves better solution quality due to population diversity, while Simulated Annealing provides faster execution with simpler configuration.

## Notes
- Due to the stochastic nature of both algorithms, results may vary between runs.
- Multiple executions are recommended for more reliable comparison.
- Parameter tuning has a strong impact on performance.



