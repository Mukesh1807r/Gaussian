# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Read the order of the matrix n.

Read the augmented matrix of size n × (n+1).

Perform Forward Elimination:

For each pivot row i from 0 to n-1:

For each row j below pivot (i+1 to n-1):

Compute ratio:

𝑟
𝑎
𝑡
𝑖
𝑜
=
𝐴
[
𝑗
]
[
𝑖
]
𝐴
[
𝑖
]
[
𝑖
]
ratio=
A[i][i]
A[j][i]
	​


Update row elements:

𝐴
[
𝑗
]
[
𝑘
]
=
𝐴
[
𝑗
]
[
𝑘
]
−
𝑟
𝑎
𝑡
𝑖
𝑜
×
𝐴
[
𝑖
]
[
𝑘
]
A[j][k]=A[j][k]−ratio×A[i][k]

Perform Back Substitution:

Initialize solution array X.

Start from last row and compute:

𝑋
[
𝑖
]
=
𝐴
[
𝑖
]
[
𝑛
]
−
∑
𝐴
[
𝑖
]
[
𝑗
]
𝑋
[
𝑗
]
𝐴
[
𝑖
]
[
𝑖
]
X[i]=
A[i][i]
A[i][n]−∑A[i][j]X[j]
	​


Display the solution values.

## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Mukesh R
RegisterNumber: 212224240098
'''

import numpy as np

n = int(input())

values = []
for _ in range(n * (n + 1)):
    values.append(float(input()))

A = np.array(values).reshape(n, n + 1)

for i in range(n):
    for j in range(i + 1, n):
        ratio = A[j][i] / A[i][i]
        for k in range(n + 1):
            A[j][k] = A[j][k] - ratio * A[i][k]

X = np.zeros(n)

for i in range(n - 1, -1, -1):
    X[i] = A[i][n]
    for j in range(i + 1, n):
        X[i] -= A[i][j] * X[j]
    X[i] = X[i] / A[i][i]

for i in range(n):
    print(f"X{i} = {X[i]:.2f}", end=" ")
```

## Output:
<img width="760" height="375" alt="image" src="https://github.com/user-attachments/assets/327f19b2-7a32-4a5d-ad00-a907ad8f606a" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

