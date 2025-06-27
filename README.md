# SoC_2025
Optimization with LP solvers<br>



In week 1 and 2, I gained the knowlegde to mathematically formulate linear programming problems by going through IE501 notes, also I learned theory regarding convex optimization.<br>
In week 3, I learned how to use solvers like Gurobi and PuLP to solve problems like LP, MILP, Integer programming.<br>
Link to gurobi tutorial "http://localhost:8888/lab/tree/Gurobi_tutorial.ipynb"<br>
In week 4, I completed assignment problems.<br>



## Assignment Problems

### 🔶 Problem 1: Nurse Scheduling with Preferences and Limits

You must assign nurses to shifts over a week.

- **Data**:
    - 7 days, 3 shifts/day (morning, afternoon, night)
    - 6 nurses
    - Each nurse can work at most 5 shifts a week and no more than one per day
    - No night shift followed by a morning shift the next day
    - Each shift must be covered by exactly one nurse
    - Nurses have preferences (0–10 score) for each shift
- **Objective**: Maximize total preference score across the week.

---

### 🔶 Problem 2: Production with Setup Times and Costs

A factory produces 4 products over 5 time periods.

- **Data**:
    - Each product requires different machine time and raw materials
    - Each switch to a new product has a fixed setup cost
    - Daily capacity for time and raw material
    - Storage cost for leftover products
    - Product demands per period
- **Objective**: Minimize total production + setup + storage costs.

---

### 🔶 Problem 3: Advertisement Budget Allocation (Piecewise Linear Approx.)

A company wants to allocate a monthly ad budget across 4 channels: social media, TV, newspaper, and online banners.

- **Data**:
    - Total budget = ₹1,00,000
    - Each channel has diminishing returns (e.g., modeled with piecewise linear utility functions)
    - Minimum and maximum spend per channel
    - TV must get at least 30% if chosen at all
    - At most 3 out of 4 channels can be active
- **Objective**: Maximize total reach.

