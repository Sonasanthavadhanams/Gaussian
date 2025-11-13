# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1.Form the augmented matrix 
<br>

Step 2.Use row operations to convert the augmented matrix into an upper triangular form — that is, make all elements below the main diagonal zero.

<br>

step 3.Once the matrix is in upper triangular form, start from the last equation and substitute backward to find the values of all unknowns.

<br>

step 4.Print or return the values of all variables as the final solution of the system.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: SONA.S
RegisterNumber:212224110049 
*/
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())

for i in range(n):
    if a[i][j]==0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
       ratio=a[j][i]/a[i][i]
       for k in range(n+1):
           a[j][k]=a[j][k]-ratio * a[i][k]

x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![gaussian elimination]()
<img width="1220" height="587" alt="image" src="https://github.com/user-attachments/assets/709b5fce-0838-4909-ba07-b69a40b4f474" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

