---
sidebar_position: 1
---

# Gauss-Jordan Elimination

Suppose an augmented matrix is in row-echelon form. Is there a an algorithm to get its **reduced** row-echelon form?

What is [reduced row-echelon](../lecture-2/5.reduced-row-echelon-form.md) form?

1. All pivots must be 1
2. For each pivot column, except the pivot point, all other entries are 0

## Algorithm

Use elementary row operations to reduce a matrix to reduced row-echelon form.

1. Use Gaussian Elimination to get a row-echelon form
2. For each non-zero row, multiply a suitable constant so that the pivot point becomes 1.
3. Begin with the last non-zero, work backwards.
   1. Add a suitable multiple of each row to the rows above to introduce $0$ above the pivot points.

## Additional Notes

- Every matrix has a unique redued row-echelon form
- Every non-zero matrix has infinitely many (non-reduced) row-echelon forms.

## Example

$\begin{pmatrix}\begin{array}{ccccc|c}
    1 & 2 & 4 & 5 & 3 & -9\\
    0 & 0 & 2 & 4 & 2 & 8\\
    0 & 0 & 0 & 0 & 6 & -24
\end{array}\end{pmatrix}$

- All pivot points must be 1
  - Multiply $\frac{1}{2}$ to 2nd row, multiply $\frac{1}{6}$ to 3rd row
  - $\begin{pmatrix}\begin{array}{ccccc|c}
    1 & 2 & 4 & 5 & 3 & -9\\
    0 & 0 & 1 & 2 & 1 & 4\\
    0 & 0 & 0 & 0 & 1 & -4
    \end{array}\end{pmatrix}$
- For each pivot column, except the pivot point, all other entries are 0
  - To make the computation easier, we start from the last row.
    1. Add ($-3$) times 3rd row to 1st row, and add ($-1$) times 3rd row to 2nd row.
       - $\begin{pmatrix}\begin{array}{ccccc|c}
            1 & 2 & 4 & 5 & 0 & 3\\
            0 & 0 & 1 & 2 & 0 & 8\\
            0 & 0 & 0 & 0 & 1 & -4
            \end{array}\end{pmatrix}$
    2. Add ($-4$) times 2nd row to 1st row
       - $\begin{pmatrix}\begin{array}{ccccc|c}
         1 & 2 & 0 & -3 & 0 & -29\\
         0 & 0 & 1 & 2 & 0 & 8\\
         0 & 0 & 0 & 0 & 1 & -4
         \end{array}\end{pmatrix}$