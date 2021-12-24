# Python–从字典值中设置

> 原文:[https://www . geesforgeks . org/python-从字典中设置-值/](https://www.geeksforgeeks.org/python-set-from-dictionary-values/)

给定一个字典，任务是编写一个 Python 程序来获取所有的值并转换为 set。

**示例:**

> **输入:** test_dict = {'Gfg' : 4，' is' : 3，' best' : 7，' for' : 3，' geek' : 4}
> 
> **输出:** {3，4，7}
> 
> **说明:**3 的第 2 次出现在转化阶段被去除。
> 
> **输入:** test_dict = {'Gfg' : 4，' is' : 3，' best' : 7，' geek' : 4}
> 
> **输出:** {3，4，7}
> 
> **说明:**第 2 次出现的 4 在相变阶段被去除。

**方法#1:使用生成器表达式+ {}**

在本例中，我们使用生成器表达式执行获取所有值的任务，而{}运算符执行移除重复元素和转换为 set 的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Set from dictionary values
# Using generator expression + {}

# initializing dictionary
test_dict = {'Gfg': 4, 'is': 3, 'best': 7, 'for': 3, 'geek': 4}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# {} converting to set
res = {test_dict[sub] for sub in test_dict}

# printing result
print("The converted set : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 4，' is': 3，' best': 7，' for': 3，' geek': 4}
> 
> 转换后的集合:{3，4，7}

**方法 2:使用** [**值()**](https://www.geeksforgeeks.org/python-dictionary-values/) **+** [**设置()**](https://www.geeksforgeeks.org/python-set-method/)

在本例中，我们使用 values()执行从字典中获取值的任务，set()用于转换为 set。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Set from dictionary values
# Using values() + set()

# initializing dictionary
test_dict = {'Gfg': 4, 'is': 3, 'best': 7, 'for': 3, 'geek': 4}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# values() used to get values
res = set(test_dict.values())

# printing result
print("The converted set : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 4，' is': 3，' best': 7，' for': 3，' geek': 4}
> 
> 转换后的集合:{3，4，7}