# Python |词典项的类型转换

> 原文:[https://www . geesforgeks . org/python-type-转换词典-items/](https://www.geeksforgeeks.org/python-type-conversion-of-dictionary-items/)

数据类型的相互转换很常见，我们在使用字典时也可能会遇到这个问题。我们可能有一个键和对应的数字字母列表，我们需要将整个字典转换成整数，而不是字符串数字。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这个问题可以通过使用循环使用天真的方法来解决。在这种情况下，我们对每个键和值进行循环，然后分别对键和值进行类型转换，并返回所需的整数容器。

```py
# Python3 code to demonstrate working of
# Type conversion of dictionary items
# Using loop

# Initialize dictionary
test_dict = {'1' : ['4', '5'], '4' : ['6', '7'], '10' : ['8']}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using loop
# Type conversion of dictionary items
res = {}
for key, value in test_dict.items():
    res[int(key)] = [int(item) for item in value]

# printing result 
print("Dictionary after type conversion : " + str(res))
```

**Output :**

> 原始字典:{'10': ['8']，' 4': ['6 '，' 7']，' 1': ['4 '，' 5']}
> 类型转换后的字典:{1: [4，5]，10: [8]，4: [6，7]}