# 等分一串(Python 中的石斑鱼)

> 原文:[https://www . geeksforgeeks . org/split-一串等份-python 中的石斑鱼/](https://www.geeksforgeeks.org/split-a-string-in-equal-parts-grouper-in-python/)

**`Grouper recipe`** 是一个扩展的工具集，使用现有的`itertool` 作为构建块。它将数据收集到固定长度的块中。

**使用的现有迭代工具:**
**`izip_longest(*iterables[, fillvalue])` :** 创建一个迭代器，从每个迭代表中聚合元素。如果数据项长度不均匀，缺失的值用 fillvalue 填充。迭代一直持续到最长的可迭代次数用完。

**性能:**

*   扩展工具提供了与底层工具集相同的高性能。
*   卓越的内存性能是通过一次处理一个元素来保持的，而不是一次将所有可迭代的元素都放入内存。
*   通过以一种有助于消除临时变量的函数式方式将工具链接在一起，代码量得以保持较小。
*   相对于使用导致解释器开销的 for 循环和生成器，更喜欢使用“矢量化”构建块，从而保持了高速度。

**示例:**

```py
Input : str = ABCDEFG, l = 3
Output : ABC DEF Gxx
Explanation: 
Grouping characters of string in set of 3: ABC DEF Gxx.
'x' is added to the set which doesn't have 3 elements in it. 

Input : str = GEEKSFORGEEKS, l = 5
Output : GEEKS FORGE EKSxx
```

下面是蟒蛇 3 的代码:

```py
# Python3 code for the grouper recipe

# import the existing itertool izip_longest
from itertools import izip_longest

# function for the grouper recipe
def grouper(iterable, n, fillvalue ='x'):

    # create 'n'-blocks for collection
    args = [iter(iterable)] * n

    # collect data into fixed length blocks of
    # length 'n' using izip_longest and store
    # result as a list
    ans = list(izip_longest(fillvalue = fillvalue, *args))

    # (optional) loop to convert ans to string
    t = len(ans)
    for i in range(t):
        ans[i] = "".join(ans[i])

    # return ans as string    
    return " ".join(ans)    

# Driver code
s = "ABCDEFG"
k = 3

result = grouper(s, k)
print(result)    
```

**输出:**

```py
ABC DEF Gxx
```