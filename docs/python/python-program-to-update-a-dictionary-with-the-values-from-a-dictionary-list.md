# Python 程序，使用字典列表中的值更新字典

> 原文:[https://www . geesforgeks . org/python-program-to-update-a-dictionary-with-values-from-dictionary-list/](https://www.geeksforgeeks.org/python-program-to-update-a-dictionary-with-the-values-from-a-dictionary-list/)

给定字典和字典列表，用字典列表值更新字典。

> **输入**:test _ dict = {“Gfg”:2、“is”:1、“Best”:3 }、dict_list = [{'for' : 3、' all' : 7}、{'and' : 1、' CS' : 9}]
> **输出**:{“Gfg”:2、' is': 1、' Best': 3、' for' : 3、' all' : 7、' and' : 1、' CS': 9}
> **解释**:单词典中更新的所有词典键。
> 
> **输入**:test _ dict = {“Gfg”:2、“is”:1、“Best”:3 }、dict _ list =[{“for”:3、“All”:7 }]
> **输出**:{“Gfg”:2、“is”:1、“Best”:3、“for”:3、“All”:7 }
> **解释**:所有字典键在单个字典中更新。

**方法#1:使用** [**更新()**](https://www.geeksforgeeks.org/python-dictionary-update-method/#:~:text=In%20Python%20Dictionary%2C%20update(),iterable%20of%20key%2Fvalue%20pairs.&text=Parameters%3A%20This%20method%20takes%20either,(generally%20tuples)%20as%20parameters.) **+循环**

在这种情况下，我们遍历循环中的所有元素，并执行更新以将字典中的所有键更新为原始字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Update dictionary with dictionary list
# Using update() + loop

# initializing dictionary
test_dict = {"Gfg" : 2, "is" : 1, "Best" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing dictionary list
dict_list = [{'for' : 3, 'all' : 7}, {'geeks' : 10}, {'and' : 1, 'CS' : 9}]

for dicts in dict_list:

    # updating using update()
    test_dict.update(dicts)

# printing result
print("The updated dictionary : " + str(test_dict))
```

**输出:**

> 原词典为:{'Gfg': 2，' is': 1，' Best': 3}
> 
> 更新后的词典:{“Gfg”:2，“is”:1，“Best”:3，“for”:3，“all”:7，“geeks”:10，“and”:1，“CS”:9 }

**方法 2:使用** [**链图**](https://www.geeksforgeeks.org/chainmap-in-python/)**+**[*** ***](https://www.geeksforgeeks.org/python-operators/)**运算符**

在本例中，我们使用 ChainMap 执行将所有列表词典合并为 1 的任务，并使用**运算符将目标词典合并为合并词典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Update dictionary with dictionary list
# Using ChainMap + ** operator
from collections import ChainMap

# initializing dictionary
test_dict = {"Gfg" : 2, "is" : 1, "Best" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing dictionary list
dict_list = [{'for' : 3, 'all' : 7}, {'geeks' : 10}, {'and' : 1, 'CS' : 9}]

# ** operator extracts keys and re initiates.
# ChainMap is used to merge dictionary list
res = {**test_dict, **dict(ChainMap(*dict_list))}

# printing result
print("The updated dictionary : " + str(res))
```

**输出:**

> 原词典为:{'Gfg': 2，' is': 1，' Best': 3}
> 
> 更新后的词典:{“Gfg”:2，“is”:1，“Best”:3，“for”:3，“all”:7，“geeks”:10，“and”:1，“CS”:9 }