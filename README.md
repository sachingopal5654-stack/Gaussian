# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the NumPy library to perform matrix operations and handle multidimensional arrays.
2. Get the coefficient matrix and constant matrix as input from the user and form the augmented matrix.
3. Apply Gaussian Elimination by performing elementary row operations to convert the augmented matrix into an upper triangular matrix.
4. Use the back substitution method to calculate the unknown variables and print the solution of the given system of linear equations.
## Program:

/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Sachin G
RegisterNumber: 26011448
*/
```
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"

import numpy as np
n= int(input())

a=np.zeros((n,n+1))

for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

for i in range(n):
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(i,n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
            
x = np.zeros(n)
x[n -1 ]=a[n-1][n]/a[n-1][n-1]

for i in range (n-2,-1,-1):
    x[i] =a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]

output =" ".join([f"X{i} = {x[i]:.2f}"for i in range(n)])
    
print(output)  
```

## Output:
<img width="1900" height="910" alt="Screenshot 2026-11-16 153108" src="https://github.com/user-attachments/assets/0c743b05-72ae-40ce-b76c-c145fd33abe6" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

