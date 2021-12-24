# Python |删除字典键中的空格

> 原文:[https://www . geesforgeks . org/python-remove-spaces-from-dictionary-keys/](https://www.geeksforgeeks.org/python-remove-spaces-from-dictionary-keys/)

在 Python 中，[字典](https://www.geeksforgeeks.org/python-dictionary/)是一个无序的、可变的、有索引的集合。字典是用花括号写的，它们有键和值。它用于散列特定的密钥。

让我们看看如何在 Python 中删除字典键中的空格。

**方法#1:**
使用这里的`translate()`功能，我们逐个访问每个键，用无移除空格。这里，translate 函数接受参数 32，其中 32 是空格“”的 ASCII 值，用 none 替换它。

```
# Python program to remove space from keys

# creating a dictionary of type string

Product_list = {'P 01' : 'DBMS', 'P 02' : 'OS',
                'P 0 3 ': 'Soft Computing'}

# removing spaces from keys
# storing them in sam dictionary
Product_list = { x.translate({32:None}) : y 
                 for x, y in Product_list.items()}

# printing new dictionary
print (" New dictionary : ", Product_list)
```

**Output:**

```
New dictionary :  {'P01': 'DBMS', 'P03': 'Soft Computing', 'P02': 'OS'}

```

**方法 2:**
使用`replace()`功能。在这种方法中，我们逐个访问字典中的每个键，并用无空格替换键中的所有空格。这个函数把第二个非空间作为参数空间。

```
# Python program to remove space from keys

# creating a dictionary of type string

Product_list = {'P 01' : 'DBMS', 'P 02' : 'OS',
                'P 0 3 ': 'Soft Computing'};

# removing spaces from keys
# storing them in sam dictionary
Product_list = {x.replace(' ', ''): v 
     for x, v in Product_list.items()}

# printing new dictionary
print (" New dictionary : ", Product_list)
```

**Output:**

```
New dictionary :  {'P03': 'Soft Computing', 'P01': 'DBMS', 'P02': 'OS'}

```