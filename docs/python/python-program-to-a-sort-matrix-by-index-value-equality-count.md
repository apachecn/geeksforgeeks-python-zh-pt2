# 通过索引值相等计数将 Python 编程为排序矩阵

> 原文:[https://www . geeksforgeeks . org/python-程序-按索引排序-矩阵-值-相等-计数/](https://www.geeksforgeeks.org/python-program-to-a-sort-matrix-by-index-value-equality-count/)

给定一个矩阵，任务是编写一个 Python 程序，该程序可以根据等于其索引号的值的数量对其行或列进行排序。对于每一行或每一列，计算索引号与值相等的次数。计算每行或每列的计数后，根据步骤 1 中为每行或每列提取的计数对矩阵进行排序。

> **输入** : test_list = [[3，1，2，5，4]，[0，1，2，3，4]，[6，5，4，3，2]，[0，5，4，2]]
> **输出** : [[6，5，4，3，2]，[0，5，4，2]，[3，1，2，5，4]，[0，1，2，3，4]]
> **解释** : 02 等于它在第二个列表中的索引位置。
> 
> **输入** : test_list = [[0，1，2，3，4]，[6，5，4，3，2]，[0，5，4，2]]
> ]**输出** : [[6，5，4，3，2]，[0，5，4，2]，[0，1，2，3，4]]
> **解释** : 0 < 2 < 5 为索引元素相等计数排序。最后一个列表中的所有元素都等于其索引，因此返回计数。

### 对行进行排序

