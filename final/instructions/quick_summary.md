# COE 311K Final Project: Quick Summary

The final project is a progressive three-part assignment where you will build a production-quality Ordinary Differential Equation (ODE) solver. 

## The Three Parts and How They Relate

*   **Part 1: Non-Stiff ODEs (35 Points).** You will model a real-world second-order ODE, convert it into a system of first-order ODEs, and solve it using explicit methods (Euler's Forward and RK4). You will analyze stability limits and errors.
*   **Part 2: Stiff ODEs (40 Points).** You will tackle "stiff" systems where explicit methods fail or become impractically slow. You will implement an implicit method (Euler's Backward) solved via Newton-Raphson iteration.
*   **Part 3: Robust & Efficient Solvers (25 Points).** You will enhance your Part 2 solver to make it robust and efficient. You will add Newton-Raphson Damping (to prevent divergence) and Adaptive Step Size Control (to automatically adjust step sizes based on error).

**Relationship:** The project builds sequentially. Part 1 introduces explicit numerical methods and basic stability analysis. Part 2 pivots to implicit methods required for stiff equations. Part 3 optimizes the implicit solver from Part 2 into a robust, professional-grade tool.

## What You Need to Deliver

*   **Due Date:** All parts are due April 30, 2026.
*   **Formats:** For each part, you need to write a well-documented Jupyter Notebook (`.ipynb`). 
*   **Submission:** 
    *   **Canvas:** Submit a printed PDF version of each completed Jupyter Notebook.
    *   **GitHub:** Submit the `.ipynb` files.
*   **Naming Convention:** `LastName_FirstName_COE311K_Part[1/2/3].pdf` (and `.ipynb`).
*   **Group Work:** This can be an individual or group project. Individual submissions receive 3 bonus points. If submitting as a group, only one submission is needed, but all members must be listed in the notebook header.
