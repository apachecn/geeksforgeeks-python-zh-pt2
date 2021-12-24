# Python 程序，通过分片行和列求和对矩阵进行排序

> 原文:[https://www . geeksforgeeks . org/python-程序对矩阵进行逐行逐列排序-求和/](https://www.geeksforgeeks.org/python-program-to-sort-matrix-by-sliced-row-and-column-summation/)

给定一个矩阵和一系列索引，任务是编写一个 python 程序，该程序可以根据每行和每列的仅给定范围的索引之和对矩阵进行排序，即从给定的开始到结束索引对行和列进行分片，此外，矩阵仅使用来自每行或每列的那些分片之和进行排序。

> **输入** : test_list = [[1，4，3，1，3]，[3，4，5，2，4]，[23，5，5，3]，[2，3，5，1，6]]，I，j = 1，3
> **输出** : [[1，4，3，1，3]，[2，3，5，1，6]，[3，4，5，2，4]，[23，5，5，3]] 【T5
> 
> **输入** : test_list = [[1，4，3，1，3]，[23，5，5，3]，[2，3，5，1，6]]，I，j = 1，3
> **输出** : [[1，4，3，1，3]，[2，3，5，1，6]，[23，5，5，3]]
> **解释** : 7 < 8 < 10，为

### 行上求和

**方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/)*[*切片*](https://www.geeksforgeeks.org/python-list-slicing/) *和* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/)*

*在这种情况下，我们使用 sort()执行就地排序任务，使用 sum()执行求和，使用列表切片执行切片操作，这些操作共同构成了排序的关键功能。*

***示例:***

## *蟒蛇 3*

```py
*# get sliced summation
def get_sliced_sum(row):
    return sum(row[i:j])

# initializing list
test_list = [[1, 4, 3, 1, 3], [3, 4, 5, 2, 4],
             [23, 5, 5, 3], [2, 3, 5, 1, 6]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 1, 3

# performing sort
test_list.sort(key=get_sliced_sum)

# printing result
print("Sorted List : " + str(test_list))*
```

***输出:***

> *原来的名单是:[[1，4，3，1，3]，[3，4，5，2，4]，[23，5，5，3]，[2，3，5，1，6]]*
> 
> *排序列表:[[1，4，3，1，3]，[2，3，5，1，6]，[3，4，5，2，4]，[23，5，5，3]]*

***方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*[*求和()*](https://www.geeksforgeeks.org/sum-function-python/) *和* [*切片*](https://www.geeksforgeeks.org/python-list-slicing/)***

**在这种情况下，执行排序的任务是使用 sorted()完成的，lambda 函数用于在没有外部函数调用的情况下，使用一条语句获得切片呈现的总和。**

****示例:****

## **蟒蛇 3**

```py
**# initializing list
test_list = [[1, 4, 3, 1, 3], [3, 4, 5, 2, 4],
             [23, 5, 5, 3], [2, 3, 5, 1, 6]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 1, 3

# performing sort using sorted()
# filter util. using lambda fnc.
res = sorted(test_list, key=lambda row: sum(row[i:j]))

# printing result
print("Sorted List : " + str(res))**
```

****输出:****

> **原来的名单是:[[1，4，3，1，3]，[3，4，5，2，4]，[23，5，5，3]，[2，3，5，1，6]]**
> 
> **排序列表:[[1，4，3，1，3]，[2，3，5，1，6]，[3，4，5，2，4]，[23，5，5，3]]**

### **列上求和**

****方法 1 :** *使用* [*排序()*](https://www.geeksforgeeks.org/sort-in-python/)*[*切片*](https://www.geeksforgeeks.org/python-list-slicing/) *和* [*求和()*](https://www.geeksforgeeks.org/sum-function-python/)***

**在这种情况下，我们执行基本矩阵的转置，然后使用上述方法 1 执行获取切片的通常任务，在排序之后，矩阵再次转换为其转置格式。**

****示例:****

## **蟒蛇 3**

```py
**# get sliced summation
def get_sliced_sum(row):
    return sum(row[i:j])

# initializing list
test_list = [[1, 4, 3, 1], [3, 4, 5, 2],
             [23, 5, 5, 3], [2, 3, 5, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 1, 3

# transposing matrix
test_list = list(zip(*test_list))

# performing sort
test_list.sort(key=get_sliced_sum)

# performing transpose again to get 
# result.
test_list = zip(*test_list)

# converting list of tuples to list of 
# lists
res = [list(sub) for sub in test_list]

# printing result
print("Sorted List Columnwise : " + str(res))**
```

****输出:****

> **原来的名单是:[[1，4，3，1]，[3，4，5，2]，[23，5，5，3]，[2，3，5，1]]**
> 
> **按列排序的列表:[[1，4，3，1]，[2，4，5，3]，[3，5，5，23]，[1，3，5，2]]**

****方法二:** *使用* [*排序()*](https://www.geeksforgeeks.org/sorted-function-python/)*[*λ*](https://www.geeksforgeeks.org/python-lambda/)*[*求和()*](https://www.geeksforgeeks.org/sum-function-python/) *和* [*切片*](https://www.geeksforgeeks.org/python-list-slicing/)****

**在这种情况下，我们执行基本矩阵的转置，然后使用上述方法 2 执行获取切片的通常任务，在排序之后，矩阵再次转换为其转置格式。**

****示例:****

## **蟒蛇 3**

```py
**# initializing list
test_list = [[1, 4, 3, 1], [3, 4, 5, 2], 
             [23, 5, 5, 3], [2, 3, 5, 1]]

# printing original list
print("The original list is : " + str(test_list))

# initializing range
i, j = 1, 3

# transposing matrix
test_list = zip(*test_list)

# performing sort using sorted()
# filter util. using lambda fnc.
res = sorted(test_list, key=lambda row: sum(row[i:j]))

# performing transpose again to get result.
res = zip(*res)

# converting list of tuples to list of lists
res = [list(sub) for sub in res]

# printing result
print("Sorted List Columnwise : " + str(list(res)))**
```

****输出:****

> **原来的名单是:[[1，4，3，1]，[3，4，5，2]，[23，5，5，3]，[2，3，5，1]]**
> 
> **按列排序的列表:[[1，4，3，1]，[2，4，5，3]，[3，5，5，23]，[1，3，5，2]]**