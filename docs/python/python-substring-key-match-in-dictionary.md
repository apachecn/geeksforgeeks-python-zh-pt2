# Python |字典中的子串关键字匹配

> 原文:[https://www . geesforgeks . org/python-substring-key-match-in-dictionary/](https://www.geeksforgeeks.org/python-substring-key-match-in-dictionary/)

有时，在使用字典时，我们可能会遇到这样的用例:我们不知道我们需要的确切的键，而只知道我们需要获取的键的特定部分。这种问题可能会在许多应用中出现。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`items()` +列表理解**
上述方法的组合可以用来执行这个特定的任务，在这个任务中，我们只是使用 items 函数访问键值对，列表理解有助于迭代和访问逻辑。

```
# Python3 code to demonstrate working of
# Substring Key match in dictionary
# Using items() + list comprehension

# initializing dictionary
test_dict = {'All' : 1, 'have' : 2, 'good' : 3, 'food' : 4}

# initializing search key string
search_key = 'ood'

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Using items() + list comprehension
# Substring Key match in dictionary
res = [val for key, val in test_dict.items() if search_key in key]

# printing result 
print("Values for substring keys : " + str(res))
```

**Output :**

```
The original dictionary is : {'All': 1, 'food': 4, 'have': 2, 'good': 3}
Values for substring keys : [4, 3]

```