# sys_id_bilinear

Updated on June 2026.

Code and figures for bilinear system identification.

This repository reproduces numerical experiments comparing the set-membership estimator (SME) and ordinary least squares (OLS) for identifying bilinear dynamical systems.

## Model

We consider the discrete-time bilinear system

```math
x_{t+1} = A x_t + \sum_{i=1}^4 u_{t,i} B_i x_t + w_t .
```

In this experiment, the linear transition matrix is

```math
A =
\begin{bmatrix}
1.0000 & 0 & 0 & 0 & 0 \\
0 & -0.4604 & 0 & 0 & 0 \\
0 & 0 & -0.9181 & 0 & 0 \\
0 & 0 & 0 & -0.9669 & 0 \\
0 & 0 & 0 & 0 & 0.6265
\end{bmatrix}.
```

The bilinear matrices are

```math
B_1 =
\begin{bmatrix}
0 & 0 & 0 & 0 & 0 \\
-0.6233 & 0 & 0 & 0 & 0 \\
-0.7323 & -0.5443 & 0 & 0 & 0 \\
-0.1285 & 1.3665 & -0.6652 & 0 & 0 \\
0.0940 & -0.7435 & -0.9217 & -0.4577 & 0
\end{bmatrix},
```

```math
B_2 =
\begin{bmatrix}
0 & 0 & 0 & 0 & 0 \\
0.3554 & 0 & 0 & 0 & 0 \\
-1.2591 & 1.5139 & 0 & 0 & 0 \\
-0.3139 & 1.4580 & 1.9603 & 0 & 0 \\
0.3574 & -1.2083 & -0.0045 & 0.6565 & 0
\end{bmatrix},
```

```math
B_3 =
\begin{bmatrix}
0 & 0 & 0 & 0 & 0 \\
-0.4364 & 0 & 0 & 0 & 0 \\
-0.2586 & 1.5835 & 0 & 0 & 0 \\
0.0520 & 0.6837 & 1.0040 & 0 & 0 \\
-1.3204 & -0.6615 & 0.9350 & 0.0491 & 0
\end{bmatrix},
```

```math
B_4 =
\begin{bmatrix}
0 & 0 & 0 & 0 & 0 \\
0.6304 & 0 & 0 & 0 & 0 \\
-0.2874 & 1.5744 & 0 & 0 & 0 \\
1.0315 & 0.1610 & -0.5855 & 0 & 0 \\
0.5027 & 0.9897 & -0.1643 & -1.0744 & 0
\end{bmatrix}.
```

Here, `A` is diagonal and each `B_i` is strictly lower triangular. The true parameter matrix is packed as

```math
\Theta^\star = [A, B_1, B_2, B_3, B_4].
```

## Files

* `bilinear_sys_id.ipynb`: main notebook for generating the system, simulating trajectories, computing SME and OLS confidence diameters, and plotting the results.

## Requirements

```text
numpy
scipy
matplotlib
```

## Running

Open and run:

```text
bilinear_sys_id.ipynb
```
