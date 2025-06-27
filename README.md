# SoC_2025
Optimization with LP solvers<br>



In week 1 and 2, I gained the knowlegde to mathematically formulate linear programming problems by going through IE501 notes, also I learned theory regarding convex optimization.<br>
In week 3, I learned how to use solvers like Gurobi and PuLP to solve problems like LP, MILP, Integer programming.<br>
Link to gurobi tutorial "http://localhost:8888/lab/tree/Gurobi_tutorial.ipynb"<br>
In week 4, I completed assignment problems.<br>


# SOC: Optimization with LP solvers

# Important links

GDrive Material link: https://drive.google.com/drive/folders/1RcEt3WW9UFROonDG9CepdkZy3A9m84J7?usp=sharing

# Week 0

<aside>
**📚 Core Concepts**

These are some introductory concepts about time series and Python. This week is optional, if you have prior knowledge of these topics you can start with week 1.

</aside>

## Study Material

- **1. Python Basics**
    
    <aside>
    **🎥 Video Watching Tip**
    
    Refrain from completing this material all at once. Instead, use it to gain a general understanding of the concepts. If you need more clarity on specific topics or encounter challenges, you can look them up online for deeper insights. This approach will help you learn more effectively and focus on what is most relevant to you.
    
    </aside>
    
    - https://www.geeksforgeeks.org/python-basics/ | Getting started with Python
    - https://youtu.be/QUT1VHiLmmI?si=NKYnQF0F-033z9dw | Tutorial for Numpy
    - https://youtu.be/nzKy9GY12yo?si=1QBjybLnk1vWve4l | Tutorial for Matplotlib
- **2. Pandas and Jupyter Notebook**
    
    <aside>
    **💡 Alternative Option**
    
    If you encounter issues with Jupyter Notebook, you can use [Google Colab](https://colab.research.google.com/) as an alternative. Google Colab provides a free, cloud-based Jupyter Notebook environment that requires no setup and allows you to work with Python and data science libraries directly in your browser. 
    
    </aside>
    
    - https://realpython.com/jupyter-notebook-introduction/ | Introduction to Jupyter Notebook
    - https://youtu.be/vmEHCJofslg?si=H1YG5WUGcIHV9vUE | Pandas Introduction
- **3. Numpy essentials**
    - https://www.youtube.com/watch?v=QUT1VHiLmmI

<aside>
**💡 Pro Tip**

As you review these materials, try to implement the concepts using the stock data you'll use for your project. This hands-on approach will help solidify your understanding and prepare you for the assignments ahead.

</aside>

# Week 1-2

<aside>
**📚 Introduction to Optimization Modeling**

This week will be a bit more on the theoretical side. Before we start coding, it's important to understand how to properly model optimization problems. A good model can make a huge difference in how efficiently a solver can handle it. For instance, many constraints can be written in different ways, sometimes even as quadratic ones, but finding a clean linear formulation is usually the best choice. That said, coming up with the right linear form isn’t always obvious, and that’s exactly what we’ll focus on this week: building the intuition and tools to model problems effectively.

</aside>

## *Study Material*

**1. IE501 notes:** https://drive.google.com/file/d/1bPQdTeWONETV57NSsBq_ObRAqiVPtvsR/view?usp=sharing | For this week, pages 2 to 8 are enough. (Feel free to go beyond if you're interested.)

**2. Detailed book on linear optimization:** https://www2.isye.gatech.edu/~nemirovs/WSPrintedNoSol.pdf | (Optional) If you want to practice or read more. 

# Week 3-4

<aside>
**📚 Introduction to Optimization Modeling**

This week, you’ll learn how to translate real-world scenarios into mathematical optimization problems using **Linear Programming (LP)**. They will be introduced to classic problem types such as **transportation**, **assignment**, and **scheduling**, and gain experience in formulating these problems with decision variables, objective functions, and constraints. The focus will be on **implementing and solving these models using Gurobi's Python API (`gurobipy`)**, with attention to both modelling correctness and computational efficiency. By the end of this module, students will be able to identify LP-suitable problems in real-world settings, structure them formally, and solve them programmatically.

</aside>

## Setup Instructions:

You will need to set up at least one of the solvers - the choice is entirely yours. One of the best industry-standard solvers is **Gurobi** (which is not free commercially, but you can get it for free with an academic license). If you prefer something simpler to set up, try **PuLP**. You're free to use any other solver as well, but we might not be able to assist with the modelling part since the mentors are only familiar with Gurobi and PuLP.

### Gurobi with Python (gurobipy)

### 1. **Get an Academic License**

- Visit Gurobi Academic Program
- Register using your academic email (e.g., `@iitb.ac.in`)
- Download the license key.

### 2. **Install gurobipy**

```bash
pip install gurobipy
```

### 3. **Activate Gurobi**

```bash
grbgetkey <your-license-key>
```

---

## 📘 Learning Resources: Modelling in gurobipy

### Tutorials & Docs

- [Gurobi Python Quick Start](https://support.gurobi.com/hc/en-us/articles/17278438215313-Tutorial-Getting-Started-with-the-Gurobi-Python-API)
- [Gurobipy basics on Google Colab](https://colab.research.google.com/github/Gurobi/modeling-examples/blob/master/intro_to_gurobipy/intro_to_gurobipy.ipynb)
- [Gurobipy example application for linear regression](https://github.com/Gurobi/modeling-examples/tree/master/linear_regression)

### PuLP with Python

### 1. **Install PuLP**

PuLP is a Python library for linear programming that works with many solvers (like CBC, GLPK, and even Gurobi).

```bash
pip install pulp
```

### 2. **(Optional) Install CBC Solver**

PuLP uses CBC (Coin-or branch and cut) as its default solver, which you may need to install separately depending on your OS.

- On Linux:
    
    ```bash
    sudo apt install coinor-cbc
    ```
    
- On Mac:
    
    ```bash
    brew install cbc
    ```
    
- On Windows: CBC usually installs automatically with PuLP. If not, DM me.

---

## 📘 Learning Resources: Modelling in PuLP

### Tutorials & Docs

- [PuLP Official Documentation](https://coin-or.github.io/pulp/)
- [PuLP Beginner's Guide](https://towardsdatascience.com/linear-programming-and-discrete-optimization-with-python-using-pulp-449f3c5f6e99/)
- [PuLP Examples](https://coin-or.github.io/pulp/CaseStudies/a_blending_problem.html)

---

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

