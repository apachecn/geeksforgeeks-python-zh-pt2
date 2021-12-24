# Python–测试字典的布尔值

> 原文:[https://www . geesforgeks . org/python-test-boolean-value-of-dictionary/](https://www.geeksforgeeks.org/python-test-boolean-value-of-dictionary/)

有时，在处理数据时，我们会遇到一个问题，即我们需要根据字典的真实值来接受或拒绝字典，即所有的键都是布尔真或假。这类问题在数据预处理领域有可能得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是解决这个问题的蛮力方法。在这种情况下，我们对每个键进行迭代，如果发现第一次出现假值并从循环中断开，就将其标记为假。

```
# Python3 code to demonstrate working of 
# Test Boolean Value of Dictionary
# Using loop

# initializing dictionary
test_dict = {'gfg' : True, 'is' : False, 'best' : True}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Test Boolean Value of Dictionary
# Using loop
res = True 
for ele in test_dict:
    if not test_dict[ele]:
        res = False 
        break

# printing result 
print("Is Dictionary True ? : " + str(res)) 
```

**Output :**

> 原词典是:{'is': False，' best': True，' gfg': True}
> 词典是真的吗？:假