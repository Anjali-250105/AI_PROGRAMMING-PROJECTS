# Uniform Cost Search on an Indian Road Map

## 1. Project Title

**Uniform Cost Search (UCS) for Finding the Shortest Route in an Indian Road Map**

## 2. Introduction

This project implements the **Uniform Cost Search (UCS)** algorithm in Python to find the minimum-cost route between two cities in an Indian road network.

The road network is represented using a **weighted graph**, where:

* Cities are represented as nodes.
* Roads between cities are represented as edges.
* The distance between cities is represented as the edge cost in kilometres.

The program uses a **priority queue** to always explore the path with the lowest total distance first.

## 3. Objective

The main objective of this project is to:

* Implement Uniform Cost Search using Python.
* Represent an Indian road network using a weighted graph.
* Find the minimum-distance route between a source city and a destination city.
* Calculate and display the total distance of the selected route.

## 4. Algorithm Used

### Uniform Cost Search (UCS)

Uniform Cost Search is an uninformed search algorithm that expands the node with the **lowest path cost** first.

A priority queue is used to store:

```text
(total cost, current city, path)
```

The algorithm continues exploring the graph until the destination city is reached with the minimum possible cost.

## 5. Technologies Used

* **Programming Language:** Python
* **Environment:** Google Colab
* **Library Used:** `heapq`
* **Algorithm:** Uniform Cost Search

## 6. Graph Representation

The Indian road map is represented using a Python dictionary.

Example:

```python
"Hyderabad": [
    ("Nagpur", 500),
    ("Bengaluru", 570),
    ("Pune", 560)
]
```

Here:

* Hyderabad → Nagpur = 500 km
* Hyderabad → Bengaluru = 570 km
* Hyderabad → Pune = 560 km

The complete graph contains the following cities:

* Hyderabad
* Nagpur
* Bengaluru
* Pune
* Bhopal
* Indore
* Mumbai
* Ahmedabad
* Jaipur
* Delhi

## 7. Source and Destination

**Starting City:** Hyderabad

**Goal City:** Delhi

The UCS algorithm searches for the route having the minimum total distance.

## 8. Working of the Program

The program works as follows:

1. The starting city, Hyderabad, is inserted into the priority queue with cost `0`.
2. The city with the lowest accumulated cost is removed from the priority queue.
3. Its neighbouring cities are explored.
4. The distance to each neighbouring city is added to the current path cost.
5. The new path and its total cost are inserted into the priority queue.
6. A `visited_cost` dictionary keeps track of the lowest cost found for each city.
7. Cities that have already been reached with a lower or equal cost are skipped.
8. When Delhi is reached, the path and its total distance are returned.

## 9. Code

The implementation is provided in the Google Colab notebook:

**`UCS_Indian_Road_Map.ipynb`**

The program uses Python's `heapq` module to implement the priority queue required by Uniform Cost Search.

## 10. Expected Output

For the given graph, the program finds the minimum-cost route from Hyderabad to Delhi.

```text
Route: Hyderabad -> Nagpur -> Bhopal -> Delhi
Total distance: 1630 km
```

### Distance Calculation

```text
Hyderabad → Nagpur = 500 km
Nagpur → Bhopal = 350 km
Bhopal → Delhi = 780 km

Total = 500 + 350 + 780
      = 1630 km
```

Therefore, the minimum-distance route found by UCS is:

**Hyderabad → Nagpur → Bhopal → Delhi**

with a total distance of **1630 km**.

## 11. Time and Space Complexity

For a graph with vertices `V` and edges `E`, the complexity depends on the priority queue implementation.

Using a binary heap, UCS has approximately:

**Time Complexity:** `O((V + E) log V)`

**Space Complexity:** `O(V + E)`

The actual performance depends on the structure and size of the graph.

## 12. Advantages of Uniform Cost Search

* Finds the minimum-cost path when edge costs are non-negative.
* Works well for weighted graphs.
* Uses the actual path cost rather than the number of edges.
* Can find optimal routes in road-network problems.

## 13. Conclusion

This project demonstrates the implementation of **Uniform Cost Search** using Python on a weighted Indian road network.

The algorithm successfully determines the minimum-distance route from **Hyderabad to Delhi** by expanding the city with the lowest accumulated path cost first.

The final route obtained is:

**Hyderabad → Nagpur → Bhopal → Delhi**

with a total distance of **1630 km**.
