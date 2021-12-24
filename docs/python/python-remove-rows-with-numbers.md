# Python–删除带有数字的行

> 原文:[https://www . geesforgeks . org/python-remove-row-with-numbers/](https://www.geeksforgeeks.org/python-remove-rows-with-numbers/)

给定一个矩阵，用整数实例删除行。

> **输入** : test_list = [[4，' Gfg '，' best']，['gfg '，5，' is '，' best']，[3，5]，['GFG '，' Best']]
> **输出**:[' GFG '，' Best ']
> **解释**:所有带数字的行都去掉。
> 
> **输入** : test_list = [[4，' Gfg '，' best']，['gfg '，5，' is '，' best']，[3，5]，['GFG '，' best '，1]]
> **输出** : []
> **解释**:删除所有带数字的行。没有名单了。

**方法一:使用任意()+列表理解**

在本文中，我们使用任意行中的 *any()* 来检查任意整数元素，并使用列表理解来执行迭代任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove rows with Numbers
# Using list comprehension + any

# initializing lists
test_list = [[4, 'Gfg', 'best'], [
    'gfg', 'is', 'best'], [3, 5], ['GFG', 'Best']]

# printing original lists
print("The original list is : " + str(test_list))

# using isinstance to check for integer and not include them
res = [sub for sub in test_list if not any(
    isinstance(ele, int) for ele in sub)]

# printing result
print("The filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，' Gfg '，' best']，['gfg '，' is '，' best']，[3，5]，['GFG '，' Best']]
> 筛选的行:['gfg '，' is '，' Best']，['GFG '，' Best']]

**方法 2:使用过滤器()+ lambda + any()**

在本例中，我们使用*λ*和*过滤器()*执行过滤任务，其中 *any()* 的使用方式与上述方法类似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Remove rows with Numbers
# Using filter() + lambda + any()

# initializing lists
test_list = [[4, 'Gfg', 'best'], [
    'gfg', 'is', 'best'], [3, 5], ['GFG', 'Best']]

# printing original lists
print("The original list is : " + str(test_list))

# using isinstance to check for integer and not include them
# filter() used to filter with lambda fnc.
res = list(filter(lambda sub: not any(isinstance(ele, int)
                                      for ele in sub), test_list))

# printing result
print("The filtered rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，' Gfg '，' best']，['gfg '，' is '，' best']，[3，5]，['GFG '，' Best']]
> 筛选的行:['gfg '，' is '，' Best']，['GFG '，' Best']]