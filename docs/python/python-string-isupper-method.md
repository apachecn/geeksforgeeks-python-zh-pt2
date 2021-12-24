# Python String isupper()方法

> 原文:[https://www.geeksforgeeks.org/python-string-isupper-method/](https://www.geeksforgeeks.org/python-string-isupper-method/)

Python String isupper()方法返回字符串中的所有字符是否都大写。

> **语法:**
> 
> string.isupper()
> 
> **参数:**
> 
> isupper()方法不接受任何参数。
> 
> **返回:**
> 
> 如果字符串中的所有字母都是大写字母，则为 True 如果其中一个字母是小写字母，则为 False。

### **示例 1:** 演示 isupper()的工作

## 蟒蛇 3

```
# Python3 code to demonstrate
# working of isupper()

# initializing string
isupp_str = "GEEKSFORGEEKS"
not_isupp = "Geeksforgeeks"

# Checking which string is
# completely uppercase
print ("Is GEEKSFORGEEKS full uppercase ? : " + str(isupp_str.isupper()))
print ("Is Geeksforgeeks full uppercase ? : " + str(not_isupp.isupper()))
```

**输出:**

```
Is GEEKSFORGEEKS full uppercase ? : True
Is Geeksforgeeks full uppercase ? : False
```

### 例 2: **实际应用**

这个功能可以有多种用途，有很多实际应用。检查大写字母的一种应用，检查缩写(通常是大写字母)，检查句子的正确性，要求所有大写字母。下面是一个展示 isupper()方法应用的小例子。

## 蟒蛇 3

```
# Python3 code to demonstrate
# application of isupper()

# checking for abbreviations.
# short form of work/phrase
test_str = "Cyware is US based MNC and works in IOT technology"

# splitting string
list_str = test_str.split()

count = 0

# counting upper cases
for i in list_str:
    if (i.isupper()):
        count = count + 1

# printing abbreviations count
print ("Number of abbreviations in this sentence is : " + str(count))
```

**输出:**

```
Number of abbreviations in this sentence is : 3
```