# Python |字典值中的类型转换

> 原文:[https://www . geesforgeks . org/python-type-conversion-in-dictionary-values/](https://www.geeksforgeeks.org/python-type-conversion-in-dictionary-values/)

传统类型转换的问题很常见，可以使用 python 库的内置转换器轻松解决。但是有时候，在更复杂的 vis 场景中，我们可能需要相同的功能。字典列表的关键字。让我们讨论一下实现这一点的某些方法。
**方法#1:天真方法**
在天真方法中，我们采用 2 个循环，嵌套。一个用于列表中的所有字典，第二个用于特定字典中的字典键值对。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Type conversion in list of dicts.
# using naive method

# initializing list of dictionary
test_list = [{'a' : '1', 'b' : '2'}, { 'c' : '3', 'd' : '4'}]

# printing original list
print ("The original list is : " + str(test_list))

# using naive method
# type conversation in list of dicts.
for dicts in test_list:
    for keys in dicts:
        dicts[keys] = int(dicts[keys])

# printing result
print ("The modified converted list is : " +  str(test_list))
```

**输出:**

```py
The original list is : [{'a': '1', 'b': '2'}, {'c': '3', 'd': '4'}]
The modified converted list is : [{'a': 1, 'b': 2}, {'c': 3, 'd': 4}]
```

**方法 2:使用 items() +列表理解**
借助列表理解，只需一行就可以轻松完成。可以利用 items 函数在需要时提取列表值，列表理解部分处理迭代部分。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# Type conversion in list of dicts.
# using items() + list comprehension

# initializing list of dictionary
test_list = [{'a' : '1', 'b' : '2'}, { 'c' : '3', 'd' : '4'}]

# printing original list
print ("The original list is : " + str(test_list))

# using items() + list comprehension
# type conversation in list of dicts.
res = [dict([key, int(value)]
       for key, value in dicts.items())
       for dicts in test_list]

# printing result
print ("The modified converted list is : " +  str(res))
```

**输出:**

```py
The original list is : [{'b': '2', 'a': '1'}, {'c': '3', 'd': '4'}]
The modified converted list is : [{'a': 1, 'b': 2}, {'c': 3, 'd': 4}]
```