# Python String islower()方法

> 原文:[https://www.geeksforgeeks.org/python-string-islower-method/](https://www.geeksforgeeks.org/python-string-islower-method/)

Python String islower()方法检查字符串中的所有字符是否都是小写的。如果字符串中的所有字母都是小写字母，该方法返回 **True** 。如果字符串至少包含一个大写字母，则返回 False。

> **语法:**
> 
> string.islower（）
> 
> **参数:**
> 
> 没有人
> 
> **返回:**
> 
> *   True:如果字符串中的所有字母都是小写，并且
> *   错误:如果其中一个大写。

### **示例 1:** 演示 islower()的工作原理

## 蟒蛇 3

```py
# Python3 code to demonstrate
# working of islower()

# initializing string
islow_str = "geeksforgeeks"
not_islow = "Geeksforgeeks"

# checking which string is
# completely lower
print ("Is geeksforgeeks full lower ? : " + str(islow_str.islower()))
print ("Is Geeksforgeeks full lower ? : " + str(not_islow.islower()))
```

**输出:**

```py
Is geeksforgeeks full lower ? : True
Is Geeksforgeeks full lower ? : False
```

### 示例 2:实际应用

这个功能可以有多种用途，有很多实际应用。一个这样的应用是检查小写，检查专有名词，检查需要所有小写的句子的正确性。下面演示的是一个小例子，展示了 islower()方法的应用。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# application of islower() method

# checking for proper nouns.
# nouns which start with capital letter

test_str = "Geeksforgeeks is most rated Computer \
            Science portal and is highly recommended"

# splitting string
list_str = test_str.split()

count = 0

# counting lower cases
for i in list_str:
    if (i.islower()):
        count = count + 1

# printing proper nouns count
print ("Number of proper nouns in this sentence is : "
                            + str(len(list_str)-count))
```

**输出:**

```py
Number of proper nouns in this sentence is : 3
```