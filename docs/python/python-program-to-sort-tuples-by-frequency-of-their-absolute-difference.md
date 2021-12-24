# Python 程序根据元组绝对差异的频率对元组进行排序

> 原文:[https://www . geeksforgeeks . org/python-程序-按绝对差异频率对元组进行排序/](https://www.geeksforgeeks.org/python-program-to-sort-tuples-by-frequency-of-their-absolute-difference/)

给定二元组列表，这里的任务是编写一个 python 程序，可以根据元素绝对差异的频率对它们进行排序。

> **输入** : [(1，6)，(11，3)，(9，1)，(6，11)，(2，10)，(5，7)]
> 
> **输出:** [(5，7)，(1，6)，(6，11)，(11，3)，(9，1)，(2，10)]
> 
> **解释:**7–5 = 2 只出现 1 次。5 出现两次[(6–1)，(11–6)]和 8 出现三次作为差异。
> 
> **输入:** [(1，6)，(6，11)，(5，7)]
> 
> **输出:** [(5，7)，(1，6)，(6，11)]
> 
> **解释:**7–5 = 2 只出现 1 次。5 出现两次[(6–1)，(11–6)]。

**方法:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*ABS()*](https://www.geeksforgeeks.org/abs-in-python/)*[*count()*](https://www.geeksforgeeks.org/python-list-function-count/#:~:text=count()%20is%20an%20inbuilt,given%20object%20occurs%20in%20list.&text=Parameters%20%3A,count%20is%20to%20be%20returned.)*和* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**

**在本文中，我们使用 abs()和列表理解来执行计算每个绝对差的任务。然后，sorted()和 count()用于根据绝对差的计算结果对元组进行排序。**

****示例:****

## **蟒蛇 3**

```
**# initializing list
test_list = [(1, 6), (11, 3), (9, 1), (6, 11), (2, 10), (5, 7)]

# printing original list
print("The original list is : " + str(test_list))

# getting differences pairs
diff_list = [abs(x - y) for x, y in test_list]

# sorting list by computed differences
res = sorted(test_list, key = lambda sub: diff_list.count(abs(sub[0] - sub[1])))

# printing result
print("Sorted Tuples : " + str(res))**
```

****输出:****

> **原清单为:[(1，6)，(11，3)，(9，1)，(6，11)，(2，10)，(5，7)]**
> 
> **排序元组:[(5，7)，(1，6)，(6，11)，(11，3)，(9，1)，(2，10)]**