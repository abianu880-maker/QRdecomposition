# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```


import numpy as np
def qr_decomposition(A):
    m,n=A.shape
    Q=np.zeros((m, n))
    R=np.zeros((n, n))
    for j in range(n):
        v=A[:, j]
        for i in range(j):
            R[i,j] = np.dot(Q[:, i],A[:, j])
            v=v-R[i,j] * Q[:, i]
        R[j,j] = np.linalg.norm(v)
        Q[:,j] = v/R[j,j]
    return Q,R
A=np.array(eval(input()))
Q,R=qr_decomposition(A)

print("The Q Matrix is \n",Q)
print("The R Matrix is \n",R)




```

## Output

<img width="1217" height="505" alt="Screenshot 2025-12-17 110916" src="https://github.com/user-attachments/assets/ff3dfc37-6794-4ef1-9111-70c12135db23" />
<img width="1196" height="591" alt="Screenshot 2025-12-17 111050" src="https://github.com/user-attachments/assets/d98f38d3-130b-47c1-8bc1-f3fc92709c31" />



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
