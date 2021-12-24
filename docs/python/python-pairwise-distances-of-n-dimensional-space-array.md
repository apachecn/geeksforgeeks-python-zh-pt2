# Python–n 维空间数组的成对距离

> 原文:[https://www . geesforgeks . org/python-成对 n 维空间距离-数组/](https://www.geeksforgeeks.org/python-pairwise-distances-of-n-dimensional-space-array/)

**scipy.stats.pdist(array，axis=0)** 函数计算 n 维空间中观测值之间的成对距离。

> **参数:**
> **数组:**输入数组或对象，该数组或对象具有计算两两距离的元素
> **轴:**轴，沿该轴进行计算。默认情况下，轴= 0
> 
> **返回:**基于设置参数的数组元素的成对距离。

**代码#1 : 2D 阵**

```
from scipy.spatial.distance import pdist

arr1 = pdist([[1, 3, 27], 
             [3, 6, 8]]) 

print("Arithmetic Mean is :", arr1) 
```

**输出:**

```
Value of pdist is : [19.33907961]

```

**代码#2 : 3D 阵列**

```
from scipy.spatial.distance import pdist

arr1 = [[1, 3, 27],  
        [3, 4, 6],  
        [7, 6, 3],  
        [3, 6, 8]]  

print("Arithmetic Mean is :", pdist(arr1))  
```

**输出:**

```
Value of pdist is : [21.11871208 24.91987159 19.33907961  
                    5.38516481  2.82842712  6.40312424]

```