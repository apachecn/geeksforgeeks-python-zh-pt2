# Python 程序通过重叠中间元组来合并元组列表

> 原文:[https://www . geesforgeks . org/python-程序-合并-元组-列表-重叠-中元组/](https://www.geeksforgeeks.org/python-program-to-merge-tuple-list-by-overlapping-mid-tuple/)

给定两个包含元组作为元素的列表，任务是在考虑第一个列表的两个连续元组之间存在的范围之后，编写一个 Python 程序来容纳第二个列表的元组和第一个列表的连续元组之间的元组。

> **输入** : test_list1 = [(4，8)，(19，22)，(28，30)，(31，50)]，test_list2 = [(10，12)，(23，26)，(15，20)，(52，58)]
> **输出**:[(4，8)，(10，12)，(19，22))，((19，22)，(23，26)，(28，30))，((4，8)，(2)
> 
> **输入** : test_list1 = [(4，8)，(19，22)，(28，30)，(31，50)]，test_list2 = [(10，22)，(23，26)，(15，20)，(52，58)]
> **输出**:[(19，22)，(23，26)，(28，30))，((4，8)，(15，20)，(19，22))]
> **解释**

**方法:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这里，我们保留了两个指针，一个用于每个容器，另一个用于列表 1 中的每个元素。现在，检查列表 2 中的任何元组是否能满足要求的条件，如果不能，则为下一组迭代考虑以下连续元素。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Merge tuple list by overlapping mid tuple
# Using loop

# initializing lists
test_list1 = [(4, 8), (19, 22), (28, 30), (91, 98)]
test_list2 = [(10, 22), (23, 26), (15, 20), (52, 58)]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

idx = 0
j = 0
res = list()

# iterating till anyone of list exhausts.
while j < len(test_list2):

    # checking for mid tuple and appending
    if test_list2[j][0] > test_list1[idx][0]\
    and test_list2[j][1] < test_list1[idx + 1][1]:

        # appending the range element from 2nd list which 
        # fits consecution along with original elements 
        # from 1st list.
        res.append((test_list1[idx], test_list2[j], test_list1[idx + 1]))
        j += 1
        idx = 0
    else:

        # if not, the 1st list is iterated and next two
        # ranges are compared for a fit.
        idx += 1

    # restart indices once limits are checked.
    if idx == len(test_list1) - 1:
        idx = 0
        j += 1

# printing result
print("Merged Tuples : " + str(res))
```

**输出:**

> 原列表 1 为:[(4，8)，(19，22)，(28，30)，(91，98)]
> 
> 原清单 2 为:[(10，22)，(23，26)，(15，20)，(52，58)]
> 
> 合并元组:[(19，22)，(23，26)，(28，30))，((4，8)，(15，20)，(19，22))，((28，30)，(52，58)，(91，98))]