# Python |更新字典中的值列表

> 原文:[https://www . geesforgeks . org/python-updating-value-list-in-dictionary/](https://www.geeksforgeeks.org/python-updating-value-list-in-dictionary/)

当使用以列表作为值的字典时，总是容易被更新其值。在这种情况下，执行这项任务的方法或人手不足可能会很方便。这可能发生在 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
执行这个特定任务的天真方法，在这种情况下，我们只是提取密钥，然后在打包列表中以列表综合格式迭代它的值。这就解决了问题。

```
# Python3 code to demonstrate working of
# Updating value list in dictionary
# Using list comprehension

# Initialize dictionary
test_dict = {'gfg' : [1, 5, 6], 'is' : 2, 'best' : 3}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using list comprehension
# Updating value list in dictionary
test_dict['gfg'] = [x * 2 for x in test_dict['gfg']]

# printing result 
print("Dictionary after updation is : " + str(test_dict))
```

**Output :**

> 原词典:{'is': 2，' gfg': [1，5，6]，' best': 3}
> 词典更新后为:{'is': 2，' gfg': [2，10，12]，' best': 3}