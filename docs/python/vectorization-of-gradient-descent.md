# 梯度下降矢量化

> 原文:[https://www . geesforgeks . org/梯度下降矢量化/](https://www.geeksforgeeks.org/vectorization-of-gradient-descent/)

在机器学习中，**回归**问题可以通过以下方式解决:

1.使用**优化算法**–梯度下降

*   批量梯度下降。
*   随机梯度下降。
*   小批量梯度下降
*   其他高级优化算法，如(共轭下降…)

2.使用**法向方程**:

*   使用线性代数的概念。

让我们考虑一元线性回归问题的**批梯度下降的情况。**

这个回归问题的**成本函数**是:

<center>![J(\Theta)=(1/2m)*\sum_{i=1}^m(h_{\theta}(x^i)-y^i)^2      ](img/47f56304ecf5ffb23bce8b022d9fefe0.png "Rendered by QuickLaTeX.com")</center>

**目标:**

<center>![minimize_{\ \theta_{o},\theta_{1}}\ \ J({\theta})      ](img/4732092cee82eda11aba837bd8b7bd8f.png "Rendered by QuickLaTeX.com")</center>

为了解决这个问题，我们可以选择**矢量化方法**(使用线性代数的概念)或者**非矢量化方法**(使用 for 循环)。

### 1.非工厂化方法:

这里为了求解下面提到的数学表达式，我们使用**进行循环**。

```
The above mathematical expression is a part of Cost Function.

```

<center>![\sum_{i=1}^m(h_{\theta}(x^i)-y^i)^2      ](img/f38d37ba8a554b0c9f0016b68253c872.png "Rendered by QuickLaTeX.com")</center>

```
The above Mathematical Expression is the hypothesis.

```

<center>![h_{\theta}=\theta_{0}x_{0}+\theta_{1}x_{1}+\theta_{2}x_{2}+... +\theta_{n}x_{n}\\ where,\\ h_{\theta}=hypothesis.\\        ](img/531d623cf78ac43ca62add7abe55568f.png "Rendered by QuickLaTeX.com")</center>

**代码:非工厂化 Grad** 的 Python 实现

```
# Import required modules.
from sklearn.datasets import make_regression
import matplotlib.pyplot as plt
import numpy as np
import time

# Create and plot the data set.
x, y = make_regression(n_samples = 100, n_features = 1,
                       n_informative = 1, noise = 10, random_state = 42)

plt.scatter(x, y, c = 'red')
plt.xlabel('Feature')
plt.ylabel('Target_Variable')
plt.title('Training Data')
plt.show()

# Convert y from 1d to 2d array.
y = y.reshape(100, 1)

# Number of Iterations for Gradient Descent
num_iter = 1000

# Learning Rate
alpha = 0.01

# Number of Training samples.
m = len(x)

# Initializing Theta.
theta = np.zeros((2, 1),dtype = float)

# Variables
t0 = t1 = 0
Grad0 = Grad1 = 0

# Batch Gradient Descent.
start_time = time.time()

for i in range(num_iter):
    # To find Gradient 0.
    for j in range(m):
        Grad0 = Grad0 + (theta[0] + theta[1] * x[j]) - (y[j])

    # To find Gradient 1.
    for k in range(m):
        Grad1 = Grad1 + ((theta[0] + theta[1] * x[k]) - (y[k])) * x[k]
    t0 = theta[0] - (alpha * (1/m) * Grad0)
    t1 = theta[1] - (alpha * (1/m) * Grad1)
    theta[0] = t0
    theta[1] = t1
    Grad0 = Grad1 = 0

# Print the model parameters.    
print('model parameters:',theta,sep = '\n')

# Print Time Take for Gradient Descent to Run.
print('Time Taken For Gradient Descent in Sec:',time.time()- start_time)

# Prediction on the same training set.
h = []
for i in range(m):
    h.append(theta[0] + theta[1] * x[i])

# Plot the output.
plt.plot(x,h)
plt.scatter(x,y,c = 'red')
plt.xlabel('Feature')
plt.ylabel('Target_Variable')
plt.title('Output')
```

**输出:**

<center>
![](img/712c3306bb2b1dede7765eab84018f9a.png)
</center>

```
model parameters:
[[ 1.15857049]
 [44.42210912]]

Time Taken For Gradient Descent in Sec: 2.482538938522339

```

<center>
![](img/40b770758f087a02cb1a21213ee06468.png)
</center>

### 2.矢量化方法:

这里为了求解下面提到的数学表达式，我们使用**矩阵和**向量(线性代数)。

```
The above mathematical expression is a part of Cost Function.

```

<center>![\sum_{i=1}^m(h_{\theta}(x^i)-y^i)^2      ](img/f38d37ba8a554b0c9f0016b68253c872.png "Rendered by QuickLaTeX.com")
</center>

```
The above Mathematical Expression is the hypothesis.

```

<center>![h_{\theta}=\theta^T.X\\ where,\\ h_{\theta}=hypothesis.\\ \theta=  \begin{bmatrix}    \theta_{0} \\    \theta_{1}\\    \theta_{2}\\    \theta_{3}\\    .\\    .\\    \theta_{n}\\  \end{bmatrix} X= \begin{bmatrix}    {x_{0}} \\    {x_{1}}\\    {x_{2}}\\    {x_{3}}\\    .\\    .\\    {x_{n}}\\  \end{bmatrix}\\        ](img/f481b6061bbcea3489dfa37185e874a5.png "Rendered by QuickLaTeX.com")</center>

#### 批量梯度下降:

<center>![Loop\ until\ converge\{\\ \ \theta_{j}:=\theta_{j}-(1/m)*(\alpha)*\frac{\partial J(\theta)}{\partial \theta_{j}} \\ \}\\ Let, \ Gradients=\frac{\partial J(\theta)}{\partial \theta_{j}}](img/c41865826f334b5ea15f5ad372724b0e.png "Rendered by QuickLaTeX.com")</center>

#### 使用矩阵运算寻找梯度的概念:

![X\_New= \begin{bmatrix}    {x_{0}^1} & {x_{1}^1} \\    {x_{0}^2} & {x_{1}^2}\\    {x_{0}^3} & {x_{1}^3}\\    {x_{0}^4} & {x_{1}^4}\\    . & .\\    . & .\\    . & .\\    {x_{0}^m} & {x_{1}^m}  \end{bmatrix}_{m X 2}  \theta=  \begin{bmatrix}    \theta_{0} \\    \theta_{1}\\  \end{bmatrix}_{2X1}\\  where,\\  \x_{0}^i=1\\      ](img/ec09713fa80b6a55a5c32d3e53a11ce7.png "Rendered by QuickLaTeX.com")

![H(\theta)=X\_New\ .\ \theta\\ H(\theta)= \begin{bmatrix}    {\Theta_{0}}{x_{0}^1}+{\Theta_{1}}{x_{1}^1} \\    {\Theta_{0}}{x_{0}^2}+{\Theta_{1}}{x_{1}^2}\\    {\Theta_{0}}{x_{0}^3}+{\Theta_{1}}{x_{1}^3}\\    {\Theta_{0}}{x_{0}^4}+{\Theta_{1}}{x_{1}^4}\\    .\\    .\\    . \\    {\Theta_{0}}{x_{0}^m}+{\Theta_{1}}{x_{1}^m}  \end{bmatrix}_{mX1} And\ \ \  Y=  \begin{bmatrix}     {y^1}\\     {y^2}\\     {y^3}\\     .\\     .\\     .\\     {y^m}  \end{bmatrix}_{mX1}\\        ](img/ff565a2c06d365b93a0bc0b76145ea72.png "Rendered by QuickLaTeX.com")

![H(\theta)-Y= \begin{bmatrix}    {\Theta_{0}}{x_{0}^1}+{\Theta_{1}}{x_{1}^1} -y^1\\    {\Theta_{0}}{x_{0}^2}+{\Theta_{1}}{x_{1}^2}-y^2\\    {\Theta_{0}}{x_{0}^3}+{\Theta_{1}}{x_{1}^3}-y^3\\    {\Theta_{0}}{x_{0}^4}+{\Theta_{1}}{x_{1}^4}-y^4\\    .\\    .\\    . \\    {\Theta_{0}}{x_{0}^m}+{\Theta_{1}}{x_{1}^m}-y^m  \end{bmatrix}_{mX1} \\      ](img/91e67bbac3f8bda324693a18e03630bd.png "Rendered by QuickLaTeX.com")

![X\_New^T= \begin{bmatrix}    {x_{0}^1\ x_{0}^2\ x_{0}^3\ .\ .\ .\ x_{0}^m}\\    {x_{1}^1\ x_{1}^2\ x_{1}^3\ .\ .\ .\ x_{1}^m}  \end{bmatrix}_{2Xm} \\      ](img/6f2f1e55e058acd19a4a94f1c8620ad6.png "Rendered by QuickLaTeX.com")

![Gradients=X\_New\ . \ (H(\theta)-Y)\\ = \begin{bmatrix} {x_{0}^1(\Theta x_{0}^1+\Theta x_{1}^1-y^1)\ + \ x_{0}^2(\Theta x_{0}^2+\Theta x_{1}^2-y^2)\ + \ x_{0}^3(\Theta x_{0}^3+\Theta x_{1}^3-y^3)\ + . . .}\\ {x_{1}^1(\Theta x_{0}^1+\Theta x_{1}^1-y^1)\ + \ x_{1}^2(\Theta x_{0}^2+\Theta x_{1}^2-y^2)\ + \ x_{1}^3(\Theta x_{0}^3+\Theta x_{1}^3-y^3)\ + . . .}\\      \end{bmatrix}_{2X1}\\       ](img/6d5f5229ac2410c0ec7fb19d1897c5f2.png "Rendered by QuickLaTeX.com")

![Finally\ we\ can \ say,\\ \ \ \ Gradients=\frac{\partial J(\theta)}{\partial \theta_{j}}=X\_New^T.(X\_New.\theta-Y)  ](img/709f80d7dc8a6561e38885efecdf4bf0.png "Rendered by QuickLaTeX.com")

**代码:矢量化梯度下降法的 Python 实现**

```
# Import required modules.
from sklearn.datasets import make_regression
import matplotlib.pyplot as plt
import numpy as np
import time

# Create and plot the data set.
x, y = make_regression(n_samples = 100, n_features = 1,
                       n_informative = 1, noise = 10, random_state = 42)

plt.scatter(x, y, c = 'red')
plt.xlabel('Feature')
plt.ylabel('Target_Variable')
plt.title('Training Data')
plt.show()

# Adding x0=1 column to x array.
X_New = np.array([np.ones(len(x)), x.flatten()]).T

# Convert y from 1d to 2d array.
y = y.reshape(100, 1)

# Number of Iterations for Gradient Descent
num_iter = 1000

# Learning Rate
alpha = 0.01

# Number of Training samples.
m = len(x)

# Initializing Theta.
theta = np.zeros((2, 1),dtype = float)

# Batch-Gradient Descent.
start_time = time.time()

for i in range(num_iter):
    gradients = X_New.T.dot(X_New.dot(theta)- y)
    theta = theta - (1/m) * alpha * gradients

# Print the model parameters.    
print('model parameters:',theta,sep = '\n')

# Print Time Take for Gradient Descent to Run.
print('Time Taken For Gradient Descent in Sec:',time.time() - start_time)

# Hypothesis.
h = X_New.dot(theta) # Prediction on training data itself.

# Plot the Output.
plt.scatter(x, y, c = 'red')
plt.plot(x ,h)
plt.xlabel('Feature')
plt.ylabel('Target_Variable')
plt.title('Output')
```

#### 输出:

<center>![](img/712c3306bb2b1dede7765eab84018f9a.png)</center>

```
model parameters:
[[ 1.15857049]
 [44.42210912]]

Time Taken For Gradient Descent in Sec: 0.019551515579223633
```

<center>
![](img/40b770758f087a02cb1a21213ee06468.png)
</center>

#### **观测值:**

1.  实现矢量化方法减少了梯度下降(高效代码)的执行时间。
2.  易于调试。