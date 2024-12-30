# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1.Input and Initialization:

2.Take the size of the system 
𝑛
n.

3.Initialize an augmented matrix 
𝑎
a of size 
𝑛
×
(
𝑛
+
1
)
n×(n+1) and a solution vector 
𝑥
x of size 
𝑛
n.

4.Input Matrix Coefficients:

5.Fill the augmented matrix 
𝑎
a with the coefficients of the equations and the constants.

6.Forward Elimination:

7.For each row 
𝑖
i from 0 to 
𝑛
−
1
n−1:

8.Check for a zero diagonal element; if found, exit with an error.
For each row 
𝑗
>
𝑖
j>i:

9.Compute the ratio 
ratio
=
𝑎
[
𝑗
]
[
𝑖
]
/
𝑎
[
𝑖
]
[
𝑖
]
ratio=a[j][i]/a[i][i].

10.Update each element of row 
𝑗
j:
𝑎
[
𝑗
]
[
𝑘
]
=
𝑎
[
𝑗
]
[
𝑘
]
−

11.ratio
×
𝑎
[
𝑖
]
[
𝑘
]
a[j][k]=a[j][k]−ratio×a[i][k], for 
𝑘
k from 0 to 
𝑛
n.

12.Backward Substitution:

13.Solve for 
𝑥
[
𝑛
−
1
]
x[n−1]: 
𝑥
[
𝑛
−
1
]
=
𝑎
[
𝑛
−
1
]
[
𝑛
]
/
𝑎
[
𝑛
−
1
]
[
𝑛
−
1
]
x[n−1]=a[n−1][n]/a[n−1][n−1].

14.For each row 
𝑖
i from 
𝑛
−
2
n−2 to 0:
Set 
𝑥
[
𝑖
]
=
𝑎
[
𝑖
]
[
𝑛
]
x[i]=a[i][n].

15.Subtract the contributions of known 
𝑥
[
𝑗
]
x[j] values for 
𝑗
>
𝑖
j>i:
𝑥
[
𝑖
]
−
=
𝑎
[
𝑖
]
[
𝑗
]
×
𝑥
[
𝑗
]
x[i]−=a[i][j]×x[j].

16.Divide by 
𝑎
[
𝑖
]
[
𝑖
]
a[i][i] to isolate 
𝑥
[
𝑖
]
x[i].

17.Output the Solution:

18.Print the values of 
𝑥
[
𝑖
]
x[i] for 
𝑖
=
0
i=0 to 
𝑛
−
1
n−1. 

## Program:
```
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range (n+1):
        matrix[i][j]=int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by:duraiarasan
RegisterNumber:24901028 
*/
```

## Output:
![gaussian elimination]()
![image 1](<Screenshot 2024-12-04 215603.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

