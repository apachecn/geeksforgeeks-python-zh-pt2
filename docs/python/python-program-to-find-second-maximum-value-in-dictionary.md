# Python 程序在字典中查找第二个最大值

> 原文:[https://www . geesforgeks . org/python-program-to-find-second-最大值-in-dictionary/](https://www.geeksforgeeks.org/python-program-to-find-second-maximum-value-in-dictionary/)

[Python 中的字典](https://contribute.geeksforgeeks.org/geek/python-dictionaries/)与其他语言中的关联数组或映射相同。与列表不同，字典以键值对存储数据。
我们来看看如何在 Python 字典中找到第二个最大值。
**方法#1:** 天真方法:
一般方法是找到字典的最大值，然后遍历字典，保持该值必须大于所有其他值且小于最大值。

## 蟒蛇 3

```py
# Python naive approach to find the
# second largest element in a dictionary

# creating a new dictionary
new_dict ={"google":12, "amazon":9, "flipkart":4, "gfg":13}

# maximum value
max = max(new_dict.values())

# iterate through the dictionary
max2 = 0
for v in new_dict.values():
     if(v>max2 and v<max):
            max2 = v

# print the second largest value
print(max2)
```

**Output:** 

```py
12
```

**方法#2:** 使用 sorted()方法
我们可以通过对字典的值进行排序，然后从排序列表中检索倒数第二个元素，从而找到字典中的第二大值。

## 蟒蛇 3

```py
# Python code to find second largest
# element from a dictionary using sorted() method

# creating a new Dictionary
example_dict = {"mark": 13, "steve": 3, "bill": 6, "linus": 11}

# now directly print the second largest
# value in the dictionary
print("Output1:", sorted(example_dict.values())[-2])

# More than 1 keys with maximum value are present
example_dict = {"fb": 20, "whatsapp": 12, "instagram": 20, "oculus": 10}
print("Output2:", sorted(set(example_dict.values()), reverse=True)[-2])
```

**Output:** 

```py
11
```

**解释:** example_dict.values()给出了字典中所有值的列表。sorted()方法将对 dict_values 列表进行排序。list(sorted(example _ dict . values())))[-2]将 dict_values 转换为 list，并返回排序列表的倒数第二个元素，即字典的第二大值。
如果字典中存在多个最大值，如第二个示例所示，将字典值转换为一个集合将消除重复。