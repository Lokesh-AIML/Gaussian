# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1: Import numpy and sys, and create the augmented matrix using np.zeros() and input() for user data.
### Step 2: Use np.linalg.LU() (or similar built-in LU decomposition) to decompose the augmented matrix into P, L, and U.
### Step 3: Solve for the solution vector using back substitution with built-in np.linalg.solve() or equivalent.
### step 4: Print the solution vector using formatted output with print() and the end the program.

## Program:
```python
#Program to find the solution of a matrix using Gaussian Elimination.
#Developed by: Kamlesh.Y
#RegisterNumber: 212224100029
import numpy as np
import sys

n = int(input())
a = np.zeros((n, n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n + 1):
        a[i][j] = float(input())

for i in range(n):
    if a[i][i] == 0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i + 1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n + 1):
            a[j][k] = a[j][k] - ratio * a[i][k]

x[n-1] = a[n-1][n] / a[n-1][n-1]

for i in range(n-2, -1, -1):
    x[i] = a[i][n]
    for j in range(i+1, n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i] / a[i][i]

for i in range(n):
    print('%d = %.2f' % (i, x[i]), end=" ")

```

## Output:

![image](https://github.com/user-attachments/assets/7271f373-45ec-4d1f-9b79-de645525bd2b)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