**方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/)*[*len()*](https://www.geeksforgeeks.org/python-string-length-len/#:~:text=len()%20function%20is%20an,the%20length%20of%20the%20string.&text=Parameters%3A,takes%20string%20as%20the%20parameter.)*和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)*

*在这种情况下，我们通过比较枚举组件来检查索引和元素的相等性，结果的求和是通过提取列表的长度来完成的。这作为关键字传递给执行就地排序的 sort()。*

***示例:***

## *蟒蛇 3*

```py
*# Python3 code to demonstrate working of
# Sort Matrix by index-value equality count
# Using sort() + len() + enumerate()

def get_idx_ele_count(row):

    # getting required count
    # element and index compared, if equal added
    # in list, length computed using len()
    return len([ele for idx, ele in enumerate(row) if ele == idx])

# initializing list
test_list = [[3, 1, 2, 5, 4], [0, 1, 2, 3, 4], 
             [6, 5, 4, 3, 2], [0, 5, 4, 2]]

# printing original list
print("The original list is : " + str(test_list))

# inplace sorting using sort()
test_list.sort(key=get_idx_ele_count)

# printing result
print("Sorted List : " + str(test_list))*
```

***输出:***

> *原始列表为:[[3，1，2，5，4]，[0，1，2，3，4]，[6，5，4，3，2]，[0，5，4，2]]*
> 
> *排序列表:[[6，5，4，3，2]，[0，5，4，2]，[3，1，2，5，4]，[0，1，2，3，4]]*

***方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/#:~:text=This%20function%20can%20have%20any,restricted%20to%20a%20single%20expression.)*[*len()*](https://www.geeksforgeeks.org/python-string-length-len/#:~:text=len()%20function%20is%20an,the%20length%20of%20the%20string.&text=Parameters%3A,takes%20string%20as%20the%20parameter.)*和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)***

**在本文中，我们使用 sorted()执行排序任务，lambda 函数提供了与 len()和 enumerate()相结合的排序工具。**

****示例:****

## **蟒蛇 3**

```py
**# Python3 code to demonstrate working of
# Sort Matrix by index-value equality count
# Using sorted() + lambda + len() + enumerate()

# initializing list
test_list = [[3, 1, 2, 5], [0, 1, 2, 3], 
             [6, 5, 4, 3], [0, 5, 4, 2]]

# printing original list
print("The original list is : " + str(test_list))

# sorting using sorted()
# utility injection using lambda
# element and index compared, if equal added in list,
# length computed using len()
res = sorted(test_list, key=lambda row: len(
    [ele for idx, ele in enumerate(row) if ele == idx]))

# printing result
print("Sorted List : " + str(res))**
```

****输出:****

> **原始列表为:[[3，1，2，5]，[0，1，2，3]，[6，5，4，3]，[0，5，4，2]]**
> 
> **排序列表:[[6，5，4，3]，[0，5，4，2]，[3，1，2，5]，[0，1，2，3]]**

### **排序列**

****方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/)*[*len()*](https://www.geeksforgeeks.org/python-string-length-len/#:~:text=len()%20function%20is%20an,the%20length%20of%20the%20string.&text=Parameters%3A,takes%20string%20as%20the%20parameter.)*和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)***

**在这种情况下，我们执行基矩阵的转置，然后使用上述方法 1 执行获取索引值相等计数的常规任务，排序后，矩阵再次转换为其转置格式。**

****例:**** 

## **蟒蛇 3**

```py
**# Python3 code to demonstrate working of
# Sort Matrix by index-value equality count
# Using sort() + len() + enumerate()

def get_idx_ele_count(row):

    # getting required count
    # element and index compared, if equal added in 
    # list, length computed using len()
    return len([ele for idx, ele in enumerate(row) if ele == idx])

# initializing list
test_list = [[3, 1, 2, 5], [0, 1, 2, 3], 
             [6, 5, 4, 3], [0, 5, 4, 2]]

# printing original list
print("The original list is : " + str(test_list))

# transposing matrix
test_list = list(zip(*test_list))

# inplace sorting using sort()
test_list.sort(key=get_idx_ele_count)

# performing transpose again to get result.
test_list = zip(*test_list)

# converting list of tuples to list of lists
res = [list(sub) for sub in test_list]

# printing result
print("Sorted List : " + str(res))**
```

****输出:****

> **原始列表为:[[3，1，2，5]，[0，1，2，3]，[6，5，4，3]，[0，5，4，2]]**
> 
> **排序列表:[[3，2，5，1]，[0，2，3，1]，[6，4，3，5]，[0，4，2，5]]**

****方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/#:~:text=This%20function%20can%20have%20any,restricted%20to%20a%20single%20expression.)*[*len()*](https://www.geeksforgeeks.org/python-string-length-len/#:~:text=len()%20function%20is%20an,the%20length%20of%20the%20string.&text=Parameters%3A,takes%20string%20as%20the%20parameter.)*和* [*枚举()*](https://www.geeksforgeeks.org/enumerate-in-python/#:~:text=Enumerate()%20method%20adds%20a,tuples%20using%20list()%20method.)****

**在这种情况下，我们执行基矩阵的转置，然后使用上述方法 2 执行获取索引值相等计数的常规任务，排序后，矩阵再次转换为其转置格式。**

****示例:****

## **蟒蛇 3**

```py
**# Python3 code to demonstrate working of
# Sort Matrix by index-value equality count
# Using sorted() + lambda + len() + enumerate()

# initializing list
test_list = [[3, 1, 2, 5], [0, 1, 2, 3],
             [6, 5, 4, 3], [0, 5, 4, 2]]

# printing original list
print("The original list is : " + str(test_list))

# transposing matrix
test_list = zip(*test_list)

# sorting using sorted()
# utility injection using lambda
# element and index compared, if equal added in
# list, length computed using len()
res = sorted(test_list, key=lambda row: len(
    [ele for idx, ele in enumerate(row) if ele == idx]))

# performing transpose again to get result.
res = zip(*res)

# converting list of tuples to list of lists
res = [list(sub) for sub in res]

# printing result
print("Sorted List : " + str(res))**
```

****输出:****

> **原始列表为:[[3，1，2，5]，[0，1，2，3]，[6，5，4，3]，[0，5，4，2]]**
> 
> **排序列表:[[3，2，5，1]，[0，2，3，1]，[6，4，3，5]，[0，4，2，5]]**