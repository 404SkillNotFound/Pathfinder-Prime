Pathfinder-Prime: Autonomous Delivery Agent
Pathfinder-Prime is a project for CSA2001 - Fundamentals of AI and ML. It features an autonomous agent that navigates a 2D grid-based city to deliver packages efficiently. The agent is designed to handle static environments with varying terrain costs as well as dynamic environments with moving obstacles, using a range of search and replanning algorithms.

Features
Complex Environment Modeling: Simulates a 2D city grid with:

Static obstacles (e.g., buildings).

Varying terrain costs (e.g., roads vs. rough terrain).

Dynamic obstacles with predictable or unpredictable movement.

Pathfinding Algorithms: Implements several classic AI search algorithms to find the optimal path.

Uninformed Search: Breadth-First Search (BFS), Uniform-Cost Search (UCS).

Informed Search: A* Search with an admissible heuristic (Manhattan distance).

Dynamic Replanning: Utilizes a local search strategy to adapt to unexpected changes in the environment, such as new obstacles appearing on the planned route.

Performance Analysis: The agent's performance is benchmarked across different algorithms and maps based on path cost, nodes expanded, and execution time.

Getting Started
Follow these instructions to get the project running on your local machine.

Prerequisites
Python 3.8 or newer

Git

Installation
Clone the repository:

git clone [https://github.com/404SkillNotFound/Pathfinder-Prime.git](https://github.com/404SkillNotFound/Pathfinder-Prime.git)
cd Pathfinder-Prime

Install dependencies:
It is recommended to use a virtual environment.

# Create and activate a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

# Install the required packages
pip install -r requirements.txt

Usage
The main entry point for the simulation is main.py. You can run different pathfinding algorithms on various maps using command-line arguments.

Command Structure:

python main.py --map <path_to_map_file> --algorithm <algorithm_name>

Arguments:

--map: The file path to the grid map. (e.g., maps/small.txt)

--algorithm: The search algorithm to use. Options are bfs, ucs, astar.

Examples:

*Run A on the medium map:**

python main.py --map maps/medium.txt --algorithm astar

Run BFS on the small map:

python main.py --map maps/small.txt --algorithm bfs

Run Dynamic Replanning Demo:
To run the proof-of-concept for dynamic replanning, use the dynamic map. The agent will initially plan a path, and the simulation will introduce an obstacle, forcing the agent to replan.

python main.py --map maps/dynamic.txt --algorithm astar

The console output will log when the obstacle appears and the agent initiates its replanning logic.

Map File Format
The grid maps are represented as .txt files where each character is a cell in the grid:

S: Starting position of the agent.

G: Goal/delivery destination.

#: An impassable static obstacle (wall).

.: Normal terrain with a movement cost of 1.

*: Difficult terrain (e.g., gravel) with a movement cost of 3.

@: Water terrain with a movement cost of 5.

D: A dynamic obstacle.

Project Structure
Pathfinder-Prime/
├── maps/                # Contains map files (.txt) for testing
│   ├── small.txt
│   ├── medium.txt
│   └── ...
├── pathfinder/          # Core source code for algorithms and environment
│   ├── __init__.py
│   └── algorithms.py
├── .gitignore
├── main.py              # Main script to run the simulations via CLI
├── README.md            # This file
├── report.pdf           # Project report
└── requirements.txt     # Python dependencies
