# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1:  
Import the required libraries `numpy` and `sys`.  

### Step 2:  
Input the size of the matrix `n` and define augmented matrix `a` as a NumPy array of size `(n, n+1)`. Initialize the solution array `x` as a NumPy array of size `n`.  

### Step 3:  
Perform forward elimination to transform the augmented matrix into an upper triangular form:  
- For each pivot row, ensure the pivot element is non-zero.  
- Subtract multiples of the pivot row from the rows below to eliminate the elements below the pivot.

### Step 4:  
Perform backward substitution to compute the solution:  
- Start with the last variable and substitute back into the equations to find the remaining variables.

### Step 5:  
Display the solution values of all variables using formatted output.

### Step 6:  
Verify the results for correctness.

## Program:
```python
Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: kishore kavin s
RegisterNumber: 212224230132

import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
        
for i in range (n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1,n):
        ratio =a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
            
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    
    x[i] = x[i]/a[i][i]
    
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
    
```

## Output:

![437951283-2adfea22-ab3c-4412-8df3-2b446afeb00c](https://github.com/user-attachments/assets/2106947d-8059-49cc-bef9-536d6560b3bd)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

