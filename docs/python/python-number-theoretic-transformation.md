# Python |数论变换

> 原文:[https://www . geeksforgeeks . org/python-数论-变换/](https://www.geeksforgeeks.org/python-number-theoretic-transformation/)

数论变换是快速傅里叶变换定理的推广。它是通过用第 n 个原始单位根替换 e^(-2piik/N 而获得的。所以这意味着，代替复数 C，在商环 **Z/pZ** 上使用变换。该理论基于并使用了有限域和数论的概念。

数论变换模必须是素数。但是如果它是质数，它会让事情变得更简单。人们可以用复合模量进行 NTT。对于模数:

*   n <sup>第</sup>根的统一存在
*   n 的乘法逆

数论变换基本上是**傅里叶变换**。另外，假设给出了一个**标准离散傅里叶变换**，并且可以通过将数据乘以傅里叶矩阵以矩阵形式完成。让我们假设 N = 4。然后，矩阵可以是–

```
[ 1   1    1    1  ]
[ 1   w   w^2  w^3 ]
[ 1  w^2  w^4  w^6 ]
[ 1  w^3  w^6  w^9 ]

```

## **sympy . discrete . transforms . ntt():**

它可以对序列进行**数论变换(NTT)** 。
它专门研究带有 **Z/pZ** 的离散傅里叶变换(DFT)商环，用于素数 na 的复数而不是复数。

由于基数为 2 的快速傅立叶变换要求样本点数为 2 的幂，因此序列会自动向右填充零。

```

Parameters : 
-> seq       : [iterable] sequence on which DFT is to be applied.
-> prime no. : [Integer] prime modulus for NTT to perform on.

Returns : 
Number Theoretic Transform

```

**例 1 :**

```
# import sympy 
from sympy import ntt

# sequence 
seq = [15, 21, 13, 44]

prime_no = 3 * 2**8 + 1

# ntt
transform = ntt(seq, prime_no)
print ("NTT : ", transform)
```

**输出:**

```
NTT :  [93, 114, 732, 659]
```

 **例 2 :**

```
# import sympy 
from sympy import ntt

# sequence 
seq = [153, 321, 133, 44, ]

# Prime modulus of the form (m * 2**k + 1)
prime_no = 3 * 2**8 + 1

# ntt
transform = ntt(seq, prime_no)
print ("NTT : ", transform)
```

**输出:**

```
NTT :  [651, 276, 690, 533]

```