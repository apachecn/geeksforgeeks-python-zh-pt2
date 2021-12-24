# Python–在值的大小限制上拆分字典值

> 原文:[https://www . geesforgeks . org/python-split-dictionary-values-on-size-limit-values/](https://www.geeksforgeeks.org/python-split-dictionary-values-on-size-limit-of-values/)

给定一个带有字符串值的字典，任务是编写一个 python 程序，在字符串大小超过 k 时拆分值。

> **输入:** {1:“极客 forgeeks”，2:“最适合”，3:“所有极客”}，限制= 5
> 
> **输出:**{ 1:“Geeks”，2:“forge”，3:“eks”，4:“best”，5:“for”，6:“all g”，7:“eeks”}
> 
> **说明:**所有字符串值都被限制到长度 5。新值是由帖子大小限制创建的。
> 
> **输入:**{ 1:“geeks forgeeks”，2:“最适合”}，限制= 5
> 
> **输出:**{ 1:“Geeks”，2:“forge”，3:“eks”，4:“best”，5:“for”
> 
> **说明:**所有字符串值都被限制到长度 5。新值是由帖子大小限制创建的。

**方法:使用** [**字典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/) **+** [**列表切片**](https://www.geeksforgeeks.org/python-list-slicing/)

在本文中，我们使用列表切片和对使用 values()提取的值的迭代的列表理解来执行获取所需值块的任务。下一步是使用列表理解和枚举()为键重新分配新的分块值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Split Dictionary values on size limit
# Using dictionary comprehension + enumerate() +  list slicing

# initializing dictionary
test_dict = {1: "Geeksforgeeks", 
             2: "best for", 3: 
             "all geeks"}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing limit
limit = 4

# cutting chunks of K
chunks = (sub[idx: idx + limit] for sub in test_dict.values()
          for idx in range(0, len(sub), limit))

# re assigning dictionary with chunks
res = {key: val for key, val in enumerate(chunks, 1)}

# printing result
print("The extracted values : " + str(res))
```

**输出:**

> 最初的字典是:{1: 'Geeksforgeeks '，2:'最适合'，3:'所有 geeks'}
> 
> 提取的值:{1:“极客”，2:“稳定”，3:“极客”，4:“s”，5:“最佳”，6:“适合”，7:“全部”，8:“极客”，9:“s”}