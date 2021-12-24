# Python |选择条件给定键大于 k 的字典

> 原文:[https://www . geeksforgeeks . org/python-select-dictionary-with-condition-给定-key-大于-k/](https://www.geeksforgeeks.org/python-select-dictionary-with-condition-given-key-greater-than-k/)

在 Python 中，有时我们只需要获得解决问题所需的一些字典。这个问题在 web 开发中很常见，我们只需要得到满足给定标准的选择性字典。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解**

```py
# Python3 code to demonstrate
# filtering of a list of dictionary
# on basis of condition

# initialising list of dictionary
ini_list = [{'a':1, 'b':3, 'c':7}, {'a':3, 'b':8, 'c':17},
            {'a':78, 'b':12, 'c':13}, {'a':2, 'b':2, 'c':2}]

# printing initial list of dictionary
print ("initial_list", str(ini_list))

# code to filter list
# where c is greater than 10
res = [d for d in ini_list if d['c'] > 10]

# printing result
print ("resultant_list", str(res))
```

**输出:**

> initial_list [{'c': 7，' b': 3，' a': 1}，{'c': 17，' b': 8，' a': 3}，{'c': 13，' b': 12，' a': 78}，{'c': 2，' b': 2，' a ':2 }]
> result _ list[{ ' c ':17，' b': 8，' a': 3}，{'c': 13，' b': 12，' a': 78}]

**方法 2:使用λ和滤波器**

```py
# Python3 code to demonstrate
# filtering of list of dictionary
# on basis of condition

# initialising list of dictionary
ini_list = [{'a':1, 'b':3, 'c':7}, {'a':3, 'b':8, 'c':17},
            {'a':78, 'b':12, 'c':13}, {'a':2, 'b':2, 'c':2}]

# printing initial list of dictionary
print ("initial_list", str(ini_list))

# code to filter list
# where c is less than 10
res = list(filter(lambda x:x["c"] > 10, ini_list ))

# printing result
print ("resultant_list", str(res))
```

**输出:**

> initial_list [{'b': 3，' c': 7，' a': 1}，{'b': 8，' c': 17，' a': 3}，{'b': 12，' c': 13，' a': 78}，{'b': 2，' c': 2，' a ':2 }]
> result _ list[{ ' c ':17，' b': 8，' a': 3}，{'c': 13，' b': 12，' a': 78}]

**方法三:使用字典理解和列表理解**

```py
# Python3 code to demonstrate
# filtering of list of dictionary
# on basis of condition

# initialising list of dictionary
ini_list = [{'a':1, 'b':3, 'c':7}, {'a':3, 'b':8, 'c':17},
            {'a':78, 'b':12, 'c':13}, {'a':2, 'b':2, 'c':10}]

# printing initial list of dictionary
print ("initial_list", str(ini_list))

# code to filter list
# where c is more than 10

res = [{ k:v for (k, v) in i.items()} 
        for i in ini_list if i.get('c') > 10]

# printing result
print ("resultant_list", str(res))
```

**输出:**

> initial_list [{'a': 1，' c': 7，' b': 3}，{'a': 3，' c': 17，' b': 8}，{'a': 78，' c': 13，' b': 12}，{'a': 2，' c': 10，' b ':2 }]
> result _ list[{ ' a ':3，' c': 17，' b': 8}，{'a': 78，' c': 13，' b': 12}]