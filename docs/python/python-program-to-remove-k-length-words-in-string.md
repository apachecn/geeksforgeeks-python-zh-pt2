# Python 程序删除字符串中的 K 长度单词

> 原文:[https://www . geesforgeks . org/python-program-to-remove-k-length-in-words-in-string/](https://www.geeksforgeeks.org/python-program-to-remove-k-length-words-in-string/)

给定一个字符串，编写一个 Python 程序删除所有长度为 K 的单词。

**示例:**

> **输入** : test_str = 'Gfg 最适合所有极客'，K = 3
> **输出**:最适合极客
> **解释** : Gfg，for 和 all 长度均为 3，因此移除。
> 
> **输入** : test_str = 'Gfg 最适合所有极客'，K = 2
> **输出** : Gfg 最适合所有极客
> **解释**:长度为 2，因此删除。

**方法#1:使用** [**拆分()**](https://www.geeksforgeeks.org/python-string-split/) **+** [**连接()**](https://www.geeksforgeeks.org/join-function-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)**+**[T21】len()](https://www.geeksforgeeks.org/python-string-length-len/)

在这种情况下，使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 分割每个单词，然后使用 [len()](https://www.geeksforgeeks.org/python-string-length-len/) 检查长度，然后省略匹配的 k。最后连接单词。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove K length words in String
# Using split() + join() + list comprehension + len()

# initializing string
test_str = 'Gfg is best for all geeks'

# printing original string
print("The original string is : " + (test_str))

# initializing K
K = 3

# getting splits
temp = test_str.split()

# omitting K lengths
res = [ele for ele in temp if len(ele) != K]

# joining result
res = ' '.join(res)

# printing result
print("Modified String : " + (res))
```

**输出:**

```
The original string is : Gfg is best for all geeks
Modified String : is best geeks
```

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)**+**[**分裂()**](https://www.geeksforgeeks.org/python-string-split/)T18】+[T21】len()](https://www.geeksforgeeks.org/python-string-length-len/)**+**[加入()](https://www.geeksforgeeks.org/join-function-python/)

在本例中，我们使用 filter() + lamnda 执行过滤任务，其余所有功能与上述方法相似。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Remove K length words in String
# Using filter() + lambda + split() + len() + join()

# initializing string
test_str = 'Gfg is best for all geeks'

# printing original string
print("The original string is : " + (test_str))

# initializing K
K = 3

# getting splits
temp = test_str.split()

# omitting K lengths
# filtering using filter() and lambda
res = list(filter(lambda ele: len(ele) != K, temp))

# joining result
res = ' '.join(res)

# printing result
print("Modified String : " + (res))
```

**输出:**

```
The original string is : Gfg is best for all geeks
Modified String : is best geeks
```