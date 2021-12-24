# Python–字典中的元组值乘积

> 原文:[https://www . geesforgeks . org/python-tuple-value-product-in-dictionary/](https://www.geeksforgeeks.org/python-tuple-value-product-in-dictionary/)

有时，在处理数据时，我们会遇到一个问题，即我们需要找到作为字典值接收的元组元素的乘积。我们可能在获取指数型产品时遇到问题。让我们讨论一下解决这个特殊问题的某些方法。

**方法#1:使用`tuple() + loop + zip() + values()`**
上述方法的组合可用于执行该特定任务。在这种情况下，我们只需使用 zip()将由 values()提取的等价索引值压缩在一起。然后使用各自的功能找到产品。最后，结果以元组的形式作为索引乘积返回。

```
# Python3 code to demonstrate working of
# Dictionary Tuple Values Product
# Using tuple() + loop + zip() + values()

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= ele
    return res 

# Initializing dictionary
test_dict = {'gfg' : (5, 6, 1), 'is' : (8, 3, 2), 'best' : (1, 4, 9)}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Dictionary Tuple Values Product
# Using tuple() + loop + zip() + values()
res = tuple(prod(x) for x in zip(*test_dict.values()))

# printing result
print("The product from each index is : " + str(res))
```

**Output :**

```
The original dictionary is : {'gfg': (5, 6, 1), 'is': (8, 3, 2), 'best': (1, 4, 9)}
The product from each index is : (40, 72, 18)

```