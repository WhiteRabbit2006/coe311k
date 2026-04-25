# COE 311K Final Project: Comprehensive Summary

This document provides a comprehensive breakdown of all requirements across the three parts of the final project.

## General Requirements (Applies to All Parts)
- **Due Date:** April 30, 2026.
- **Submissions:** Jupyter Notebooks (`.ipynb`) to GitHub, and printed PDFs to Canvas.
- **Naming:** `LastName_FirstName_COE311K_FinalProject.pdf` (Part 1), `...Part2.pdf`, `...Part3.pdf`.
- **Format:** Notebooks must mix markdown text, well-commented modular Python code, and plots. Code must run perfectly from top to bottom.
- **Plots:** Must include descriptive titles, labeled axes with units, legends, and readable font sizes.
- **Team:** Can be done individually (+3 bonus points) or in a group (only one submission needed, list names in header).

---

## Part 1: Numerical Solution of Second-Order ODEs (35 Points)

**Goal:** Model a real-world second-order ODE, convert it to a first-order system, and solve using explicit methods.
**Length:** 5-7 pages printed (~2 pages markdown, ~1-2 pages code, ~2-3 pages plots with 4-6 key figures).

### Core Tasks:
1. **Model Selection:** Choose ONE real-world application (A: Spring-Mass, B: RLC Circuit, C: Damped Mechanical, D: Population Dynamics).
2. **Parameter Research:** Find realistic parameter values, cite sources, and justify initial conditions.
3. **Numerical Implementation:**
   - Convert the 2nd-order ODE to a system of two 1st-order ODEs.
   - Implement **Euler's Forward** and **RK4** in separate, modular functions.
   - Test with at least 3 different step sizes.
4. **Stability Analysis:**
   - Investigate accuracy vs. step size.
   - Identify maximum stable step sizes.
   - Quantify error (log-log plot of error vs step size to verify convergence rates: O(h) for Euler, O(h^4) for RK4).
   - Provide physical interpretation of instabilities (e.g., energy growth).

### Notebook Structure:
1. Introduction & Model Selection (~0.5 pages)
2. Parameter Research & Justification (~0.5 pages)
3. Numerical Methods Implementation (~0.25 pages + code)
4. Solutions & Comparison (~0.5 pages + plots)
5. Stability Analysis (~0.5 pages + plots)
6. Conclusions (~0.25 pages)

---

## Part 2: Stiff ODEs and Implicit Methods (40 Points)

**Goal:** Solve a stiff ODE using Euler's Backward method, utilizing Newton-Raphson to handle the implicit step.
**Length:** 6-8 pages printed (~2.5-3 pages text, ~1.5-2 pages code, ~2-3 pages plots with 5-7 key figures).

### Core Tasks:
1. **Stiff Scalar ODE Selection:** Choose ONE stiff scalar problem (A: RC Circuit, B: Chemical Reaction, C: Cooling, D: Mechanical System, E: Population). All are in the form $dy/dt = -\lambda y + g(t)$.
2. **Demonstrating Stiffness:**
   - Attempt Euler's Forward with a reasonable step size and show it fails/requires tiny steps.
   - Calculate the stiffness ratio (fastest to slowest timescales).
3. **Euler's Backward with Newton-Raphson:**
   - Derive the residual function $g(y_{n+1})$ and its derivative $g'(y_{n+1})$.
   - Implement a Newton-Raphson solver (initial guess = explicit Euler, track iterations).
   - Implement Euler's Backward utilizing the NR solver.
4. **Analysis & Comparison:**
   - Compare stable step sizes between Forward and Backward Euler.
   - Analyze accuracy vs computational cost (NR iterations per step, total function evaluations).
   - Plot Newton-Raphson iterations vs time.

### Notebook Structure:
1. Introduction & System Selection (~0.5 pages)
2. Demonstration of Stiffness (~0.5 pages + plots)
3. Mathematical Setup (~0.5 pages)
4. Implementation (~0.25 pages + code)
5. Results & Analysis (~0.75 pages + plots)
6. Performance Analysis (~0.5 pages + table/plots)
7. Conclusions (~0.25 pages)

---

## Part 3: Damping and Adaptive Step Sizes (25 Points)

**Goal:** Enhance the Part 2 implicit solver with damped Newton-Raphson and adaptive step-size control.
**Length:** 6-8 pages printed (~2.5 pages text, ~2 pages code, ~2.5 pages plots with 6-8 figures).

### Core Tasks:
1. **Newton-Raphson Damping:**
   - Implement line search (backtracking) to choose a damping factor $\alpha$.
   - Track backtracking steps and $\alpha$ values.
   - Demonstrate a scenario where basic NR fails but Damped NR succeeds.
2. **Adaptive Step Size Control:**
   - Implement Step-Doubling error estimation (take one step $h$, and two half-steps $h/2$).
   - Implement Accept/Reject logic based on a target tolerance.
   - Automatically adjust the next step size using $h_{new} = h \cdot \sqrt{tol / err} \cdot safety$.
   - Track $h$ used, accepted/rejected steps, and total NR iterations.
3. **Performance & Robustness Testing:**
   - Compare fixed vs adaptive stepping (same accuracy -> compare steps; same steps -> compare accuracy).
   - Test robustness with large initial $h$ or tight tolerances.

### Notebook Structure:
1. Review of Part 2 (~0.25 pages)
2. Newton-Raphson Damping Implementation (~0.5 pages + code)
3. Adaptive Step Size Implementation (~0.75 pages + code)
4. Performance Analysis (~0.75 pages + plots)
5. Robustness Testing (~0.5 pages + results)
6. Conclusions (~0.25 pages)

### Optional Bonus (+10 points max):
- PI Controller for step size (+5 pts)
- Embedded RK2 Method instead of step-doubling (+5 pts)
- Work-Precision Diagram log-log plot (+5 pts)
