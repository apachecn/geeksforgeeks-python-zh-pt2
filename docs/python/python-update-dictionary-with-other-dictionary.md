# Python–用其他词典更新词典

> 原文:[https://www . geesforgeks . org/python-update-dictionary-with-other-dictionary/](https://www.geeksforgeeks.org/python-update-dictionary-with-other-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到需要用字典的其他键来执行字典更新的问题。在我们需要将某些记录添加到以前捕获的记录的域中，这可能会有应用程序。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的蛮力方式。在这种情况下，我们检查其他字典中的关键字，并在新字典中添加条目。

```py
# Python3 code to demonstrate working of 
# Update dictionary with other dictionary
# Using loop

# initializing dictionaries
test_dict1 = {'gfg' : 1, 'best' : 2, 'for' : 4, 'geeks' : 6}
test_dict2 = {'for' : 3, 'geeks' : 5}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Update dictionary with other dictionary
# Using loop
for key in test_dict1:
    if key in test_dict2:
        test_dict1[key] = test_dict2[key]

# printing result 
print("The updated dictionary is : " + str(test_dict1)) 
```

**Output :**

> 原词典 1 为:{'best': 2，' for': 4，' gfg': 1，' geeks': 6}
> 原词典 2 为:{'for': 3，' geeks': 5}
> 更新后的词典为:{'best': 2，' for': 3，' gfg': 1，' geeks': 5}