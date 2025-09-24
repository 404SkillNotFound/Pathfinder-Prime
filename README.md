# Pathfinder-Prime

**An Autonomous Delivery Agent for CSA2001 - Fundamentals of AI and ML**

Pathfinder-Prime is an advanced pathfinding system designed to navigate a 2D grid-based city environment for efficient package delivery. The system handles both static environments with varying terrain costs and dynamic environments with moving obstacles, demonstrating various AI search algorithms in real-world scenarios.

## Table of Contents
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Pathfinding Algorithms](#pathfinding-algorithms)
- [Map File Format](#map-file-format)
- [Installation](#installation)
- [Usage](#usage)
- [Dynamic Replanning](#dynamic-replanning)
- [Performance Analysis](#performance-analysis)

## Features

- **Environment Modeling**: 2D city grid with static obstacles, varying terrain costs, and dynamic obstacles
- **Multiple Pathfinding Algorithms**: BFS, UCS, and A* with Manhattan distance heuristic
- **Dynamic Replanning**: Local search strategy to adapt when new obstacles appear
- **Performance Analysis**: Benchmarks across different maps based on path cost, nodes expanded, and execution time
- **Visualization**: Visual representation of the path found by the agent

## Technologies Used

- **Language**: Python 3.8+
- **Dependencies**: matplotlib (for visualization)
- **Core Framework**: Custom pathfinding implementation

## Project Structure

```
Pathfinder-Prime/
├── maps/                 # Contains map file (.txt) for testing
│   ├── small.txt
│   ├── medium.txt
│   └── dynamic.txt
├── pathfinder/          # Core source code for algorithms and environment
│   ├── __init__.py
│   └── algorithms.py
├── tests/               # Test files
├── .gitignore
├── main.py              # Main script to run simulations via CLI
├── README.md            # Project documentation
├── report.pdf           # Project report
└── requirements.txt     # Python dependencies
```

## Pathfinding Algorithms

The project implements several classic AI search algorithms:

### Uninformed Search
- **Breadth-First Search (BFS)**: Explores all neighbors at the current depth before moving to nodes at the next depth level
- **Uniform-Cost Search (UCS)**: Expands the node with the lowest path cost, optimal for weighted graphs

### Informed Search
- **A* Search**: Uses Manhattan distance heuristic to guide the search toward the goal, balancing between UCS and greedy best-first search

### Dynamic Replanning
- **Local Search Strategy**: Adapts to unexpected environmental changes when new obstacles appear during navigation

## Map File Format

The grid maps use a text-based format where each character represents a cell:

- `S`: Starting position of agent
- `G`: Goal/destination
- `#`: Impassable static obstacle
- `.`: Normal terrain (cost: 1)
- `*`: Difficult terrain (cost: 3)
- `@`: Water terrain (cost: 5)
- `D`: Dynamic obstacle

## Installation

1. Clone the repository:
```bash
git clone https://github.com/404SkillNotFound/Pathfinder-Prime.git
```

2. Navigate to the project directory:
```bash
cd Pathfinder-Prime
```

3. Install the required dependencies:
```bash
pip install -r requirements.txt
```

## Usage

The main entry point is `main.py`, which runs simulations via command-line interface:

### Command Structure
```bash
python main.py --map <path_to_map_file> --algorithm <algorithm_name>
```

### Arguments
- `--map`: Path to the grid map file (e.g., `maps/medium.txt`)
- `--algorithm`: Search algorithm to use (`UCS`, `A*`, or `dynamic_demo`)

### Examples
```bash
# Run A* on medium map
python main.py --map maps/medium.txt --algorithm A*

# Run UCS on small map
python main.py --map maps/small.txt --algorithm UCS

# Run dynamic replanning demo
python main.py --map maps/dynamic.txt --algorithm dynamic_demo
```

## Dynamic Replanning

The dynamic replanning feature demonstrates how the agent can adapt when the environment changes during navigation:

1. Initially calculates a path using A*
2. Simulates the agent moving along the path
3. Introduces a dynamic obstacle on the planned path
4. Replans from the agent's current position using A*

This functionality is essential for real-world applications where obstacles may appear unexpectedly.

## Performance Analysis

The system provides performance metrics for each algorithm:
- Path cost: Total cost of the path found
- Nodes expanded: Number of nodes explored during search
- Execution time: Time taken to find the solution

These metrics allow for comparison between different pathfinding approaches and their effectiveness in various scenarios.

## Contributing

This project was developed for educational purposes in the CSA2001 - Fundamentals of AI and ML course. Contributions and improvements are welcome!

## License

This project is open source and available under the MIT License.
