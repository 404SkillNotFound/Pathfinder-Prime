Pathfinder-Prime: Autonomous Delivery Agent



Pathfinder-Prime is a project for CSA2001 - Fundamentals of AI and ML. It features an autonomous agent that navigates a 2D grid-based city to deliver packages efficiently. The agent is designed to handle static environments with varying terrain costs as well as dynamic environments with moving obstacles, using a range of search and replanning algorithms.


<h1 align="center">


  Pathfinder-Prime 🤖📍


</h1>




Features


Complex Environment Modeling: Simulates a 2D city grid with:


<p align="center">


  An autonomous delivery agent for CSA2001 that navigates complex 2D grid environments using AI search algorithms.


</p>




Static obstacles (e.g., buildings).


<p align="center">


  <img src="https://img.shields.io/badge/Python-3.8+-blue.svg" alt="Python Version">

  <img src="https://img.shields.io/badge/Project%20Status-Complete-brightgreen" alt="Project Status">


</p>




Varying terrain costs (e.g., roads vs. rough terrain).


---




Dynamic obstacles with predictable or unpredictable movement.


**Pathfinder-Prime** features an autonomous agent designed to efficiently navigate a 2D grid-based city. The agent can handle static environments with varying terrain costs as well as dynamic environments with moving obstacles, using a range of search and replanning algorithms.




Pathfinding Algorithms: Implements several classic AI search algorithms to find the optimal path.


## 🎯 Key Features




Uninformed Search: Breadth-First Search (BFS), Uniform-Cost Search (UCS).


-   **Complex Environment Modeling:** Simulates a 2D city grid with:


    -   Static obstacles (e.g., buildings).


    -   Varying terrain costs (e.g., roads vs. rough terrain).


    -   Dynamic obstacles with predictable or unpredictable movement.


-   **Advanced Pathfinding:** Implements several classic AI search algorithms to find the optimal path.


    -   **Uninformed Search:** Breadth-First Search (BFS), Uniform-Cost Search (UCS).


    -   **Informed Search:** A* Search with an admissible heuristic (Manhattan distance).


-   **Dynamic Replanning:** Utilizes a local search strategy to adapt to unexpected changes in the environment, such as new obstacles appearing on the planned route.


-   **Performance Analysis:** Benchmarks algorithm performance across different maps based on path cost, nodes expanded, and execution time.




Informed Search: A* Search with an admissible heuristic (Manhattan distance).


---




Dynamic Replanning: Utilizes a local search strategy to adapt to unexpected changes in the environment, such as new obstacles appearing on the planned route.


## 🚀 Getting Started




Performance Analysis: The agent's performance is benchmarked across different algorithms and maps based on path cost, nodes expanded, and execution time.





Getting Started

Follow these instructions to get the project running on your local machine.




Prerequisites


Python 3.8 or newer





Git

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


### Prerequisites




Arguments:


-   Python 3.8 or newer


-   Git




--map: The file path to the grid map. (e.g., maps/small.txt)


### Installation




--algorithm: The search algorithm to use. Options are bfs, ucs, astar.


1.  **Clone the repository:**


    ```bash


    git clone [https://github.com/404SkillNotFound/Pathfinder-Prime.git](https://github.com/404SkillNotFound/Pathfinder-Prime.git)


    cd Pathfinder-Prime


    ```




Examples:


2.  **Install dependencies:**


    > **Note:** It is highly recommended to use a Python virtual environment to avoid conflicts with other projects.




*Run A on the medium map:**


    ```bash


    # Create and activate a virtual environment


    python -m venv venv


    source venv/bin/activate  # On Windows, use: venv\Scripts\activate




python main.py --map maps/medium.txt --algorithm astar


    # Install the required packages


    pip install -r requirements.txt


    ```




Run BFS on the small map:


---




python main.py --map maps/small.txt --algorithm bfs


## ⚙️ Usage




Run Dynamic Replanning Demo:


To run the proof-of-concept for dynamic replanning, use the dynamic map. The agent will initially plan a path, and the simulation will introduce an obstacle, forcing the agent to replan.


The main entry point for the simulation is `main.py`. You can run different algorithms on various maps using command-line arguments.




python main.py --map maps/dynamic.txt --algorithm astar


#### Command Structure:




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





```bash


python main.py --map <path_to_map_file> --algorithm <algorithm_name>
