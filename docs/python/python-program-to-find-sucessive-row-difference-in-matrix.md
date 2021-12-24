# Python 程序查找矩阵中的连续行差

> 原文:[https://www . geesforgeks . org/python-program-to-find-success-row-in-difference-in-matrix/](https://www.geeksforgeeks.org/python-program-to-find-sucessive-row-difference-in-matrix/)

给定一个矩阵，任务是编写一个 Python 程序，根据存在的元素执行与前一行不同的操作。

> **输入:** test_list = [[5，6，3，1]，[7，5，3，1]，[3，2]，[7，3，3，2]，[2，3]，[9，8，1]]
> 
> **输出:** [[]，[7]，[2]，[7]，[]，[8，9，1]]
> 
> **说明:**比较第 1 行和第 2 行，第 2 行只有 7 个，第 1 行没有，因此输出[7]。
> 
> **输入:** test_list = [[5，6]，[7，5，3，1]，[3，4]，[7]，[2，9]，[9，8，1]]
> 
> **输出:** [[]，[1，3，7]，[4]，[7]，[9，2]，[8，1]]
> 
> **说明:**比较第二和第三个列表，第三个列表只有 4 个，第二个没有，因此输出。

**示例:使用**[**set . difference()**](https://www.geeksforgeeks.org/python-set-difference/)**+**[**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，保持先前的集合，保持对先前集合的跟踪以获得差异。这将删除当前列表中已存在于先前列表中的所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sucessive row difference in Matrix
# Using set.difference + loop

# initializing list
test_list = [[5, 6, 3, 1], [7, 5, 3, 1],
             [3, 2], [7, 3, 3, 2],
             [2, 3], [9, 8, 1]]

# printing original list
print("The original list is : " + str(test_list))

res = []
prev = set(test_list[0])
for ele in test_list:

    # appending difference set diff with previous
    # element
    res.append(list(set(ele).difference(prev)))

    # updating prev. for comparison
    prev = set(ele)

# printing result
print("Sucessive Row difference : " + str(res))
```

**输出:**

> 原来的名单是:[[5，6，3，1]，[7，5，3，1]，[3，2]，[7，3，3，2]，[2，3]，[9，8，1]]
> 
> 连续行差:[[]，[7]，[2]，[7]，[]，[8，9，1]]