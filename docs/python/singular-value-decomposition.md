# 奇异值分解

> 原文:[https://www.geeksforgeeks.org/singular-value-decomposition/](https://www.geeksforgeeks.org/singular-value-decomposition/)

**先决条件:** [矩阵对角化](https://www.geeksforgeeks.org/matrix-diagonalization/)[特征向量计算和低秩逼近](https://www.geeksforgeeks.org/eigenvector-computation-and-low-rank-approximations/)

在深入研究奇异值分解之前，让我们先简单了解一下什么是矩阵对角化技术，以及当它不能有效执行时。

**矩阵对角化**

矩阵对角化是取一个*方阵*并将其转化为一种特殊类型的矩阵即对角矩阵的过程。该矩阵与基础矩阵具有相同的基本属性。数学上，任何输入矩阵 A 都可以简化为任何对角矩阵 D，如果它满足:

<center>![D = P ^{-1} A P ](img/57dfe1d7580cbda6e57e63bf7ac0b091.png "Rendered by QuickLaTeX.com")</center>

```
where,
P -> Modal Matrix: It is a (n x n) matrix that consists of eigen-vectors. 
               It is generally used in the process of diagonalization 
               and similarity transformation.
```

然而，矩阵对角化技术**对于形式为( **m x n)** 的矩阵**失败，其中 **m ≠ n** 。(即当矩阵不是正方形矩阵时。这就是*‘奇异值分解’*的由来，为这个问题提供了很好的解决方案。

**奇异值(σ)**

设 *A* 为任意的 *m x n* 秩为 *r.* 的矩阵，将其与其转置相乘(即 *A <sup>T</sup> A* ，则生成一个 *n x n* 矩阵，该矩阵是对称的，同时也是正半定的。简单来说，所有 *A <sup>T</sup> A* 矩阵的特征值 *(λ <sub>i…r</sub> )* 都是非负的(即大于 0)。

奇异值被定义为获得的特征值的平方根。那就是:

<center>![\sigma_i = \sqrt{\lambda_i} \\ where \ (i \le r)](img/0f9bdcbb4bfa560aa44129282385ffb5.png "Rendered by QuickLaTeX.com")</center>

**奇异值分解**

让 *A* 成为任意 *m x n* 矩阵。然后奇异值分解将这个矩阵分成两个性质上正交的酉矩阵和一个包含奇异值的矩形对角矩阵，直到 *r* 。数学上，它表示为:

<center>![A = U \Sigma V^T ](img/a78687f9e62a9fd61f7154b10fc98a9d.png "Rendered by QuickLaTeX.com")</center>

```
where, 
Σ -> (m x n) orthogonal matrix
U -> (m x m) orthogonal matrix 
V -> (n x n) diagonal matrix with first r rows having only singular values.
     (Rest of the values are 0) 
```

现在，重要的是理解如何计算矩阵 **U** 、**V**&**σ**。

**计算正交矩阵 V**

首先，我们计算与输入矩阵 a 相关联的本征向量 x <sub>i</sub> ，然后，通过将向量 x <sub>i</sub> 中的每个值除以其大小，我们找到对应于 x <sub>i</sub> 的归一化向量 v <sub>i</sub> 。例如:

```
Let x = [1,2,4]
=> mag(x) or |x| = √(12 + 22 + 42) = √21.

Therefore, v = [(1/√21), (2/√21), (4/√21)]
```

我们知道， *A* 是 *m x n* 矩阵。因此，A <sup>T</sup> A 是 n×n 对称矩阵，所有特征值> 0。因此，我们可以得到 A <sup>T</sup> A 的本征向量 v <sub>1…n</sub> 这样:

<center>![(A^TA)v_i = \sigma_i^2v_i = \lambda_iv_i](img/00577d3af0b686b23f2fb82b5db09b9e.png "Rendered by QuickLaTeX.com")</center>

```
where,
x<sub>i -></sub> eigen vector
v<sub>i -></sub> normalized eigen vector.
and
σ<sub>i -></sub> corresponding singular value.
λ<sub>i -></sub> corresponding eigen value.
```

计算 *AAT* 的特征向量后，矩阵 *V* 将为:

<center>![V = \begin{bmatrix} v_1 & v_2 & ...\ v_i\end{bmatrix}](img/538740f28870aa97d01b5f6cb7d987e5.png "Rendered by QuickLaTeX.com")</center>

```
where, v1, v2, ... vi are arranged column-wise into matrix V.
```

**计算正交矩阵 U**

同样，对于任何 *A* ( *m x n* )矩阵，*AA<sup>T</sup>T7】是一个 *m x m* 对称矩阵，所有特征值> 0。因此，我们可以得到 *AA <sup>T</sup>* 的特征向量 x <sub>1…n</sub> ，这样:*

<center>![(AA^T)x_i = \sigma_i^2x_i = \lambda_ix_i](img/5f3c3fb795d69c9eaaf75fb3fb1e71fa.png "Rendered by QuickLaTeX.com")</center>

```
where,
x<sub>i -></sub> eigen vector.
and
σ<sub>i -></sub> corresponding singular value.
λ<sub>i -></sub> corresponding eigen value.
```

现在，我们用下面的等式来计算矩阵 U:

<center>![u_i = \frac{Av_i}{\sigma_i}](img/81a0df22c22172fd5bd80e5570a2e047.png "Rendered by QuickLaTeX.com")</center>

计算后，矩阵 U 将为:

<center>![U = \begin{bmatrix} u_1 & u_2 & ...\ u_i\end{bmatrix}](img/b8dc82f99e8ad09cb661cffbdac43a8b.png "Rendered by QuickLaTeX.com")</center>

```
where, u1, u2, ... ui are arranged column-wise into matrix U.
```

**计算对角矩阵σ**

这里，矩阵 A 有秩(A) = r，其中 r ≤ min (m，n)。

**情况 1:** 如果 **m ≤ n** ，假设 m = 2 & n = 4，那么假设所有(σ <sub>i</sub> > 0)，σ可以表示为:

<center>![\begin{bmatrix} \sigma_1 & 0 & 0 & 0\\ 0 & \sigma_2 & 0 & 0\\ \end{bmatrix}](img/298d793f6b2269fb44913d32983cab37.png "Rendered by QuickLaTeX.com")</center>

**情况 2:** 如果 m ≥ n，假设 m = 5 & n = 3，那么假设所有(σ <sub>i</sub> > 0)，σ可以表示为:

<center>![\begin{bmatrix} \sigma_1 & 0 & 0 \\ 0 & \sigma_2 & 0 \\ 0 & 0 & \sigma_3 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{bmatrix}](img/3063b12dcee01af52bbc871ac18924b0.png "Rendered by QuickLaTeX.com")</center>

**特例:**指定矩阵秩时，假设 r = 3，m = 6 & n = 4。那么σ可以表示为:

<center>![\begin{bmatrix} \sigma_1 & 0 & 0 & 0\\ 0 & \sigma_2 & 0 & 0\\ 0 & 0 & \sigma_3 & 0\\ 0 & 0 & 0 & 0\\ 0 & 0 & 0 & 0\\ 0 & 0 & 0 & 0 \end{bmatrix}](img/45794b0b667ab6494f79a50b6260a57a.png "Rendered by QuickLaTeX.com")</center>

这意味着 **σ <sub>4</sub> ≤ 0** ，因此被丢弃。

> **注:**奇异值个数其中**σ<sub>I</sub>T8】0**可以确定矩阵的秩。

**例题**

考虑以下问题。求一个(*2×3*)矩阵 A 的奇异值分解，矩阵 A 的值为:

<center>![A =\begin{bmatrix} 1 & 1 & 0\\ 0 & 1 & 1\\ \end{bmatrix}](img/ad450011a3ff9986860ed7318bc4a26e.png "Rendered by QuickLaTeX.com")</center>

**解决方案**

让我们了解解决此类问题所需的每个步骤。

```
Step 1 - Find AT and then compute ATA.
```

<center>![A = \begin{bmatrix} 1 & 1 & 0\\ 0 & 1 & 1\\ \end{bmatrix} \\ then, \\ A^T = \begin{bmatrix} 1 & 0 \\ 1 & 1 \\ 0 & 1 \\ \end{bmatrix}](img/769a0eca50422eabddb33d51e45d2525.png "Rendered by QuickLaTeX.com")</center>

<center>![A^TA = \begin{bmatrix} 1 & 0 \\ 1 & 1 \\ 0 & 1 \\ \end{bmatrix} \begin{bmatrix} 1 & 1 & 0\\ 0 & 1 & 1\\ \end{bmatrix} = \begin{bmatrix} 1 & 1 & 0\\ 1 & 2 & 1\\ 0 & 1 & 1\\ \end{bmatrix}](img/de0980180f73424d41fea9403e8adfd1.png "Rendered by QuickLaTeX.com")</center>

```
Step 2 - Find the eigen values associated with matrix ATA. 
         (Discussed in the prerequisite articles mentioned above)
```

**与 A <sup>T</sup> A 相关的特征值:** λ = 0，1 & 3。

```
Step 3 - Find the singular values corresponding to the obtained 
         eigen values using formula:
```

<center>![\sigma_i = \sqrt{\lambda_i}](img/bf09dcd5ccf65538d8ded8e8e6f1a86b.png "Rendered by QuickLaTeX.com")</center>

**与 A <sup>T</sup> A 相关的奇异值:** λ = 3，1 & 0。

```
λ1 = 3 -> σ1 = √3
λ2 = 1 -> σ2 = 1 
λ3 = 0 -> σ3 = 0
```

```
Step 4 - Compute diagonal matrix Σ using the values of σ keeping
         the above discussed cases in mind.
```

作为(m = 2 < n = 3)，应用情况 1，矩阵σ为:

<center>![\Sigma = \begin{bmatrix} \sqrt{3} & 0 & 0\\ 0 & 1 & 0\\ \end{bmatrix}](img/d42e83aff2839048e1b3df52d68b6895.png "Rendered by QuickLaTeX.com")</center>

```
Step 5 - Find the eigen vectors & corresponding normalized eigen vectors
         associated with matrix ATA.
 (Discussed in the prerequisite articles mentioned above)
```

> **注:**重要的是要理解 A <sup>T</sup> A 的归一化特征向量定义了矩阵 v

**与 A <sup>T</sup> A:** 相关的特征向量

```
For λ<sub>1 = 3 -></sub> x1 = [1, 2, 1]
For λ<sub>2 = 1 -></sub> x2 = [-1, 0, 1]
For λ<sub>3 = 0 -></sub> x3 = [1, -1, 1]

where x1, x2 and x3 are eigen vectors of matrix ATA. 
```

**与 A <sup>T</sup> A:** 关联的归一化特征向量

```
For x1 = [1, 2, 1] => v1 = [(1/√6), (2/√6), (1/√6)]
For x2 = [-1, 0, 1] => v2 = [(-1/√2), 0, (1/√2)]
For x3 = [1, -1, 1] => v3 = [(1/√3), (-1/√3), (1/√3)]

where v1, v2 and v3 are eigen vectors of matrix ATA. 
```

```
Step 6 - Use eigen vectors obtained to compute matrix V.
```

<center>![V = \begin{bmatrix} (1/√6) & (-1/√2) & (1/√3)\\ (2/√6) & 0 & (-1/√3)\\ (1/√6) & (1/√2) & (1/√3)\\ \end{bmatrix}](img/a22c52d32464ac600edc576dcf2587ec.png "Rendered by QuickLaTeX.com")</center>

```
Step 7 - Use the above given equation to compute the orthogonal matrix U. 
```

<center>![u_1 = \frac{Av_1}{\sigma_1} \\ =\frac{1}{\sqrt{3}}\begin{bmatrix} 1 & 1 & 0\\ 0 & 1 & 1\\ \end{bmatrix}\begin{bmatrix} (1/√6) \\ (2/√6) \\ (1/√6) \\ \end{bmatrix} = \begin{bmatrix} (1/√2) \\ (1/√2) \end{bmatrix}](img/b76e98f46358c21b6be557a5d34ce99c.png "Rendered by QuickLaTeX.com")</center>

<center>![u_2 = \frac{Av_2}{\sigma_2} \\ =\frac{1}{1}\begin{bmatrix} 1 & 1 & 0\\ 0 & 1 & 1\\ \end{bmatrix}\begin{bmatrix} (-1/√2) \\ 0 \\ (1/√2) \\ \end{bmatrix} = \begin{bmatrix} (-1/√2) \\ (1/√2) \end{bmatrix}](img/5403a07e312a492d07cb4f80aafea803.png "Rendered by QuickLaTeX.com")</center>

因此，正交矩阵 U 为:

<center>![U = \begin{bmatrix} (1/√2) & (-1/√2) \\ (1/√2) & (1/√2) \end{bmatrix}](img/aab030540db9307eef20a8ddff0ac2e1.png "Rendered by QuickLaTeX.com")</center>

```
Step 8 - Compute the SVD of A using the equation given below: 
         (As discussed above)
```

<center>![A = U \Sigma V^T ](img/a78687f9e62a9fd61f7154b10fc98a9d.png "Rendered by QuickLaTeX.com")</center>

因此，使用奇异值分解， *A* 可以表示为:

<center>![A = U \Sigma V^T \\ = \begin{bmatrix} (1/√2) & (-1/√2) \\ (1/√2) & (1/√2) \end{bmatrix} \begin{bmatrix} \sqrt{3} & 0 & 0\\ 0 & 1 & 0\\ \end{bmatrix} \begin{bmatrix} (1/√6) & (-1/√2) & (1/√3)\\ (2/√6) & 0 & (-1/√3)\\ (1/√6) & (1/√2) & (1/√3)\\ \end{bmatrix}](img/866aaba399ec26566b1ff58fe6f0b0ce.png "Rendered by QuickLaTeX.com")</center>