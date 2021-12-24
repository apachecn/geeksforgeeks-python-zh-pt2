# Python–字典中有多个相似值的对

> 原文:[https://www . geesforgeks . org/python-字典中有多个相似值的对/](https://www.geeksforgeeks.org/python-pairs-with-multiple-similar-values-in-dictionary/)

有时候，在使用字典时，我们会遇到一个问题，那就是我们需要将具有相似键值的字典保存在其他字典中。这是一个非常具体的问题。这可以在 web 开发领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这个任务可以使用列表理解来执行。在这种情况下，我们迭代列表中的每个元素，并运行嵌套循环来匹配键的值和其他值。

```py
# Python3 code to demonstrate 
# Pairs with multiple similar values in dictionary
# using list comprehension

# Initializing list
test_list = [{'Gfg' : 1, 'is' : 2}, {'Gfg' : 2, 'is' : 2}, {'Gfg' : 1, 'is' : 2}]

# printing original list
print("The original list is : " + str(test_list))

# Pairs with multiple similar values in dictionary
# using list comprehension
res = [sub for sub in test_list if len([ele for ele in test_list if ele['Gfg'] == sub['Gfg']]) > 1]

# printing result 
print ("List after keeping dictionary with same key's value : " + str(res))
```

**Output :**

```py
The original list is : [{'is': 2, 'Gfg': 1}, {'is': 2, 'Gfg': 2}, {'is': 2, 'Gfg': 1}]
List after keeping dictionary with same key's value : [{'is': 2, 'Gfg': 1}, {'is': 2, 'Gfg': 1}]

```