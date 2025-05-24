# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

### Step 1: Start the process and input the number of variables n.

### Step 2: Create an augmented matrix a[n][n+1] and a solution array x[n].

### Step 3: Input all elements of the augmented matrix a from the user.

### Step 4: For each row i from 0 to n-1, check if the pivot element a[i][i] == 0.
If true, print an error and stop (to avoid division by zero).

### Step 5: For each row j from i+1 to n-1, compute the ratio:
ratio = a[j][i] / a[i][i].

### Step 6: For each column k from i to n, update the matrix element:
a[j][k] = a[j][k] - ratio * a[i][k].

### Step 7: After forward elimination is complete, begin back substitution starting from the last row i = n-1 to 0.

### Step 8: Set x[i] = a[i][n] (the constant term of the current equation).

### Step 9: For each column j from i+1 to n-1, update:
x[i] = x[i] - a[i][j] * x[j].

### Step 10: Divide to get the final value:
x[i] = x[i] / a[i][i].

### Step 11: Print all values in the solution array x.

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

