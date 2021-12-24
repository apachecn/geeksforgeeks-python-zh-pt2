# Python |将给定词典拆分为两半

> 原文:[https://www . geeksforgeeks . org/python-拆分-给定-词典一分为二/](https://www.geeksforgeeks.org/python-split-given-dictionary-in-half/)

在使用字典时，有时我们可能会遇到一个问题，即我们需要减少单个容器占用的空间，并希望将字典分成两半。让我们讨论执行这项任务的某些方法。

**方法#1:使用`items() + len()` +列表切片**
上述功能的组合可以轻松执行这个特殊的任务，其中通过列表切片将切片分成两半，通过`items()`提取字典条目

```py
# Python3 code to demonstrate working of
# Split dictionary by half
# Using items() + len() + list slicing

# Initialize dictionary
test_dict = {'gfg' : 6, 'is' : 4, 'for' : 2, 'CS' : 10}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Using items() + len() + list slicing
# Split dictionary by half
res1 = dict(list(test_dict.items())[len(test_dict)//2:])
res2 = dict(list(test_dict.items())[:len(test_dict)//2])

# printing result 
print("The first half of dictionary : " + str(res1))
print("The second half of dictionary : " + str(res2))
```

**Output :**

> 原词典:{'CS': 10，' for': 2，' is': 4，' gfg': 6}
> 前半部词典:{'is': 4，' gfg': 6}
> 后半部词典:{'for': 2，' CS': 10}