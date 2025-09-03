# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.First,we want to import numpy,then import sys,assume a variable.

2.For gaussian elimination method, we want to make 2nd and 3rd column zero.

3.For that we want to make a range accorting to our program output.

4.Then print the program with correct form then the output will display. 


## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Deepak S
RegisterNumber: 212224230053
'''
import numpy as np
import sys

n = int(input())

a = np.zeros((n, n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

# Forward elimination
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit("Divide by zero detected!")

    for j in range(i+1, n):
        ratio = a[j][i] / a[i][i]
        a[j, i:] = a[j, i:] - ratio * a[i, i:]

# Back substitution
x[n-1] = a[n-1][n] / a[n-1][n-1]

for i in range(n-2, -1, -1):
    x[i] = a[i][n] - np.dot(a[i, i+1:n], x[i+1:n])
    x[i] /= a[i][i]

for i in range(n):
    print(f"X{i} = {x[i]:.2f}",end=" ")
```

## Output:
<img width="1333" height="932" alt="image" src="https://github.com/user-attachments/assets/33d4e2b6-da74-43f4-ad9f-cf84787eec1c" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

