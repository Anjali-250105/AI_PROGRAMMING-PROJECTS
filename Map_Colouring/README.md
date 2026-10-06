# Map Coloring Problem – Telangana Districts

## 1. Introduction

The **Map Coloring Problem** is a constraint satisfaction problem in which regions of a map must be assigned colors such that no two adjacent regions have the same color.

In this project, the Map Coloring Problem is implemented for the **33 districts of Telangana** using the **Backtracking algorithm**.

The actual Telangana district boundary map is obtained from a GeoJSON dataset, and the program automatically determines which districts are adjacent.

---

## 2. Objective

The objectives of this project are:

* To implement the Map Coloring Problem using Python.
* To use the actual map of Telangana.
* To consider all **33 districts** of Telangana.
* To automatically determine adjacent districts from their geographical boundaries.
* To assign colors so that adjacent districts have different colors.
* To display the final colored Telangana map.
* To verify that the coloring is valid.

---

## 3. Technologies Used

* **Python**
* **Google Colab**
* **GeoPandas**
* **Matplotlib**
* **Requests**
* **Backtracking Algorithm**
* **GeoJSON**

---

## 4. Input Data

The program automatically downloads the Telangana district boundary GeoJSON file.

The dataset contains:

* 33 Telangana districts
* District boundary geometries
* District names

The district name field used in the dataset is:

```text
D_NAME
```

The program does not require the user to manually upload the map file.

---

## 5. Algorithm

### Backtracking

Backtracking is used to find a valid color assignment.

The algorithm works as follows:

1. Select a district.
2. Try assigning one of the available colors.
3. Check whether the selected color conflicts with any neighboring district.
4. If there is no conflict, assign the color and move to the next district.
5. If a conflict occurs, try another color.
6. If no color is possible, backtrack to the previous district.
7. Continue until all 33 districts are colored.

The four colors used are:

* Red
* Green
* Blue
* Yellow

---

## 6. Adjacency Graph

The geographical boundaries of the districts are used to construct an adjacency graph.

Each district is represented as a **vertex**.

An edge is created between two vertices when the corresponding districts share a boundary.

For example:

```text
District A -------- District B
```

means District A and District B are adjacent and therefore must have different colors.

---

## 7. Implementation

The program performs the following steps:

```text
Download Telangana GeoJSON
          ↓
Load district boundaries
          ↓
Identify 33 districts
          ↓
Construct adjacency graph
          ↓
Apply Backtracking
          ↓
Assign colors
          ↓
Display actual Telangana map
          ↓
Verify the solution
```

---

## 8. Output

The program produces an **actual colored map of Telangana containing all 33 districts**.

Each district is displayed with its assigned color and district name.

The program also performs a verification step.

Expected verification output:

```text
Map coloring successful!
VALID SOLUTION
All adjacent districts have different colors.
```

---

## 9. Correctness

The solution is considered valid only when:

```text
Color(District A) != Color(District B)
```

for every pair of adjacent districts.

The program checks every adjacency relationship after coloring and reports whether any conflict exists.

---

## 10. Time Complexity

For `n` districts and `k` available colors, the worst-case time complexity of the backtracking algorithm is:

```text
O(k^n)
```

For this project:

```text
n = 33
k = 4
```

Therefore, the worst-case search space is:

```text
O(4^33)
```

However, backtracking eliminates invalid assignments as soon as conflicts are detected, so the practical execution is much smaller than the worst-case search space.

---

## 11. Space Complexity

The color assignment and recursion require:

```text
O(n)
```

additional space.

The adjacency graph requires additional space depending on the number of neighboring relationships between districts.

---

## 12. Advantages

* Uses the actual Telangana district map.
* Handles all 33 districts.
* Automatically determines district adjacency.
* Does not require manual entry of all neighboring districts.
* Uses a standard AI search technique, Backtracking.
* Displays the final result visually.
* Automatically verifies the coloring.

---

## 13. Conclusion

The **Map Coloring Problem for Telangana's 33 districts** was successfully implemented using the **Backtracking algorithm**.

The program automatically obtains the district boundaries, constructs the adjacency graph, assigns colors while satisfying the constraints, displays the actual colored Telangana map, and verifies that no two adjacent districts have the same color.

Thus, the project demonstrates the application of **Constraint Satisfaction and Backtracking Search** to a real-world geographical problem.
