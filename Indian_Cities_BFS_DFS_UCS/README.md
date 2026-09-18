# Indian Cities Route Planning Agent using BFS, DFS and UCS

## About the Project

This project implements a Route Planning Agent for Indian cities using three uninformed search algorithms: Breadth-First Search (BFS), Depth-First Search (DFS), and Uniform Cost Search (UCS).

The Indian cities are represented as a graph, where cities are nodes and roads connecting the cities are edges. Each road has an associated distance in kilometres.

The project demonstrates how different search algorithms can be used to find a route from a starting city to a destination city.

## Aim

To implement and compare BFS, DFS, and UCS search algorithms for route planning between Indian cities.

## Algorithms Used

### 1. Breadth-First Search (BFS)

BFS explores the graph level by level. It finds a route based on the number of steps between the starting city and destination.

### 2. Depth-First Search (DFS)

DFS explores one path deeply before backtracking and exploring another path.

### 3. Uniform Cost Search (UCS)

UCS considers the cumulative distance of the roads and searches for the route with the minimum total cost.

## Indian City Graph

The project uses the following Indian cities:

- Hyderabad
- Bengaluru
- Chennai
- Nagpur
- Bhopal
- Mumbai
- Ahmedabad
- Jaipur
- Delhi
- Kolkata

The starting city is:

**Hyderabad**

The destination city is:

**Delhi**

## Results

### BFS

Route obtained:

**Hyderabad → Nagpur → Delhi**

Number of steps:

**2**

### DFS

Route obtained:

**Hyderabad → Bengaluru → Chennai → Mumbai → Nagpur → Bhopal → Jaipur → Ahmedabad → Delhi**

Number of steps:

**8**

### UCS

Route obtained:

**Hyderabad → Nagpur → Delhi**

Total distance:

**1580 km**

## Visualization

The project includes a graph visualization showing the Indian cities, their connections, and the distances between connected cities.

## Technologies Used

- Python
- Google Colab
- NetworkX
- Matplotlib
- Collections
- Heapq

## Conclusion

The Route Planning Agent was successfully implemented using BFS, DFS, and UCS. The experiment demonstrates how different search algorithms explore a city graph and how UCS uses road distances to determine a minimum-cost route.

## How to Run

1. Open the notebook in Google Colab.
2. Run the cells in order.
3. Enter or modify the starting and destination cities if required.
4. Run the BFS, DFS, and UCS implementations.
5. View the routes and graph visualization.

## Project Structure

```text
Indian_Cities_BFS_DFS_UCS/
│
├── Indian_Cities_BFS_DFS_UCS.ipynb
└── README.md
