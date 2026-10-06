# UGV Dynamic Obstacle Navigation using A* Search

## 1. Project Title

**UGV Navigation in Dynamic Obstacle Environment using A* Search**

---

## 2. Problem Statement

An Unmanned Ground Vehicle (UGV) is required to navigate through a grid-based battlefield environment from a user-specified start node to a user-specified goal node.

In a real-world battlefield, some obstacles may be dynamic and may not be known in advance. The UGV must detect these obstacles while moving, update its environment map, and find a new optimal path to reach the goal while avoiding collisions.

The objective is to design an intelligent navigation algorithm that allows the UGV to successfully navigate in a dynamic obstacle environment.

---

## 3. Objective

The main objectives of this project are:

* To navigate the UGV from a start node to a goal node.
* To use the **A* search algorithm** for path planning.
* To handle obstacles that appear dynamically during navigation.
* To detect newly appearing obstacles.
* To update the grid environment.
* To perform replanning when the current path is blocked.
* To avoid collisions with obstacles.
* To reach the destination using a short and safe path.
* To evaluate the navigation using Measures of Effectiveness (MOE).

---

## 4. Algorithm Used

### A* Search Algorithm

A* is an informed search algorithm used to find the shortest path between a start node and a goal node.

The evaluation function used by A* is:

**f(n) = g(n) + h(n)**

Where:

* **g(n)** = actual cost from the start node to the current node.
* **h(n)** = estimated cost from the current node to the goal.
* **f(n)** = total estimated cost of the path.

For this project, the **Manhattan distance** is used as the heuristic:

**h(n) = |xₙ − xg| + |yₙ − yg|**

A* selects the node having the lowest estimated total cost and continues until the goal is reached.

---

## 5. Dynamic Obstacle Navigation

Unlike static environments, dynamic obstacles can appear while the UGV is moving.

The navigation process is:

1. Generate the initial grid environment.
2. Define the start and goal positions.
3. Generate known static obstacles.
4. Use A* to calculate the initial path.
5. Start UGV movement.
6. Detect a newly appearing dynamic obstacle.
7. Add the obstacle to the environment map.
8. Check whether the current path is affected.
9. Run A* again to find a new path.
10. Continue navigation using the updated path.
11. Repeat the process whenever a new dynamic obstacle is detected.
12. Stop when the UGV reaches the goal.

### Flow

**Start → Generate Environment → A* Path Planning → UGV Movement → Detect Dynamic Obstacle → Update Map → Re-plan using A* → Continue Movement → Goal**

---

## 6. Environment

The environment is represented as a **30 × 30 grid**.

* `0` represents a free cell.
* `1` represents an obstacle.
* The UGV can move up, down, left, or right.
* The start position is `(0, 0)`.
* The goal position is `(29, 29)`.

The initial environment contains known static obstacles.

During navigation, additional obstacles are introduced dynamically to simulate a real-world environment.

---

## 7. Dynamic Obstacle Handling

The program introduces dynamic obstacles while the UGV is travelling.

A dynamic obstacle is placed on the UGV's actual current path. When the obstacle is detected:

* The obstacle is added to the grid.
* A* is executed again.
* A new safe path is calculated.
* The UGV follows the new path.
* The process continues until the goal is reached.

The program successfully demonstrated **6 dynamic obstacles and 6 replanning operations**.

---

## 8. Measures of Effectiveness (MOE)

The following measures are used to evaluate the UGV navigation:

### 1. Path Distance

The total number of grid cells travelled by the UGV.

### 2. Nodes Expanded

The number of nodes examined by the A* algorithm while searching for paths.

### 3. Number of Dynamic Obstacles

The total number of dynamically detected obstacles during navigation.

### 4. Number of Re-plans

The number of times A* had to calculate a new path because of dynamic obstacles.

### 5. Execution Time

The time required by the program to complete the navigation.

### 6. Success Rate

The percentage indicating whether the UGV successfully reached the goal.

---

## 9. Experimental Result

The program was executed with:

**Start Position:** `(0, 0)`

**Goal Position:** `(29, 29)`

The following results were obtained:

| Parameter          |         Result |
| ------------------ | -------------: |
| Path Distance      |  62 grid cells |
| Nodes Expanded     |         32,533 |
| Dynamic Obstacles  |              6 |
| Number of Re-plans |              6 |
| Execution Time     | 0.0971 seconds |
| Success Rate       |           100% |
| Navigation Status  |        SUCCESS |

---

## 10. Dynamic Obstacles Detected

The following dynamic obstacles were detected during the experiment:

```text
(0, 11)
(1, 17)
(2, 23)
(3, 29)
(10, 29)
(15, 29)
```

For every detected dynamic obstacle, the UGV updated its environment and performed A* replanning.

---

## 11. Result Analysis

The UGV successfully navigated from the start position `(0, 0)` to the goal position `(29, 29)`.

The initial A* path had a distance of 58 grid cells. Due to the appearance of dynamic obstacles, the UGV had to change its route. Therefore, the final travelled distance increased to **62 grid cells**.

Six dynamic obstacles were detected, and the algorithm performed six replanning operations. Despite these changes in the environment, the UGV successfully reached the destination.

The obtained success rate was **100%**, showing that the proposed approach can handle dynamic obstacles effectively.

---

## 12. Advantages

* Finds a short path using A* search.
* Can handle dynamic obstacles.
* Performs automatic path replanning.
* Avoids known obstacles.
* Updates the environment when new obstacles are detected.
* Successfully reaches the destination.
* Provides useful performance measures.
* Can be extended to larger grid environments.

---

## 13. Limitations

* The current simulation uses a grid-based environment.
* The movement is limited to four directions.
* Dynamic obstacle movement is simulated rather than obtained from real sensors.
* The current environment is smaller than a real battlefield.
* Real UGVs require sensors such as LiDAR, cameras, radar, or ultrasonic sensors.

---

## 14. Future Scope

The project can be extended by:

* Using real-time sensor data.
* Using LiDAR or camera-based obstacle detection.
* Allowing diagonal movement.
* Using real geographical maps.
* Implementing real-time robotics simulation.
* Using algorithms such as D* or D* Lite for dynamic environments.
* Adding multiple UGVs.
* Considering energy consumption and battery level.
* Using a larger battlefield environment such as a 70 × 70 grid.

---

## 15. Technologies Used

* **Python**
* **Google Colab**
* **A* Search Algorithm**
* **Heap Queue (`heapq`)**
* **Matplotlib**
* **Grid-based path planning**

---

## 16. Conclusion

The project successfully demonstrates UGV navigation in a dynamic obstacle environment using the A* search algorithm.

The UGV initially calculates an optimal path to the goal. When a dynamic obstacle appears on its path, the environment is updated and A* is used to calculate a new safe path. This process is repeated whenever required.

In the experiment, the UGV detected **6 dynamic obstacles**, performed **6 replanning operations**, travelled **62 grid cells**, and successfully reached the goal with a **100% success rate**.

Therefore, the proposed A*-based dynamic replanning approach provides an effective method for autonomous UGV navigation in environments containing dynamic obstacles.
