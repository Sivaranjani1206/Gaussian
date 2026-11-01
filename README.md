# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### 1. Import the numpy module to use the built-in functions for calculation
### 2. Prepare the lists from each linear equations and assign in np.array()
### 3.Using the np.zeros() and seprate them and use it in the for loops so we can find the solutions.
### 4. End the program

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: SIVARANJANI M
RegisterNumber: 212225220099
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
#Reading number of unknowns
n=int(input())
#Making numpy array of n x n+1 size and initializing 
#to zero for storing augmented matrix
a=np.zeros((n,n+1))
#Making numpy array of n size and initializing 
#to zero for storing solution vector
x=np.zeros(n)
#Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
#Applying Gauss Elimination 
for i in range(n):
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(i,n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
#Back substitution
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
#Displaying solution
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')

```

## Output:

<img width="1289" height="874" alt="Screenshot 2026-11-01 162209" src="https://github.com/user-attachments/assets/a1fff408-9601-4603-9741-8994487c1531" />
<img width="1286" height="880" alt="Screenshot 2026-11-01 162225" src="https://github.com/user-attachments/assets/e595d5d6-02c9-436f-867e-63cae8762555" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

