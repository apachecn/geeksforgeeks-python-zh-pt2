# Python–最小值键分配

> 原文:[https://www . geesforgeks . org/python-最小值-键-赋值/](https://www.geeksforgeeks.org/python-minimum-value-key-assignment/)

给定两个字典，任务是编写一个 Python 程序，为两个字典中的匹配键分配最小值。

**示例:**

> **输入:**test _ dict 1 = {“gfg”:1，“is”:7，“best”:8 }，test _ dict 2 = {“gfg”:2，“is”:2，“best”:10 }
> 
> **输出:**{“gfg”:1，“is”:2，“best”:8 }
> 
> **说明:**1 和 2 的最小值是 1，因此，gfg 被赋予 1，以此类推。
> 
> **输入:**test _ dict 1 = {“gfg”:1，“is”:7，“best”:12 }，test _ dict 2 = {“gfg”:2，“is”:2，“best”:10 }
> 
> **输出:**{“gfg”:1，“is”:2，“best”:10 }
> 
> **说明:**10 和 12 的最小值是 10，因此，最好分配 10，以此类推。

**方法一:使用** [**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)**+**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+**[**项()**](https://www.geeksforgeeks.org/python-dictionary-items-method/)

在这种情况下，使用 min()提取键的最小值。字典理解用于用修改后的值重建字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Minimum value key assignment
# Using dictionary comprehension + min() + items()

# initializing dictionaries
test_dict1 = {"gfg": 1, "is": 7, "best": 8}
test_dict2 = {"gfg": 2, "is": 2, "best": 10}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# using min() to assign min values
res = {key: min(val, test_dict2[key]) for key, val in test_dict1.items()}

# printing result
print("The minimum value keys : " + str(res))
```

**输出:**

```
The original dictionary 1 is : {'gfg': 1, 'is': 7, 'best': 8}
The original dictionary 2 is : {'gfg': 2, 'is': 2, 'best': 10}
The minimum value keys : {'gfg': 1, 'is': 2, 'best': 8}
```

**方法 2:使用**[**dict()**](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)**+**[**min()**](https://www.geeksforgeeks.org/python-min-function/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在这种情况下，为了更好的比较， *zip()* 用于获取要比较的值， *min()* 用于获取键的最小值。然后*字典()*用于结果到字典的转换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Minimum value key assignment
# Using dict() + min() + zip()

# initializing dictionaries
test_dict1 = {"gfg": 1, "is": 7, "best": 8}
test_dict2 = {"gfg": 2, "is": 2, "best": 10}

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# using min() to assign min values
# dict() for conversion of result to dictionary
res = dict([min(i, j) for i, j in zip(test_dict1.items(), test_dict2.items())])

# printing result
print("The minimum value keys : " + str(res))
```

**输出:**

```
The original dictionary 1 is : {'gfg': 1, 'is': 7, 'best': 8}
The original dictionary 2 is : {'gfg': 2, 'is': 2, 'best': 10}
The minimum value keys : {'gfg': 1, 'is': 2, 'best': 8}
```