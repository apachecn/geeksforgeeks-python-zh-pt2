# Python 程序使用字典的自定义键值对创建列表

> 原文:[https://www . geesforgeks . org/python-program-to-create-list-use-custom-key-value-pair-of-a-dictionary/](https://www.geeksforgeeks.org/python-program-to-create-a-list-using-custom-key-value-pair-of-a-dictionary/)

给定一个字典列表，这里的任务是编写一个 python 程序，该程序可以将其转换为一个字典，其中包含来自自定义键值的项。

> **输入:** test_list = [{'gfg' : 1，' is' : 4，' best' : 6}，
> 
> {'gfg' : 10，' is' : 3，' best' : 7}，
> 
> {'gfg' : 9，' is' : 4，' best' : 2}，
> 
> {'gfg' : 4，' is' : 1，' best' : 0}，
> 
> {'gfg' : 6，' is' : 3，' best' : 8}]，键，值= 'gfg '，' best '
> 
> **输出:** {1: 6，10: 7，9: 2，4: 0，6: 8}
> 
> **说明:**构造带有‘gfg’的关键字和‘best’的值的字典。
> 
> **输入:** test_list = [{'gfg' : 1，' is' : 4，' best' : 6}，
> 
> {'gfg' : 10，' is' : 3，' best' : 7}，
> 
> {'gfg' : 9，' is' : 4，' best' : 2}]，键，值= 'gfg '，' best '
> 
> **输出:** {1: 6，10: 7，9: 2}
> 
> **说明:**构造带有‘gfg’的关键字和‘best’的值的字典。

**方法 1 :** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，迭代字典列表并提取所需自定义键的值，以声明结果字典的键值对。

**示例:**

## 蟒蛇 3

```py
# initializing list
test_list = [{'gfg': 1, 'is': 4, 'best': 6},
             {'gfg': 10, 'is': 3, 'best': 7},
             {'gfg': 9, 'is': 4, 'best': 2},
             {'gfg': 4, 'is': 1, 'best': 0},
             {'gfg': 6, 'is': 3, 'best': 8}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key-values
key, value = 'gfg', 'best'

res = dict()
for sub in test_list:

    # constructed values
    res[sub[key]] = sub[value]

# printing result
print("Dictionary values : " + str(res))
```

**输出:**

> *原列表为:[{'gfg': 1，' is': 4，' best': 6}，{'gfg': 10，' is': 3，' best': 7}，{'gfg': 9，' is': 4，' best': 2}，{'gfg': 4，' is': 1，' best': 0}，{'gfg': 6，' is': 3，' best': 8}]*
> 
> *字典值:{1: 6，10: 7，9: 2，4: 0，6: 8}*

**方法二:**使用[词典理解](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

在这种情况下，我们执行与上述方法类似的任务，不同之处在于字典理解被用来提供一个线性的替代方案。

**示例:**

## 蟒蛇 3

```py
# initializing list
test_list = [{'gfg': 1, 'is': 4, 'best': 6},
             {'gfg': 10, 'is': 3, 'best': 7},
             {'gfg': 9, 'is': 4, 'best': 2},
             {'gfg': 4, 'is': 1, 'best': 0},
             {'gfg': 6, 'is': 3, 'best': 8}]

# printing original list
print("The original list is : " + str(test_list))

# initializing key-values
key, value = 'gfg', 'best'

# dictionary comprehension for one liner
res = {sub[key]: sub[value] for sub in test_list}

# printing result
print("Dictionary values : " + str(res))
```

**输出:**

> *原列表为:[{'gfg': 1，' is': 4，' best': 6}，{'gfg': 10，' is': 3，' best': 7}，{'gfg': 9，' is': 4，' best': 2}，{'gfg': 4，' is': 1，' best': 0}，{'gfg': 6，' is': 3，' best': 8}]*
> 
> *字典值:{1: 6，10: 7，9: 2，4: 0，6: 8}*