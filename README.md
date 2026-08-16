# 2D Poisson Solver

Numerical solution of the 2D Laplace equation using iterative methods.

## About

This project solves the 2D Laplace equation on a square grid using
three iterative methods:

- Jacobi method
- Gauss-Seidel method
- Successive Over-Relaxation (SOR)

The potential is calculated for fixed boundary conditions and the
convergence of the three methods is compared.

## Setup

The calculation uses a 50 x 50 grid.

The boundary conditions are:

- V = 1 on the upper boundary
- V = 0 on the other three boundaries

The convergence tolerance is 10^-6.

For SOR, the relaxation parameter used is:

omega = 1.8

## Results

The calculated potential varies smoothly across the grid between the
specified boundary values.

The number of iterations required to reach the convergence criterion
was:

| Method | Iterations |
|---|---:|
| Jacobi | 3270 |
| Gauss-Seidel | 1793 |
| SOR | 233 |

SOR converges much faster than the Jacobi and Gauss-Seidel methods for
the parameters used here.

## Methods

For the Laplace equation,

∇²V = 0

the finite-difference equation used at an interior grid point is

V(i,j) = [V(i+1,j) + V(i-1,j) + V(i,j+1) + V(i,j-1)] / 4

The Jacobi method calculates the new grid from the previous iteration.

The Gauss-Seidel method uses updated values immediately during each
iteration.

The SOR method introduces a relaxation parameter to accelerate
convergence.

## Tools

- Python
- NumPy
- Matplotlib
- Jupyter Notebook

## File

`poisson_solver.ipynb` contains the complete calculation and plots.

## Future Work

- Solve the equation with a non-zero charge density.
- Study the effect of grid size on convergence.
- Study the dependence of SOR convergence on the relaxation parameter.
