# Python 程序交换字典项目的位置

> 原文:[https://www . geesforgeks . org/python-程序到交换-字典-项目-位置/](https://www.geeksforgeeks.org/python-program-to-swap-dictionary-items-position/)

给定一个字典，任务是编写一个 python 程序来交换字典条目的位置。下面给出的代码采用两个索引，并在这些索引处交换值。

> **输入:** test_dict = {'Gfg' : 4，' is' : 1，' best' : 8，' for' : 10，' geeks' : 9}，I，j = 1，3
> 
> **输出:** {'Gfg': 4，' for': 10，' best': 8，' is': 1，'极客':9}
> 
> **说明:**(为:10)和(为:1)对调顺序。
> 
> **输入:** test_dict = {'Gfg' : 4，' is' : 1，' best' : 8，' for' : 10，' geeks' : 9}，I，j = 2，3
> 
> **输出:**{“Gfg”:4，“is”:1，“for”:10，“best”:8，“极客”:9}
> 
> **说明:**(适合:10)和(最佳:8)对调顺序。

**方法:** *使用* [*物品()*](https://www.geeksforgeeks.org/python-dictionary-items-method/) *和* [*dict()*](https://www.geeksforgeeks.org/python-dictionary/)

这项任务分三步完成:

*   第一字典被转换成元组形式的等价键值对，
*   下一个交换操作是以 Pythonic 方式执行的。
*   最后，元组列表以所需的格式转换回字典。

**示例:**

## 蟒蛇 3

```py
# initializing dictionary
test_dict = {'Gfg': 4, 'is': 1, 'best': 8, 'for': 10, 'geeks': 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing swap indices
i, j = 1, 3

# conversion to tuples
tups = list(test_dict.items())

# swapping by indices
tups[i], tups[j] = tups[j], tups[i]

# converting back
res = dict(tups)

# printing result
print("The swapped dictionary : " + str(res))
```

**输出:**

> 最初的字典是:{'Gfg': 4，' is': 1，' best': 8，' for': 10，' geeks': 9}
> 
> 交换的字典:{“Gfg”:4，“for”:10，“best”:8，“is”:1，“geeks”:9 }