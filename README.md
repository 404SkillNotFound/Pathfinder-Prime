<h1 align="center">
  Pathfinder-Prime 🤖📍
</h1>

<p align="center">
  An autonomous delivery agent for CSA2001 that navigates complex 2D grid environments using AI search algorithms.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue.svg" alt="Python Version">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License">
  <img src="https://img.shields.io/badge/Project%20Status-Complete-brightgreen" alt="Project Status">
</p>

---

**Pathfinder-Prime** features an autonomous agent designed to efficiently navigate a 2D grid-based city. The agent can handle static environments with varying terrain costs as well as dynamic environments with moving obstacles, using a range of search and replanning algorithms.

## 🎯 Key Features

-   **Complex Environment Modeling:** Simulates a 2D city grid with:
    -   Static obstacles (e.g., buildings).
    -   Varying terrain costs (e.g., roads vs. rough terrain).
    -   Dynamic obstacles with predictable or unpredictable movement.
-   **Advanced Pathfinding:** Implements several classic AI search algorithms to find the optimal path.
    -   **Uninformed Search:** Breadth-First Search (BFS), Uniform-Cost Search (UCS).
    -   **Informed Search:** A* Search with an admissible heuristic (Manhattan distance).
-   **Dynamic Replanning:** Utilizes a local search strategy to adapt to unexpected changes in the environment, such as new obstacles appearing on the planned route.
-   **Performance Analysis:** Benchmarks algorithm performance across different maps based on path cost, nodes expanded, and execution time.

---

## 📂 Project Structure

```bash
Pathfinder-Prime/
├── maps/                # Contains map files (.txt) for testing
│   ├── small.txt
│   ├── medium.txt
│   ├── large.txt
│   └── dynamic.txt
├── pathfinder/          # Core source code for the project
│   ├── __init__.py      # Makes the 'pathfinder' directory a Python package
│   ├── agent.py         # Defines the agent and its pathfinding logic (BFS, A*, etc.)
│   └── environment.py   # Models the grid, obstacles, and terrain costs
├── tests/               # Contains unit tests for the project
│   └── test_astar.py    # Tests for the A* algorithm
├── .gitignore           # Specifies files for Git to ignore (e.g., __pycache__)
├── main.py              # Main script to run the simulations via CLI
├── README.md            # This file
├── report.pdf           # The detailed project report and analysis
└── requirements.txt     # Python dependencies for pip
