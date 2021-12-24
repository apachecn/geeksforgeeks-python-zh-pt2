# 将元组列表中的元素转换为浮点数的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-elements-in-list-tuples-to-float/](https://www.geeksforgeeks.org/python-program-to-convert-a-elements-in-a-list-of-tuples-to-float/)

给定一个 Tuple 列表，将所有可能的可转换元素转换为 float。

> **输入** : test_list = [("3 "，" Gfg ")，(" 1 "，" 26.45")]
> **输出** : [(3.0，' Gfg ')，(1.0，26.45)]
> **解释**:数值字符串转换为浮点数。
> 
> **输入** : test_list = [("3 "，" Gfg")]
> **输出** : [(3.0，' Gfg')]
> **解释**:数值字符串转换为浮点数。

**方法#1:使用 loop+**[**isalpha()**](https://www.geeksforgeeks.org/python-string-isalpha-application/)**+**[**float()**](https://www.geeksforgeeks.org/float-in-python/)

在这种情况下，我们使用一个循环来迭代所有元组，使用 isalpha()检查字母，它不能转换为 float，对于其余元素，float()用于转换。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Tuple List elements to Float
# Using loop + isalpha() + float

# initializing list
test_list = [("3", "Gfg"), ("1", "26.45"), ("7.32", "8"), ("Gfg", "8")]

# printing original list
print("The original list is : " + str(test_list))

res = []
for tup in test_list:
    temp = []
    for ele in tup:

        # check for string
        if ele.isalpha():
            temp.append(ele)
        else:

            # convert to float
            temp.append(float(ele))
    res.append((temp[0],temp[1]))

# printing result 
print("The converted list : " + str(res))
```

**输出:**

> 原始列表为:[('3 '，' Gfg ')，(' 1 '，' 26.45 ')，(' 7.32 '，' 8 ')，(' Gfg '，' 8')]
> 转换后的列表:[(3.0，' Gfg ')，(1.0，26.45)，(7.32，8.0)，(' Gfg '，8.0)]

**方法二:使用 loop+isalpha()+float()+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在本文中，我们使用列表理解来执行遍历内部元组的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Tuple List elements to Float
# Using loop + isalpha() + float

# initializing list
test_list = [("3", "Gfg"), ("1", "26.45"), ("7.32", "8"), ("Gfg", "8")]

# printing original list
print("The original list is : " + str(test_list))

res = []
for tup in test_list:

    # list comprehension to check for each case
    temp = [ele if ele.isalpha() else float(ele) for ele in tup]
    res.append((temp[0],temp[1]))

# printing result 
print("The converted list : " + str(res))
```

**输出:**

> 原始列表为:[('3 '，' Gfg ')，(' 1 '，' 26.45 ')，(' 7.32 '，' 8 ')，(' Gfg '，' 8')]
> 转换后的列表:[(3.0，' Gfg ')，(1.0，26.45)，(7.32，8.0)，(' Gfg '，8.0)]