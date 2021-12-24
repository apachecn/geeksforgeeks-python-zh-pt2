# Python 程序创建包含字典列表中所有关键字的子字典

> 原文:[https://www . geesforgeks . org/python-program-to-create-a-sub-dictionary-containing-all-key-from-dictionary-list/](https://www.geeksforgeeks.org/python-program-to-create-a-sub-dictionary-containing-all-keys-from-dictionary-list/)

给定字典列表，我们的任务是创建一个包含所有关键字的新字典列表，如果没有，则为关键字分配无，并保存每个字典。

**示例:**

> **输入:** test_list = [{'gfg' : 3，' is' : 7}，{'gfg' : 3，' is' : 1，' best' : 5}，{'gfg' : 8}]
> 
> **输出:** [{'is': 7，' best ':无，' gfg': 3}，{'is': 1，' best': 5，' gfg': 3}，{'is ':无，' best ':无，' gfg': 8}]
> 
> **解释:**带有“是”和“最好”的项目被添加到所有列表中，如果没有填充值，则在缺少的地方显示为“无”。
> 
> **输入:** test_list = [{'gfg' : 3}，{'gfg' : 3，' best' : 5}，{'gfg' : 8}]
> 
> **输出:** [{'best ':无，' gfg': 3}，{'best': 5，' gfg': 3}，{'best ':无，' gfg': 8}]
> 
> **说明:**具有“最佳”的项目被添加到所有列表中，如果没有填充值，则在缺少的地方显示为“无”。

**方法#1:使用** [**集()**](https://www.geeksforgeeks.org/python-set-method/) **+** [**链. from _ iterable()**](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)**+**[**get()**](https://www.geeksforgeeks.org/get-method-dictionaries-python/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在本例中，我们使用 set()和 chain.from_iterable()执行获取所有必需密钥的任务。下一步是使用列表理解和 get()更新所有没有找到关键字的字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Ensure all keys in dictionary list
# Using set() + chain.from_iterable() + get() + list comprehension
from itertools import chain

# initializing list
test_list = [{'gfg' : 3, 'is' : 7},
             {'gfg' : 3, 'is' : 1, 'best' : 5},
             {'gfg' : 8}]

# printing original list
print("The original list is : " + str(test_list))

# extracting all keys
all_keys = set(chain.from_iterable(test_list))

# assigning None using get() if key's value is not found
res = [dict((key, sub.get(key, None)) for key in all_keys) for sub in test_list]

# printing result
print("Reformed dictionaries list : " + str(res))
```

**输出:**

> 原始列表为:[{'gfg': 3，' is': 7}，{'gfg': 3，' is': 1，' best': 5}，{'gfg': 8}]
> 
> 改良词典列表:[{'gfg': 3，' best ':无，' is': 7}，{'gfg': 3，' best': 5，' is': 1}，{'gfg': 8，' best ':无，' is ':无}]

**方法 2:使用 set()+chain . from _ iterable()+update()**

在这种情况下，字典中所有关键字的更新和检查都是使用 update()完成的，其余所有函数保持相似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Ensure all keys in dictionary list
# Using set() + chain.from_iterable() + update()
from itertools import chain

# initializing list
test_list = [{'gfg' : 3, 'is' : 7},
             {'gfg' : 3, 'is' : 1, 'best' : 5},
             {'gfg' : 8}]

# printing original list
print("The original list is : " + str(test_list))

# extracting all keys
all_keys = set(chain.from_iterable(test_list))

# assigning None using update() if key is not found
for sub in test_list:
    sub.update({key: None for key in all_keys if key not in sub})

# printing result
print("Reformed dictionaries list : " + str(test_list))
```

**输出:**

> 原始列表为:[{'gfg': 3，' is': 7}，{'gfg': 3，' is': 1，' best': 5}，{'gfg': 8}]
> 
> 改良词典列表:[{'gfg': 3，' best ':无，' is': 7}，{'gfg': 3，' best': 5，' is': 1}，{'gfg': 8，' best ':无，' is ':无}]