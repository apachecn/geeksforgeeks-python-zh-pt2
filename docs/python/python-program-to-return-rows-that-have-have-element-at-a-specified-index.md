# Python 程序返回在指定索引处有元素的行

> 原文:[https://www . geeksforgeeks . org/python-程序返回指定索引处有元素的行/](https://www.geeksforgeeks.org/python-program-to-return-rows-that-have-have-element-at-a-specified-index/)

给定两个矩阵，任务是编写一个 Python 程序，该程序可以从两个矩阵中提取在其第 k 个索引处具有相似元素的所有行，这些行映射在相似的行位置。

**示例:**

> **输入:** test_list1 = [[1，8，3]，[9，2，0]，[6，4，4]，[6，4，4]]，test_list2 = [[1，9，3]，[8，2，3]，[5，4，6]，[5，4，6]]，K = 1
> 
> **输出:** [[9，2，0]，[8，2，3]，[6，4，4]，[5，4，6]，[6，4，4]，[5，4，6]]
> 
> **说明:**提取第 1 个指标元素相似的所有元素。
> 
> **输入:** test_list1 = [[1，8，3]，[9，2，0]，[6，4，4]，[6，5，4]]，test_list2 = [[1，9，3]，[8，2，3]，[5，4，6]，[5，4，6]]，K = 1
> 
> **输出:** [[9，2，0]，[8，2，3]，[6，4，4]，[5，4，6]]
> 
> **说明:**提取第 1 个指标元素相似的所有元素。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，列表从开始行迭代到结束行，并且每一行的 Kth 索引都匹配，如果找到的话，两行都追加到结果中。

**示例:**

## 蟒蛇 3

```
# initializing lists
test_list1 = [[1, 8, 3], [9, 2, 0], [6, 4, 4], [6, 4, 4]]
test_list2 = [[1, 9, 3], [8, 2, 3], [5, 4, 6], [5, 4, 6]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 1

res = []
for idx in range(len(test_list1)):

    # comparing lists
    if test_list1[idx][K] == test_list2[idx][K]:
        res.append(test_list1[idx])
        res.append(test_list2[idx])

# printing result
print("K index matching rows : " + str(res))
```

**输出:**

> 原始列表 1 是:[[1，8，3]，[9，2，0]，[6，4，4]，[6，4，4]]
> 
> 原始列表 2 是:[[1，9，3]，[8，2，3]，[5，4，6]，[5，4，6]]
> 
> k 个索引匹配行:[[9，2，0]，[8，2，3]，[6，4，4]，[5，4，6]，[6，4，4]，[5，4，6]]

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/) *和* [*zip()*](https://www.geeksforgeeks.org/zip-in-python/)

在本例中，我们使用 zip()执行获取配对的任务，然后比较 Kth 元素，使用 extend()和列表理解进行追加和迭代。

**示例:**

## 蟒蛇 3

```
# initializing lists
test_list1 = [[1, 8, 3], [9, 2, 0], [6, 4, 4], [6, 4, 4]]
test_list2 = [[1, 9, 3], [8, 2, 3], [5, 4, 6], [5, 4, 6]]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# initializing K
K = 1

# zip() combines elements together
res = []
[res.extend([t1, t2])
 for t1, t2 in zip(test_list1, test_list2) if t1[K] == t2[K]]

# printing result
print("K index matching rows : " + str(res))
```

**输出:**

> 原始列表 1 是:[[1，8，3]，[9，2，0]，[6，4，4]，[6，4，4]]
> 
> 原始列表 2 是:[[1，9，3]，[8，2，3]，[5，4，6]，[5，4，6]]
> 
> k 个索引匹配行:[[9，2，0]，[8，2，3]，[6，4，4]，[5，4，6]，[6，4，4]，[5，4，6]]