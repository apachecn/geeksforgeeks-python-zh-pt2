# Python–按最大字符串长度排序矩阵

> 原文:[https://www . geesforgeks . org/python-sort-matrix-by-maximum-string-length/](https://www.geeksforgeeks.org/python-sort-matrix-by-maximum-string-length/)

给定一个矩阵，根据其中字符串的最大长度执行行排序。

> **输入** : test_list = [['gfg '，' best']，['geeksforgeeks']，['cs '，' rocks']，['gfg '，' cs']]
> **输出**:[' gfg '，' cs '，' best']，['cs '，' rocks']，[' geeksforgeeks ']
> **解释** : 3 < 4 < 5 < 13、最大长度
> 
> **输入** : test_list = [['gfg '，' best']，['cs '，' rocks']，['gfg '，' cs']]
> **输出**:[' gfg '，' cs '，[gfg '，' best']，['cs '，' rocks ']
> **解释** : 3 < 4 < 5 个最大长度的字符串，排序越来越靠前。

**方法#1:使用 sort()+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**max()**](https://www.geeksforgeeks.org/python-max-function/)

在这种情况下，就地排序是使用 sort()执行的，len()和 max()计算每一行中字符串的最大长度来执行排序。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by Maximum String Length
# Using sort() + len() + max()

def max_len(row):

    # getting Maximum length of string
    return max([len(ele) for ele in row])

# initializing list
test_list = [['gfg', 'best'], ['geeksforgeeks'],
             ['cs', 'rocks'], ['gfg', 'cs']]

# printing original list
print("The original list is : " + str(test_list))

# performing sort()
test_list.sort(key=max_len)

# printing result
print("Sorted Matrix : " + str(test_list))
```

**输出:**

> 原列表为:[['gfg '，' best']，['geeksforgeeks']，['cs '，' rocks']，['gfg '，' cs']]
> 排序矩阵:['gfg '，' cs']，['gfg '，' best']，['cs '，' rocks']，['geeksforgeeks']

**方法 2:使用** [**排序()**](https://www.geeksforgeeks.org/sorted-function-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+max()+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，我们使用 lambda 函数而不是外部函数来执行过滤最大值的任务。使用 sorted()执行排序任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Sort Matrix by Maximum String Length
# Using sorted() + lambda + max() + len()

# initializing list
test_list = [['gfg', 'best'], ['geeksforgeeks'],
             ['cs', 'rocks'], ['gfg', 'cs']]

# printing original list
print("The original list is : " + str(test_list))

# performing logic using lambda fnc.
res = sorted(test_list, key=lambda row: max([len(ele) for ele in row]))

# printing result
print("Sorted Matrix : " + str(res))
```

**输出:**

> 原列表为:[['gfg '，' best']，['geeksforgeeks']，['cs '，' rocks']，['gfg '，' cs']]
> 排序矩阵:['gfg '，' cs']，['gfg '，' best']，['cs '，' rocks']，['geeksforgeeks']