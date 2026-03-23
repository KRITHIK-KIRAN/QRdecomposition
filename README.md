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
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by:Krithik kiran S
RegisterNumber: 212225230145
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def QR_decompostion(A):
    n,m=A.shape
    Q,R=np.zeros((n,n)),np.zeros((n,m))
    for i in range(n):
        u=A[:,i]-sum((A[:,i]@Q[:,j])*Q[:,j] for j in range(i))
        Q[:,i]=u/np.linalg.norm(u)
        for j in range(i,n):
            R[i,j]=A[:,j]@Q[:,i]
    print("The Q Matrix is\n",Q)
    print("The R Matrix is\n",R)
a=np.array(eval(input())) 
QR_decompostion(a)
```

## Output

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5dfb011a-8f07-40b3-8308-42dc4a9c2751" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
