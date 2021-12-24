# Python–字典的对称差异

> 原文:[https://www . geesforgeks . org/python-对称差异词典/](https://www.geeksforgeeks.org/python-symmetric-difference-of-dictionaries/)

给定两个字典，任务是编写一个 Python 程序来获得对称差。

**示例:**

> **输入:** test_dict1 = {'Gfg' : 4，' is' : 3，' best' : 7，' for' : 3，' geek' : 4}，
> 
> test_dict2 = {'Gfg' : 4，' is' : 3，' good' : 7，' for' : 3，' all' : 4}
> 
> **输出:**{“all”:4、“good”:7、“best”:7、“geek”:4 }
> 
> **说明:**全、好、最好、极客是相互唯一的键。
> 
> **输入:** test_dict1 = {'Gfg' : 4，' is' : 3，' good' : 7，' for' : 3，' geek' : 4}，
> 
> test_dict2 = {'Gfg' : 4，' is' : 3，' good' : 7，' for' : 3，' all' : 4}
> 
> **输出:** {'all': 4，' geek': 4}
> 
> **说明:**所有，极客都是相互唯一的钥匙。

**方法#1:使用^算子+** [**键()**](https://www.geeksforgeeks.org/python-dictionary-keys-method/) **+** [**字典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

在本文中，我们使用 key()提取所有的密钥，并使用^算子得到所有密钥的对称差。所需的词典是用词典理解法编写的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Symmetric Difference of Dictionaries
# Using ^ operator + keys() + dictionary comprehension

# initializing dictionaries
test_dict1 = {'Gfg': 4, 'is': 3, 'best': 7, 'for': 3, 'geek': 4}
test_dict2 = {'Gfg': 4, 'is': 3, 'good': 7, 'for': 3, 'all': 4}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# getting symmetric difference using ^ operation
res = {key: test_dict1[key] if key in test_dict1 else test_dict2[key]
       for key in test_dict1.keys() ^ test_dict2.keys()}

# printing result
print("The symmetric difference : " + str(res))
```

**输出:**

> 原词典 1 为:{'Gfg': 4，' is': 3，' best': 7，' for': 3，' geek': 4}
> 
> 原始字典 2 是:{'Gfg': 4，' is': 3，' good': 7，' for': 3，' all': 4}
> 
> 对称的区别:{'geek': 4，' best': 7，' all': 4，' good': 7}

**方法 2:使用 set . symmetric _ difference()+**[**键()**](https://www.geeksforgeeks.org/python-dictionary-keys-method/)

在本文中，我们使用内置函数 symmetric_difference()来执行获取不常见元素的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Symmetric Difference of Dictionaries
# Using set.symmetric_difference() + keys()

# initializing dictionaries
test_dict1 = {'Gfg': 4, 'is': 3, 'best': 7, 'for': 3, 'geek': 4}
test_dict2 = {'Gfg': 4, 'is': 3, 'good': 7, 'for': 3, 'all': 4}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# computing sym. difference using set inbuilt function
res = {key: test_dict1[key] if key in test_dict1 else test_dict2[key] for key in
       set(test_dict1.keys()).symmetric_difference(test_dict2.keys())}

# printing result
print("The symmetric difference : " + str(res))
```

**输出:**

> 原词典 1 为:{'Gfg': 4，' is': 3，' best': 7，' for': 3，' geek': 4}
> 
> 原始字典 2 是:{'Gfg': 4，' is': 3，' good': 7，' for': 3，' all': 4}
> 
> 对称差异:{“好”:7，“所有”:4，“极客”:4，“最佳”:7}