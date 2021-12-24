# Python–按因子计数排序

> 原文:[https://www.geeksforgeeks.org/python-sort-by-factor-count/](https://www.geeksforgeeks.org/python-sort-by-factor-count/)

给定元素列表，按每个元素的因子计数排序。

> **输入**:test _ list =【12，100，22】
> **输出**:【22，12，100】
> **解释**:元素分别为 3，5，8 个因子。
> 
> **输入**:test _ list =【6，11】
> **输出**:【11，6】
> **解释**:元素分别为 1，4 个因子。

**方法一:使用 sort() + len() +列表理解**

在这种情况下，我们使用 *sort()* 和 *len()* 执行排序任务，列表理解用于获取因子计数的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort by Factor count
# Using sort() + len() + list comprehension

def factor_count(ele):

    # getting factors count
    return len([ele for idx in range(1, ele) if ele % idx == 0])

# initializing list
test_list = [12, 100, 360, 22, 200]

# printing original list
print("The original list is : " + str(test_list))

# performing sort
test_list.sort(key=factor_count)

# printing result
print("Sorted List : " + str(test_list))
```

**输出:**

```
The original list is : [12, 100, 360, 22, 200]
Sorted List : [22, 12, 100, 200, 360]

```

**方法 2:使用 lambda + sorted() + len()**

在这种情况下，排序任务是使用 *sorted()* 完成的，lambda 函数用于馈送到 sorted 以获取因子。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Sort by Factor count
# Using lambda + sorted() + len()

# initializing list
test_list = [12, 100, 360, 22, 200]

# printing original list
print("The original list is : " + str(test_list))

# performing sort using sorted(), lambda getting factors
res = sorted(test_list, key=lambda ele: len(
    [ele for idx in range(1, ele) if ele % idx == 0]))

# printing result
print("Sorted List : " + str(res))
```

**输出:**

```
The original list is : [12, 100, 360, 22, 200]
Sorted List : [22, 12, 100, 200, 360] 

```