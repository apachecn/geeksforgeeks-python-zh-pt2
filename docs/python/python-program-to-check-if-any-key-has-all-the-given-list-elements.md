# Python 程序检查任意键是否具有所有给定的列表元素

> 原文:[https://www . geesforgeks . org/python-program-to-check-if-key-if-all-给定列表元素/](https://www.geeksforgeeks.org/python-program-to-check-if-any-key-has-all-the-given-list-elements/)

给定一个包含列表值和列表的字典，任务是编写一个 Python 程序来检查任何键是否包含所有列表元素。

**示例:**

> **输入:** test_dict = {'Gfg' : [5，3，1，6，4]，' is' : [8，2，1，6，4]，' best' : [1，2，7，3，9]，' for' : [5，2，7，8，4，1]，' all' : [8，5，3，1，2]}，find_list = [7，9，2]
> 
> **输出:**真
> 
> **解释:** best 有所有值，7，9，2 因此返回 2。
> 
> **输入:** test_dict = {'Gfg' : [5，3，1，6，4]，' is' : [8，2，1，6，4]，' best' : [1，2，7，3，19]，' for' : [5，2，7，8，4，1]，' all' : [8，5，3，1，2]}，find_list = [7，9，2]
> 
> **输出:**假
> 
> **说明:**没有列表将所有值都作为查找列表。

**方法#1:使用**[**issuperset()**](https://www.geeksforgeeks.org/issuperset-in-python/)**+**[**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在本例中，我们使用 issuperset()执行查找值列表中所有元素的任务，并使用循环来迭代所有键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract values of Particular Key in
# Nested Values Using list comprehension

# initializing dictionary
test_dict = {'Gfg': [5, 3, 1, 6, 4], 
             'is': [8, 2, 1, 6, 4], 
             'best': [1, 2, 7, 3, 9],
             'for': [5, 2, 7, 8, 4, 1], 
             'all': [8, 5, 3, 1, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list
find_list = [7, 9, 2]

res = False
for key in test_dict:

    # checking if all values present using 
    # superset
    if set(test_dict[key]).issuperset(find_list):
        res = True

# printing result
print("Is any value list superset ? : " + str(res))
```

**输出:**

> 原始字典为:{'Gfg': [5，3，1，6，4]，' is': [8，2，1，6，4]，' best': [1，2，7，3，9]，' for': [5，2，7，8，4，1]，' all': [8，5，3，1，2]}
> 
> 有值列表超集吗？:真

**方法二:使用** [**任意()**](https://www.geeksforgeeks.org/python-any-function/)**+**[**issuperset()**](https://www.geeksforgeeks.org/issuperset-in-python/)

在本例中，我们使用 any()执行检查所有密钥的任务。Rest 所有功能与上述方法类似。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract values of Particular Key in
# Nested Values Using any() + issuperset()

# initializing dictionary
test_dict = {'Gfg': [5, 3, 1, 6, 4],
             'is': [8, 2, 1, 6, 4],
             'best': [1, 2, 7, 3, 9],
             'for': [5, 2, 7, 8, 4, 1],
             'all': [8, 5, 3, 1, 2]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list
find_list = [7, 9, 2]

res = any(set(sub).issuperset(find_list) 
          for sub in test_dict.values())

# printing result
print("Is any value list superset ? : " + str(res))
```

**输出:**

> 原始字典为:{'Gfg': [5，3，1，6，4]，' is': [8，2，1，6，4]，' best': [1，2，7，3，9]，' for': [5，2，7，8，4，1]，' all': [8，5，3，1，2]}
> 
> 有值列表超集吗？:真