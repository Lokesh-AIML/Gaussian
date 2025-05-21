# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

### Step 1: Import the numpy module to use the built-in functions for calculation.
### Step 2: Import the sys module to use the built-in functions.
### Step 3: Get input from the user for number of rows and add 1 to get the number of columns.
### Step 4: Use np.zeros() to initialize the matrix as a null matrix.
### Step 5: Use nested for loops to get input from the user for each element of the matrix.
### Step 6: Use nested for loops to find the ratio and perform elementary row operations to form an upper triangular matrix.
### Step 7: Use the back substitution method to find the values of the variables and print them.
### Step 8: End the program.

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

![image](https://github.com/user-attachments/assets/342fc036-3615-485b-967e-45da8b15434a)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

