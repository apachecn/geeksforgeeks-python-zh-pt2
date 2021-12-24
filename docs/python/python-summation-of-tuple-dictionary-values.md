# Python–元组字典值的总和

> 原文:[https://www . geesforgeks . org/python-元组求和-字典-值/](https://www.geeksforgeeks.org/python-summation-of-tuple-dictionary-values/)

有时，在处理数据时，我们会遇到一个问题，即我们需要找到作为字典值接收的元组元素的总和。我们可能难以得到指数求和。让我们讨论一下解决这个特殊问题的某些方法。

**方法#1:使用`tuple() + sum() + zip() + values()`**
上述方法的组合可用于执行该特定任务。在这种情况下，我们只需使用 zip()将 values()提取的等价索引值压缩在一起。然后用各自的函数求求和。最后，结果以元组的形式作为索引求和返回。

```py
# Python3 code to demonstrate working of
# Summation of tuple dictionary values
# Using tuple() + sum() + zip() + values()

# Initializing dictionary
test_dict = {'gfg' : (5, 6, 1), 'is' : (8, 3, 2), 'best' : (1, 4, 9)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Summation of tuple dictionary values
# Using tuple() + sum() + zip() + values()
res = tuple(sum(x) for x in zip(*test_dict.values()))

# printing result
print("The summation from each index is : " + str(res))
```

**Output :**

```py
The original dictionary is : {'is': (8, 3, 2), 'best': (1, 4, 9), 'gfg': (5, 6, 1)}
The summation from each index is : (14, 13, 12)

```