# MagicHexagon

## Overview

This repository presents an efficient solution to the Magic Hexagon problem, a well-known mathematical challenge. It contains the implementation developed during the "Efficient Programs" course at TU Vienna in 2023. For detailed information on the Magic Hexagon problem, refer to [Wikipedia](https://en.wikipedia.org/wiki/Magic_hexagon).

The implementation uses constraint logic programming principles, representing the numbers to be found and those given as variables (`Var` type). These variables have bounds (`lo` and `hi`) indicating the range of possible values. The solution employs a search tree to iteratively narrow down these bounds until a solution is found or deemed impossible.

## Key Concepts

### Variables and Constraints

- **Variables (`Var`):** Represent numbers with unknown values within specified bounds. The `occupation` array in the `solve()` function tracks assigned values, ensuring all variables have unique values.
- **All-different Constraint:** Ensures all variables obtain distinct values. This is implicitly managed through the `solve()` function.
- **Sum Constraints:** For all lines in the hexagon, the sum `v1 + ... + vn = M` must hold. Implemented in the `sum()` function and its calls within `solve()`.
- **Less-than Constraints:** Enforces that values at the hexagon's corners are in ascending order to eliminate symmetric solutions. Implemented in the `lessthan()` function.

### Functions

- **`labeling()`:** Explores the search tree by assigning a possible value to a variable and recursively searching for a solution. It aims to optimize search efficiency by selecting the most promising variable values first.
- **`solve()`:** The core function that applies constraints and searches for a solution. It incrementally tightens variable bounds and applies the `labeling()` function to explore all possible solutions.

## Optimizations

The implementation introduces several optimizations for performance improvement:

- **Spiral Field Exploration:** Prioritizes fields in a spiral pattern to efficiently narrow down the search space.
- **Value Range Bisection:** Splits the variable value range to expedite convergence towards a solution.
- **Guided Spiral Heuristic:** Enhances the spiral exploration with heuristics for faster solution identification.

## Reference Output

The reference output corresponds to benchmark problems and serves to verify the correctness of the implementation.

## Getting Started

To dive into the Magic Hexagon solution, examine the `header.html` file for an in-depth explanation of the task and approach. Additionally, the optimizations and their impact are detailed in the accompanying presentation.
