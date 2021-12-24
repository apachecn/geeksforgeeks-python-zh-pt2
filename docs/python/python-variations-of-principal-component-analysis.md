# Python–主成分分析的变体

> 原文:[https://www . geeksforgeeks . org/python-主成分分析变体/](https://www.geeksforgeeks.org/python-variations-of-principal-component-analysis/)

**主成分分析**是一种无监督降维和可视化技术。它通常被称为线性技术，因为新特征的映射是由特征乘以主成分分析特征向量矩阵给出的。它的工作原理是简单地识别靠近数据的超平面，然后将数据投影到其上，以最大化方差。由于主成分分析所遵循的简单方法，它被广泛应用于数据挖掘、生物信息学、心理学等领域。我们大多数人都没有意识到这样一个事实，即有各种版本的算法比传统的方法更好。让我们一个一个来看。

**随机化主成分分析:**
这是主成分分析的扩展，它使用数据的近似奇异值分解。常规主成分分析在 O(n*p <sup>2</sup> ) + O(p <sup>3</sup> )中工作，其中 *n* 是数据点的数量， *p* 是特征的数量，而随机化版本在 O(n*d*2) + O(d <sup>3</sup> 中工作，其中 d 是主成分的数量。因此，当 *d* 比 *n* 小得多时，它是极快的。
sklearn 在 **sklearn.utils.extmath** 中提供了一个随机化 _svd 的方法，可以用来做随机化 PCA。该方法返回三个矩阵: *U* 是 *m x m* 矩阵，Sigma 是 *m x n* 对角矩阵， *V^T* 是 *n x n* 矩阵的转置，其中 t 是上标。另一种方法是使用**sklearn . declaration . PCA**，将 svd_solver 超参数从“自动”更改为“随机化”或“完全”。但是，如果 *p* 或 *n* 超过 500 或主成分数小于 *p* 和 *n* 的 80%，Scikit-learn 会自动使用随机化 PCA。

**代码:**

## 蟒蛇 3

```py
# Python3 program to show the working of
# randomized PCA

# importing libraries
import numpy as np
from sklearn.decomposition import PCA
from sklearn.utils.extmath import randomized_svd

# dummy data
X = np.array([[-1, -1], [-2, -1], [-3, -2], [1, 1], [2, 1], [3, 2]])

# creates instance of PCA with randomized svd_solver
pca = PCA(n_components = 2, svd_solver ='randomized')

# This function takes a matrix and returns the
# U, Sigma and V ^ T elements
U, S, VT = randomized_svd(X, n_components = 2)

# matrix returned by randomized_svd
print(f"Matrix U of size m * m: {U}\n")
print(f"Matrix S of size m * n: {S}\n")
print(f"Matrix V ^ T of size n * n: {VT}\n")

# fitting the pca model
pca.fit(X)

# printing the explained variance ratio
print("Explained Variance using PCA with randomized svd_solver:", pca.explained_variance_ratio_)
```

**输出:**

```py
Matrix U of size m*m: [[ 0.21956688 -0.53396977]
 [ 0.35264795  0.45713538]
 [ 0.57221483 -0.07683439]
 [-0.21956688  0.53396977]
 [-0.35264795 -0.45713538]
 [-0.57221483  0.07683439]]

Matrix S of size m*n: [6.30061232 0.54980396]

Matrix V^T of size n*n: [[-0.83849224 -0.54491354]
 [-0.54491354  0.83849224]]

Explained Variance using PCA with randomized svd_solver: [0.99244289 0.00755711]
```

**增量主成分分析:**
主成分分析和大多数降维算法的主要问题是，它们要求整个数据在一个时间内适合内存，并且由于数据有时非常庞大，因此很难适合内存。
幸运的是，有一种称为增量主成分分析的算法，它对大型训练数据集很有用，因为它将数据分成最小批次，并一次一批次地将其馈送给增量主成分分析。这被称为动态学习。由于一次内存中没有多少数据，因此内存使用受到控制。
Scikit-Learn 为我们提供了一个名为 sklearn . declaration . incrementalpca 的类，我们可以使用它来实现这一点。

**代码:**

## 蟒蛇 3

```py
# Python3 program to show the working of
# incremental PCA

# importing libraries
import numpy as np
from sklearn.decomposition import IncrementalPCA

# dummy data
X = np.array([[-1, -1], [-2, -1], [-3, -2], [1, 1], [2, 1], [3, 2]])

# specify the number of batches
no_of_batches = 3

# create an instance of IncrementalPCA
incremental_pca = IncrementalPCA(n_components = 2)

# fit the data in batches
for batch in np.array_split(X, no_of_batches):
  incremental_pca.fit(batch)

# fit and transform the data
final = incremental_pca.transform(X)

# prints an 2d-array (as n_components = 2)
print(final)
```

**输出:**

```py
[[-4.24264069e+00  7.07106781e-01]
 [-4.94974747e+00  1.41421356e+00]
 [-6.36396103e+00  1.41421356e+00]
 [-1.41421356e+00  7.07106781e-01]
 [-7.07106781e-01 -5.55111512e-17]
 [ 7.07106781e-01  5.55111512e-17]]
```

**核主成分分析:**
核主成分分析是使用核的主成分分析的又一扩展。内核是一种数学技术，使用它我们可以将实例映射到称为特征空间的非常高维的空间，从而实现支持向量机(SVM)的非线性分类和回归。这通常用于新颖性检测和图像去噪。
Scikit-Learn 在 sklearn.decomposition 中提供了一个类 KernelPCA，可以用来执行内核 PCA。

**代码:**

## 蟒蛇 3

```py
# Python3 program to show the working of
# Kernel PCA

# importing libraries
import numpy as np
from sklearn.decomposition import KernelPCA

# dummy data
X = np.array([[-1, -1], [-2, -1], [-3, -2], [1, 1], [2, 1], [3, 2]])

# creating an instance of KernelPCA using rbf kernel
kernel_pca = KernelPCA(n_components = 2, kernel ="rbf", gamma = 0.03)

# fit and transform the data
final = kernel_pca.fit_transform(X)

# prints an 2d-array (as n_components = 2)
print(final)
```

**输出:**

```py
[[-0.3149893  -0.17944928]
 [-0.46965347 -0.0475298 ]
 [-0.62541667  0.22697909]
 [ 0.3149893  -0.17944928]
 [ 0.46965347 -0.0475298 ]
 [ 0.62541667  0.22697909]]
```

核主成分分析是无监督的，因此没有明显的方法来选择最佳核。由于我们通常将降维作为监督学习算法中的一个步骤，因此我们可以使用带有 GridSearchCV 的管道来选择最佳超参数，然后使用这些超参数(核和伽马)来获得最佳的分类精度。