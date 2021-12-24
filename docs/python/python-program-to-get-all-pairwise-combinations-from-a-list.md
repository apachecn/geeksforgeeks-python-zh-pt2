# Python 程序从列表中获取所有成对组合

> 原文:[https://www . geesforgeks . org/python-program-to-get-all-pair-combines-from-list/](https://www.geeksforgeeks.org/python-program-to-get-all-pairwise-combinations-from-a-list/)

给定一个列表。任务是编写一个 Python 程序，从列表中获取所有成对组合。

### 查找所有对(无唯一性)

**示例:**

> **输入:**【1，“Mallika”，2，“Yash”】
> 
> **输出：** [（1， 'Mallika'）， （1， 2）， （1， 'Yash'）， （'Mallika'， 1）， （'Mallika'， 2）， （'Mallika'， 'Yash'）， （2， 1）， （2， 'Mallika'）， （2， 'Yash'）， （'Yash'， 1）， （'Yash'， 'Mallika'）， （'Yash'， 2）]

**方法 1:** 使用简单循环

我们可以使用两个循环遍历列表索引来访问列表的所有组合。如果两个索引计数器都在同一个索引值上，我们跳过它，否则我们按顺序打印索引 I 处的元素和索引 j 处的元素。

这个方法的时间复杂度是 O(n <sup>2</sup> )，因为我们需要两个循环来迭代列表。

## 蟒蛇 3

```
# declaring a list
lst = [1,"Mallika",2,"Yash"]

# output
output = []

# looping over list
for i in range(0,len(lst)):
    for j in range(0,len(lst)):

        # checking if i and j indexes are not on same element
        if (i!=j):

            # add to output
            output.append((lst[i],lst[j]))

# view output
print(output)
```

**输出:**

> [（1， 'Mallika'）， （1， 2）， （1， 'Yash'）， （'Mallika'， 1）， （'Mallika'， 2）， （'Mallika'， 'Yash'）， （2， 1）， （'Mallika'）， （'Yash'）， （'Yash'， 1）， （'Yash'， 'Mallika'）， （'Yash'， 2）]

**方法 2:** 使用[迭代工具](https://www.geeksforgeeks.org/python-itertools/)

Python 提供对 **itertools** 标准库的支持，该标准库用于创建迭代器以实现高效循环。该库支持各种迭代、分组、排序等。这个库的置换()函数用于遍历元素列表的所有可能的顺序，没有任何重复。置换()函数具有以下语法:

```
itertools.permutations(lst,r)
```

其中 r 表示 r 长度的元组，即 2 表示一对，3 表示一个三元组。第一个参数是指定的列表。

该函数返回形成排列后返回的元素组列表。输出包含 n x (n-1)个元素，其中 n 是列表的大小，因为每个元素随后都与所有其他元素相乘。计算排列所需的时间大约是列表大小的指数级。

## 蟒蛇 3

```
# importing required library
import itertools

# creating a list of elements belonging to integers and strings
lst = [1, "Mallika", 2, "Yash"]

# simulating permutations of the list in a group of 2
pair_order_list = itertools.permutations(lst, 2)

# printing the elements belonging to permutations
print(list(pair_order_list))
```

**输出:**

> [（1， 'Mallika'）， （1， 2）， （1， 'Yash'）， （'Mallika'， 1）， （'Mallika'， 2）， （'Mallika'， 'Yash'）， （2， 1）， （'Mallika'）， （'Yash'）， （'Yash'， 1）， （'Yash'， 'Mallika'）， （'Yash'， 2）]

**注:**

*   这些对按照列表中元素到达的顺序打印。
*   对于所有相同的元素，该方法仍然继续形成对并返回它们，即使它们是重复的。

## 蟒蛇 3

```
# importing required ibrary
import itertools

# declaring a list
lst = [2,2,2]

# creating a list of pairs of the list
ordered_list = itertools.permutations(lst,2)

# looping over the elements belonging to the
# pair of permutations
for i in ordered_list:

    # printing ith element
    print(i)
```

**输出**:

```
(2, 2)
(2, 2)
(2, 2)
(2, 2)
(2, 2)
(2, 2)
```

### 查找所有唯一对(唯一性)

然而，排列的方法并不区分(a，b)和(b，a)对，而是将它们都返回。itertools 库还支持 combinations()方法，该方法打印(a，b)或(b，a)对，而不是两者都打印。元素的输出数量相当于(n-1)！其中 n 是列表的长度。计算组合所需的时间大致是多项式的。

**示例:**

> **输入:**【1，“Mallika”，2，“Yash”】
> 
> **输出：** [（1， 'Mallika'）， （1， 2）， （1， 'Yash'）， （'Mallika'， 2）， （'Mallika'， 'Yash'）， （2， 'Yash'）]

## 蟒蛇 3

```
# importing required library
import itertools

# creating a list of elements belonging 

3 to integers and strings
lst = [1,"Mallika",2,"Yash"]

# simulating permutations of the list in 
# a group of 2
pair_order_list = itertools.combinations(lst,2)

# printing the elements belonging to permutations
print (list(pair_order_list))
```

**输出:**

> [（1， 'Mallika'）， （1， 2）， （1， 'Yash'）， （'Mallika'， 2）， （'Mallika'， 'Yash'）， （2， 'Yash'）]