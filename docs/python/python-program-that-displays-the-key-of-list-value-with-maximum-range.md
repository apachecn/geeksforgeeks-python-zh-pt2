# Python 程序，显示最大范围列表值的键

> 原文:[https://www . geesforgeks . org/python-显示最大范围值列表的键的程序/](https://www.geeksforgeeks.org/python-program-that-displays-the-key-of-list-value-with-maximum-range/)

给定一个具有列表中的键和值的字典，下面的程序显示其范围最大的值的键。

```py
Range = Maximum number-Minimum number

```

> **输入**:test _ dict = {“Gfg”:[6，2，4，1]，“is”:[4，7，3，3，8]，“Best”:[1，0，9，3]}
> **输出** : Best
> **解释**:9–0 = 9，与作为值给出的所有其他列表相比的最大范围
> **输入**:test _ dict = {“Gfg”:[16，2，4

**方法 1 :** *使用* [*max()*](https://www.geeksforgeeks.org/max-min-python/) *、*[*min()*](https://www.geeksforgeeks.org/max-min-python/)*和* [*循环*](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们得到每个列表的最大值()和最小值()，并执行差分来查找范围。然后存储该值，并通过在结果列表中应用 max()来计算所有这些值的最大差值。

## 蟒蛇 3

```py
# initializing dictionary
test_dict = {"Gfg" : [6, 2, 4, 1], "is" : [4, 7, 3, 3, 8], "Best" : [1, 0, 9, 3]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

max_res = 0
for sub, vals in test_dict.items():

    # storing maximum of difference
    max_res = max(max_res, max(vals) - min(vals))    
    if max_res == max(vals) - min(vals):
        res = sub

# printing result 
print("The maximum element key : " + str(res)) 
```

**输出:**

> 原始字典为:{'Gfg': [6，2，4，1]，' is': [4，7，3，3，8]，' Best': [1，0，9，3]}
> 
> 最大元素键:最佳

**方法二:** *使用* [*列表理解*](https://www.geeksforgeeks.org/comprehensions-in-python/)*[*最大()*](https://www.geeksforgeeks.org/max-min-python/) 和 [最小()](https://www.geeksforgeeks.org/max-min-python/)*

*在这种情况下，我们计算最大范围，然后使用列表理解提取与该差异匹配的关键字。*

## *蟒蛇 3*

```py
*# initializing dictionary
test_dict = {"Gfg" : [6, 2, 4, 1], "is" : [4, 7, 3, 3, 8], "Best" : [1, 0, 9, 3]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# getting max value 
max_res = max([max(vals) - min(vals) for sub, vals in test_dict.items()])

# getting key matching with maximum value 
res = [sub for sub in test_dict if max(test_dict[sub]) - min(test_dict[sub]) == max_res][0]

# printing result 
print("The maximum element key : " + str(res)) *
```

***输出:***

> *原始字典为:{'Gfg': [6，2，4，1]，' is': [4，7，3，3，8]，' Best': [1，0，9，3]}*
> 
> *最大元素键:最佳*