# Delivery Route Optimization

An Algorithm Design and Analysis (ADA) capstone project that models a realistic last-mile delivery system with constraints on parcel weight, delivery time windows, and route efficiency.

## Project Snapshot

- Author: Satyam Singh
- Course: Algorithm Design and Analysis (ADA)
- Main artifact: Jupyter notebook implementation
- Focus area: Multi-constraint delivery optimization

## Objective

Modern delivery operations must balance speed, feasibility, and profit. This project demonstrates how different algorithmic paradigms can be combined into a practical decision pipeline:

1. Select high-value parcels under vehicle capacity.
2. Validate schedule feasibility using delivery windows.
3. Compute efficient network travel paths.
4. Estimate globally optimal route order.

## Problem Model

- Nodes: 8 total locations (1 warehouse + 7 delivery sectors)
- Parcels: 7 parcels, each with value, weight, and time window
- Vehicle constraints:
	- Maximum load: 15 kg
	- Average speed: 30 km/h
	- Shift start: 9:00 AM

## Algorithms Implemented

| Module | Technique | Complexity | What it Solves |
|---|---|---|---|
| Recursive Route Cost | Divide and Conquer | O(n!) | Demonstrates recursive route-cost formulation |
| Parcel Selection | Greedy | O(n log n) | Chooses parcels by value-to-weight efficiency |
| Time Window Feasibility | Dynamic Programming | O(n) | Verifies schedule feasibility |
| Shortest Paths | Dijkstra | O((V+E) log V) | Computes minimum distances from warehouse |
| Coverage Network | Prim's MST | O(E log V) | Builds minimum spanning coverage structure |
| Route Optimization | Held-Karp (Bitmask DP) | O(n^2 * 2^n) | Finds exact TSP route for small instance sizes |

## Repository Layout

```text
ada_capstoneproject-main/
|- delivery_route_optimization.ipynb
|- requirements (1).txt
|- README.md
```

## Setup and Execution

### 1) Clone and move into project

```bash
git clone https://github.com/<your-username>/delivery-route-mini-project-Arpita.git
cd delivery-route-mini-project-Arpita
```

### 2) Create and activate virtual environment

Windows (PowerShell):

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

Linux/macOS:

```bash
python -m venv venv
source venv/bin/activate
```

### 3) Install dependencies

```bash
pip install -r "requirements (1).txt"
```

### 4) Start Jupyter and run notebook

```bash
jupyter lab
```

Open `delivery_route_optimization.ipynb` and run all cells in order.

## Expected Outputs

- Parcel set selected under 15 kg constraint
- Total value of selected parcels
- Time-window feasibility status
- Dijkstra shortest-path distances from depot
- Prim MST total network cost
- Held-Karp optimal route summary for given nodes

## Key Takeaways

- Greedy methods are fast and practical for parcel preselection.
- DP adds critical feasibility checks for delivery windows.
- Graph algorithms support robust network-level planning.
- Exact TSP (Held-Karp) is suitable for small node counts but scales exponentially.

## Limitations and Extensions

Current scope is single-vehicle and static road costs. Natural next improvements include:

- Multi-vehicle Vehicle Routing Problem (VRP)
- Traffic-aware or time-dependent edge weights
- Fuel and emissions-aware optimization objective
- Approximation/metaheuristic methods for larger route sets

## References

- Cormen, Leiserson, Rivest, Stein. Introduction to Algorithms (CLRS)
- MIT OpenCourseWare notes on TSP and NP-hard optimization
- NetworkX Documentation: https://networkx.org
- GeeksforGeeks algorithm implementation guides
