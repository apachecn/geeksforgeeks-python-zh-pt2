# Python–调整字典中按键的大小

> 原文:[https://www . geesforgeks . org/python-resize-keys-in-dictionary/](https://www.geeksforgeeks.org/python-resize-keys-in-dictionary/)

给定字典，通过从键开始获取 K 个元素来调整键的大小。

> **输入**:test _ dict = {“geeks forgeeks”:3、“best”:3、“coding”:4、“practice”:3 }、K = 3
> **输出**:{“gee”:3、“bes”:3、“cod”:4、“pra”:3 }
> **解释**:按键调整大小为有 3 个元素。
> 
> **输入**:test _ dict = {“geeks forgeeks”:3、“best”:3、“coding”:4、“practice”:3 }、K = 4
> **输出**:{“geek”:3、“best”:3、“codi”:4、“prac”:3 }
> **解释**:按键调整大小为有 4 个元素。

**方法#1:使用切片+循环**

在这种情况下，调整大小是使用字典键的切片来完成的，循环用于迭代字典的所有键。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Resize Keys in dictionary
# Using slicing + loop

# initializing dictionary
test_dict = {"geeksforgeeks": 3, "best": 3, "coding": 4, "practice": 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 2

# reforming dictionary
res = dict()
for key in test_dict:

    # resizing to K prefix keys
    res[key[:K]] = test_dict[key]

# printing result
print("The required result : " + str(res))
```

**输出:**

> 原词典为:{'geeksforgeeks': 3，' best': 3，' coding': 4，' practice': 3}
> 所需结果:{'ge': 3，' be': 3，' co': 4，' pr': 3}

**方法二:使用** [**字典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/) **+切片**

在本文中，我们使用字典理解来执行一行中的字典改革任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Resize Keys in dictionary
# Using dictionary comprehension + slicing

# initializing dictionary
test_dict = {"geeksforgeeks": 3, "best": 3, "coding": 4, "practice": 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K
K = 2

# reforming dictionary
res = {key[:K]: test_dict[key] for key in test_dict}

# printing result
print("The required result : " + str(res))
```

**输出:**

> 原词典为:{'geeksforgeeks': 3，' best': 3，' coding': 4，' practice': 3}
> 所需结果:{'ge': 3，' be': 3，' co': 4，' pr': 3}