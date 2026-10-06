# UGV Battlefield Path Planning

A Python-based programming assignment that demonstrates shortest-path planning for an **Unmanned Ground Vehicle (UGV)** on a **70 × 70 km battlefield grid** using **Breadth-First Search (BFS)**.

## 📌 Project Overview

The battlefield is represented as a 70 × 70 grid where each cell represents a **1 × 1 km area**.

The program:

* Accepts start and goal coordinates from the user.
* Generates random obstacles.
* Tests three obstacle-density levels:

  * Low Density – 10%
  * Medium Density – 20%
  * High Density – 30%
* Uses **Breadth-First Search (BFS)** to find the shortest available path.
* Measures path distance, nodes explored, execution time, and success.
* Visualizes the battlefield, obstacles, start point, goal point, and UGV path using **Matplotlib**.

## 🎯 Objective

The main objective is to determine whether the UGV can reach the specified goal while avoiding obstacles and to evaluate the path-planning performance under different obstacle densities.

## 🗺️ Battlefield Representation

| Value | Meaning   |
| ----- | --------- |
| `0`   | Free cell |
| `1`   | Obstacle  |

* Grid size: **70 × 70**
* Coordinate range: **0–69** for X and Y
* Each cell represents **1 km × 1 km**
* Start and goal cells are kept free.

## 🚧 Obstacle Densities

The program evaluates the path planner using three different obstacle densities:

| Density | Obstacles |
| ------- | --------: |
| Low     |       10% |
| Medium  |       20% |
| High    |       30% |

Since obstacles are generated randomly, the exact results may vary each time the program is executed.

## 🔍 Algorithm Used – Breadth-First Search (BFS)

BFS explores the battlefield grid level by level.

The UGV can move in four directions:

* Up
* Down
* Left
* Right

Because every movement has the same cost of **1 km**, BFS can find the shortest path when a valid path exists.

### BFS Components

* **Queue** – stores cells waiting to be explored.
* **Visited Set** – prevents repeated exploration.
* **Parent Dictionary** – stores the previous cell and is used to reconstruct the path.

## 📊 Measures of Effectiveness

The following measures are calculated:

1. **Path Found** – Indicates whether the UGV can reach the goal.
2. **Shortest Distance** – Number of movements in the path, with each movement representing 1 km.
3. **Nodes Explored** – Number of grid nodes processed by BFS.
4. **Execution Time** – Time required to perform the search.
5. **Success** – `Yes` if a valid path is found; otherwise `No`.

## 📈 Visualization

The battlefield and calculated path are visualized using **Matplotlib**.

The visualization shows:

* Battlefield grid
* Obstacles
* UGV start position
* Goal position
* Calculated UGV path

A separate visualization is generated for each obstacle-density level.

## 🛠️ Technologies and Libraries

* **Python 3**
* **Jupyter Notebook**
* **Matplotlib**
* **random**
* **time**
* **heapq**

## 💻 Requirements

Install Python 3.x and Jupyter Notebook/JupyterLab.

Install Matplotlib using:

```bash
pip install matplotlib
```

## ▶️ How to Run

1. Clone or download this repository.
2. Open `UGV_Battlefield_Path_Planning.ipynb` in Jupyter Notebook or JupyterLab.
3. Run the notebook.
4. Enter the starting X and Y coordinates.
5. Enter the goal X and Y coordinates.
6. View the calculated path, performance measurements, and visualizations.

### Example Input

```text
Start X: 0
Start Y: 0
Goal X: 69
Goal Y: 69
```

## 🔄 Project Workflow

```text
User Input
     ↓
Validate Start and Goal Coordinates
     ↓
Generate Random Battlefield
     ↓
Apply Obstacle Density
     ↓
Run BFS
     ↓
Find Shortest Path
     ↓
Calculate Performance Measures
     ↓
Visualize Battlefield and Path
     ↓
Display Results
```

## 📁 Project Structure

```text
UGV-Battlefield-Path-Planning/
│
├── UGV_Battlefield_Path_Planning.ipynb
├── UGV_Battlefield_Path_Planning_Documentation.docx
└── README.md
```

## 📝 Expected Output

For each obstacle-density level, the program displays:

* Whether a path was found
* Shortest path distance
* Number of nodes explored
* Execution time
* Success status
* Battlefield visualization

## ⚠️ Note

The battlefield obstacles are generated randomly. Therefore, the path, distance, number of explored nodes, and execution time may be different each time the program is executed.

## ✅ Conclusion

This project demonstrates how **Breadth-First Search (BFS)** can be used for grid-based UGV path planning. By testing different obstacle densities, the project evaluates route availability, shortest-path distance, search effort, and execution time.

The visualization provides an intuitive representation of the battlefield and the route selected by the UGV.
