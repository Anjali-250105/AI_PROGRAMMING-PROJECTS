# Telangana Map Coloring Using AC-3

## Project Overview

This project implements **map coloring of the 33 districts of Telangana** using the **AC-3 (Arc Consistency 3) algorithm** and **Backtracking**.

The objective is to assign colors to all districts such that **no two neighboring districts have the same color**.

Four colors are used:

- Red
- Green
- Blue
- Yellow

## Problem Statement

Map coloring can be represented as a **Constraint Satisfaction Problem (CSP)**.

Each Telangana district is considered as a variable, and its neighboring districts form constraints. The constraint is:

> Adjacent districts must have different colors.

The project uses AC-3 to reduce the possible colors for each district and backtracking to find a complete valid assignment.

## Algorithms Used

### 1. AC-3 Algorithm

AC-3 maintains **arc consistency** between neighboring districts.

It checks whether every color in the domain of one district has at least one compatible color in the domain of its neighboring district.

If a color has no valid supporting color, it is removed from the domain.

### 2. Backtracking

After applying AC-3, backtracking is used to complete the coloring when multiple possible colors remain.

The algorithm:

1. Selects a district with the smallest remaining domain.
2. Tries one available color.
3. Applies AC-3 again.
4. Continues if the assignment is consistent.
5. Backtracks if a conflict occurs.

## Technologies Used

- **Python 3**
- `collections.deque`
- Constraint Satisfaction Problem (CSP)
- AC-3 algorithm
- Backtracking algorithm

## Input

The input consists of:

- 33 Telangana districts
- Neighbor relationships between districts
- Four available colors

The neighbor graph is also made symmetric so that if district A is a neighbor of district B, district B is also treated as a neighbor of district A.

## Output

The program produces a color assignment for all 33 districts.

### Final Color Assignment

| District | Color |
|---|---|
| Adilabad | Red |
| Bhadradri Kothagudem | Blue |
| Hanumakonda | Green |
| Hyderabad | Green |
| Jagtial | Green |
| Jangaon | Blue |
| Jayashankar Bhupalpally | Green |
| Jogulamba Gadwal | Green |
| Kamareddy | Green |
| Karimnagar | Red |
| Khammam | Red |
| Kumuram Bheem | Green |
| Mahabubabad | Yellow |
| Mahabubnagar | Green |
| Mancherial | Red |
| Medak | Red |
| Medchal-Malkajgiri | Red |
| Mulugu | Red |
| Nagarkurnool | Blue |
| Nalgonda | Red |
| Narayanpet | Blue |
| Nirmal | Blue |
| Nizamabad | Red |
| Peddapalli | Blue |
| Rajanna Sircilla | Blue |
| Rangareddy | Blue |
| Sangareddy | Green |
| Siddipet | Yellow |
| Suryapet | Green |
| Vikarabad | Red |
| Wanaparthy | Red |
| Warangal | Red |
| Yadadri Bhuvanagiri | Green |

## Constraint Verification

After generating the solution, the program checks every district against all of its neighboring districts.

The execution produced:

```text
Running AC-3...

TELANGANA MAP COLORING USING AC-3

...

Checking constraints...
All constraints satisfied!
```

Therefore, the generated coloring satisfies the constraints defined in the program.

## Main Functions

### `revise()`

Checks the domain of a district against the domain of its neighboring district and removes colors that cannot satisfy the constraint.

### `ac3()`

Maintains a queue of arcs and repeatedly applies the `revise()` function until the network becomes arc-consistent.

### `backtracking()`

Selects an unassigned district, tries possible colors, and uses AC-3 to check whether the assignment remains consistent.

## Execution Flow

```text
Define Telangana districts and neighbors
              ↓
Make neighbor graph symmetric
              ↓
Initialize 4-color domains
              ↓
Apply AC-3
              ↓
Domains become consistent
              ↓
Apply Backtracking if required
              ↓
Generate final coloring
              ↓
Check all constraints
              ↓
Display solution
```

## Conclusion

The project successfully demonstrates **map coloring as a Constraint Satisfaction Problem** using the **AC-3 algorithm with Backtracking**.

The final solution assigns one of four colors to each of the 33 Telangana districts, and the constraint-checking step confirms that **all defined neighboring-district constraints are satisfied**.
