# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input matrix dimensions and initialize augmented matrix and solution vector.
2. Perform Gaussian elimination to reduce the matrix to upper triangular form, ensuring no division by zero.
3. Back substitute to compute solution values for the variables.
4. Print the solution vector formatted to two decimal places.

## Program:
```
/*
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Lohith v
RegisterNumber: 212225230154
'''
import os 
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][j]==0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
*/
```

## Output:
<img width="1221" height="768" alt="Screenshot 2026-05-20 103319" src="https://github.com/user-attachments/assets/524e2be0-729d-401c-9238-2f85f64ea83e" />
<img width="1227" height="525" alt="Screenshot 2026-05-20 103341" src="https://github.com/user-attachments/assets/0037f2fc-829c-42f9-83c0-dc078fc0bf68" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

