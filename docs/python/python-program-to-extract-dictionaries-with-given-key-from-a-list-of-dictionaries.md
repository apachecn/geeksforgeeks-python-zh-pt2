# Python 程序，用于从字典列表中提取具有给定关键字的字典

> 原文:[https://www . geesforgeks . org/python-程序-从字典列表中提取具有给定关键字的字典/](https://www.geeksforgeeks.org/python-program-to-extract-dictionaries-with-given-key-from-a-list-of-dictionaries/)

给定一个字典列表，任务是编写一个 python 程序，只提取那些包含特定给定键值的字典。

> **输入** : test_list = [{'gfg' : 2，' is' : 8，' good' : 3}，{'gfg' : 1，' for' : 10，' geeks' : 9}，{'love' : 3}]，key = " ' gfg "
> **输出** : [{'gfg': 2，' is': 8，' good': 3}，{'gfg' : 1，' for' : 10，' geeks' : 9}]
> **解释** : gfg 在前两部词典中均有，故
> 
> **输入** : test_list = [{'gfg' : 2，' is' : 8，' good' : 3}、{'gfg' : 1，' for' : 10、' geeks' : 9}、{'love' : 3、' gfg ':4 }]、key =“good”
> **输出** : [{'gfg': 2、' is': 8、' good': 3}]
> **解释** : good 存在于第一字典中，故提取。

**方法一:** *使用* [*列表理解*](https://www.geeksforgeeks.org/python-list-comprehension/#:~:text=List%20comprehensions%20are%20used%20for,to%20iterate%20over%20each%20element.) *和* [*键()*](https://www.geeksforgeeks.org/python-dictionary-keys-method/)

在本例中，我们使用操作符中的**测试键的存在，使用键()提取键。列表理解用于迭代不同的字典。**

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Dictionaries with given Key
# Using list comprehension + keys()

# initializing list
test_list = [{'gfg': 2, 'is': 8, 'good': 3},
             {'gfg': 1, 'for': 10, 'geeks': 9},
             {'love': 3}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key
key = 'gfg'

# checking for key using in operator
# keys() used to get keys
res = [sub for sub in test_list if key in list(sub.keys())]

# printing result
print("The filtered Dictionaries : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 2，' is': 8，' good': 3}，{'gfg': 1，' for': 10，' geeks': 9}，{'love': 3}]
> 
> 筛选后的词典:[{“gfg”:2，“is”:8，“good”:3 }，{“gfg”:1，“for”:10，“极客”:9}]

**方法二:** *使用* [*滤镜()*](https://www.geeksforgeeks.org/filter-in-python/) *和*[*λ*](https://www.geeksforgeeks.org/python-lambda/)

在本例中，我们使用 filter()执行过滤任务，lambda 函数用于将逻辑注入到过滤中。操作器中的**用于检查特定按键的存在。**

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Dictionaries with given Key
# Using filter() + lambda

# initializing list
test_list = [{'gfg': 2, 'is': 8, 'good': 3},
             {'gfg': 1, 'for': 10, 'geeks': 9},
             {'love': 3, 'gfg': 4}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key
key = 'good'

# checking for key using in operator
# keys() used to get keys
# filter() + lambda used to perform fileration
res = list(filter(lambda sub: key in list(sub.keys()), test_list))

# printing result
print("The filtered Dictionaries : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 2，' is': 8，' good': 3}，{'gfg': 1，' for': 10，' geeks': 9}，{'love': 3，' gfg': 4}]
> 
> 筛选的词典:[{“gfg”:2，“is”:8，“good”:3 }]