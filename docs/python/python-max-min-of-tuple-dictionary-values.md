# Python |元组字典值的最大/最小值

> 原文:[https://www . geesforgeks . org/python-max-min-of-tuple-dictionary-values/](https://www.geeksforgeeks.org/python-max-min-of-tuple-dictionary-values/)

有时，在处理数据时，我们会遇到一个问题，即我们需要找到作为字典值接收的元组元素的最小值/最大值。我们可能在获取索引最小值/最大值时遇到问题。让我们讨论一下解决这个特殊问题的某些方法。

**方法#1:使用`tuple() + min()/max() + zip() + values()`**
上述方法的组合可用于执行该特定任务。在这种情况下，我们只需使用`zip()`将`values()`提取的等价索引值压缩在一起。然后使用各自的函数找到最小值/最大值。最后，结果作为元组以索引方式的最大/最小值返回。

```py
# Python3 code to demonstrate working of
# Max / Min of tuple dictionary values
# Using tuple() + min()/max() + zip() + values()

# Initializing dictionary
test_dict = {'gfg' : (5, 6, 1), 'is' : (8, 3, 2), 'best' : (1, 4, 9)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Max / Min of tuple dictionary values
# Using tuple() + min()/max() + zip() + values()
res = tuple(max(x) for x in zip(*test_dict.values()))

# printing result
print("The maximum values from each index is : " + str(res))
```

**Output :**

```py
The original dictionary is : {'is': (8, 3, 2), 'gfg': (5, 6, 1), 'best': (1, 4, 9)}
The maximum values from each index is : (8, 6, 9)

```