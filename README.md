# Timetabling Scheduling Problem Using Quantum Optimization

This repository presents a quantum computing approach to solving the university timetabling problem. The project formulates the scheduling task as a Quadratic Unconstrained Binary Optimization (QUBO) problem and uses quantum optimization techniques to generate feasible, conflict free timetables. 
It aims to explore whether quantum computing can offer practical advantages over traditional classical methods for constrained scheduling.


## Overview

University timetabling is a complex combinatorial optimization problem involving the assignment of courses to time slots, rooms, and instructors without conflicts. 
The objective is to find a schedule that satisfies all hard constraints (such as avoiding double-bookings) and optimizes soft preferences (such as minimizing instructor idle time or back-to-back classes).

In this project:

- The timetabling problem is modeled using a QUBO formulation.
- Constraints are encoded as binary penalty terms.
- Quantum solvers are used to solve the QUBO and return binary solutions.
- The results are decoded and analyzed in terms of feasibility and performance.

This notebook based solution evaluates the capability of current quantum systems to address practical optimization problems and 
compares results with classical scheduling logic.


## Problem Formulation

The core of the problem is represented in binary terms:

- Each course-time-room combination is encoded as a binary variable.
- Constraints (e.g., no overlapping classes, valid room capacities) are translated into a QUBO matrix.
- The optimization goal is to minimize the total penalty from violating constraints.

### Constraints Modeled

- A course must be assigned to exactly one time slot and one room.
- No two courses can occur in the same room at the same time.
- An instructor cannot be assigned to multiple courses simultaneously.
- Optional: minimize timetable gaps for teachers and room switching.


## Approach

1. **Data Preprocessing**: A sample dataset representing courses, rooms, time slots, and instructor assignments is used to build the problem space.
2. **QUBO Construction**: All constraints are converted into QUBO penalty terms.
3. **Quantum Optimization**: The QUBO is passed to a quantum solver (or simulator).
4. **Post-Processing**: The binary output is decoded into a readable timetable format.
5. **Validation**: The resulting schedule is checked for conflicts and evaluated against constraints.


## Technologies Used

- Python 3.x
- NumPy, Pandas, Qiskit Libraries
- Jupyter Notebook

## Future Work

- Integrate classical preprocessing to reduce QUBO size before quantum solving.
- Explore hybrid solvers that combine classical and quantum methods for better scalability.
- Implement auto-tuning of constraint weights using reinforcement learning.
- Extend support for more realistic scheduling constraints (e.g., preferred rooms, double lectures).
- Build an interactive interface for non-technical users to input constraints and generate schedules.



