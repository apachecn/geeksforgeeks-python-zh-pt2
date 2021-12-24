# 寻找巨型 GCD 子阵列的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-jumbo-gcd-subarray/](https://www.geeksforgeeks.org/python-program-to-find-the-jumbo-gcd-subarray/)

给定一个数组，编写一个程序，在给定数组大小> = 2 的所有子数组中找到最大 GCD。

**示例:**

```py
Input list: [2, 3, 4, 4, 4]
Output: 4

Input list: [3, 7, 2, 9, 18, 5, 1, 13 ]
Output: 9
```

### 方法:

*   导入 python 的数学模块
*   在遍历列表时，引入一个变量(比如 V1)来存储列表中每个元素的 gcd。
*   使用循环遍历数组或列表的元素。
*   每次迭代时调用 ***math.gcd()函数。**T3】*
*   每次迭代时，将 math.gcd()函数的结果存储到另一个变量(比如 V2)中。
*   现在比较一下 V1 和 V2。如果 V2 比 V1 大，就让 V1 等于 V2。
*   让循环运行，打印出 V1 的最终值。

下面可以找到上述方法的实现:
**例 1:**

## 蟒蛇 3

```py
import math

# input list
List = [2, 3, 4, 4, 4 ]

max1 = 0
for i in range(len(List)-1):

  # use math.gcd() function
  gcd1 = math.gcd(List[i], List[i + 1])
  if(gcd1>max1):
    max1 = gcd1

# print max1
# as the result
print(max1)
```

**输出:**

```py
4

```

**解释:**
对于给定的阵列，具有最大 gcd 的子阵列之一是具有 gcd 4 的[3，5]。

**例 2:**

## 蟒蛇 3

```py
import math

# input list
List = [3, 7, 2, 9, 18, 5, 1, 13 ]

max1 = 0
for i in range(len(List)-1):

  # use math.gcd() function
  gcd1 = math.gcd(List[i], List[i + 1])
  if(gcd1>max1):
    max1 = gcd1

# print max1
# as the result
print(max1)
```

**输出:**

```py
9

```

**解释:**
对于给定的阵列，具有最大 gcd 的子阵列之一是 gcd 为 9 的[4，5]。