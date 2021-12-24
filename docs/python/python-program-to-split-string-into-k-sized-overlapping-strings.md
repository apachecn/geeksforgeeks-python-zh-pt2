# Python 程序将字符串拆分成 k 个大小的重叠字符串

> 原文:[https://www . geesforgeks . org/python-程序-将字符串拆分成 k 大小的重叠字符串/](https://www.geeksforgeeks.org/python-program-to-split-string-into-k-sized-overlapping-strings/)

给定一个字符串，任务是编写一个 Python 程序，根据大小 k 从原始字符串中提取重叠的连续字符串切片。

**示例:**

> **输入:** test_str = 'Geeksforgeeks '，K = 4
> 
> **输出:【Geek，【eeks】、【eks】、【eksf】、【ksfo】、【稳定部队】、【forg】、【大麦】、【gege】、【geek】、【eeks】**
> 
> **说明:**输出连续重叠的 4 个大小的字符串。
> 
> **输入:** test_str = 'Geeksforgeeks '，K = 6
> 
> **输出:【Geeksf】、【eeksfo】、【ekstable】、【ksforg】、【sforge】、【forgee】、【orgy】、【rgeoek】、【rgeeks】**
> 
> **说明:**输出连续重叠的 6 个大小的字符串。

**方法 1:使用**[**is lice()**](https://www.geeksforgeeks.org/python-itertools-islice/)**+**[**生成器功能**](https://www.geeksforgeeks.org/generators-in-python/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)

**在这种情况下，使用 islice()提取大小为 K 的窗口，并使用 yield 以中间方式产生结果。使用 join()连接最终结果。**

## **蟒蛇 3**

```py
# Python3 code to demonstrate working of
# Overlapping consecutive K splits
# Using islice() + generator function + join() 
from itertools import islice

# generator function 
def over_slice(test_str, K):
    itr = iter(test_str)
    res = tuple(islice(itr, K))
    if len(res) == K:
        yield res    
    for ele in itr:
        res = res[1:] + (ele,)
        yield res

# initializing string
test_str = 'Geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 4

# calling generator function 
res = ["".join(ele) for ele in over_slice(test_str, K)]

# printing result
print("Overlapping windows : " + str(res))
```