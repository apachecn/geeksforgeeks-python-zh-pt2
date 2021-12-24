# Python–测试字符串是否包含任何大写字符

> 原文:[https://www . geesforgeks . org/python-test-if-string-contains-any-大写字符/](https://www.geeksforgeeks.org/python-test-if-string-contains-any-uppercase-character/)

给定一个字符串，测试它是否包含任何大写字符。

> **输入**:test _ str = ' geeksforgeeks '
> **输出** : False
> **解释**:字符串中无大写字符。
> 
> **输入**:test _ str = ' geeksforgEeks '
> **输出** : True
> **解释** : E 在 String 中大写。

**方法#1:使用 loop + isupper()**

在本例中，我们对字符串中的每个字符进行迭代，使用 *isupper()* 检查大写字母，如果找到，字符串将被标记为真。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if String contains any Uppercase character
# Using isupper() + loop

# initializing string
test_str = 'geeksforGeeks'

# printing original string
print("The original string is : " + str(test_str))

res = False
for ele in test_str:

    # checking for uppercase character and flagging
    if ele.isupper():
        res = True
        break

# printing result
print("Does String contain uppercase character : " + str(res))
```

**输出:**

```
The original string is : geeksforGeeks
Does String contain uppercase character : True

```

**方法 2:使用任意()+ isupper()**

在本例中，我们使用 *any()* 来检查任何字符是否是大写字符。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if String contains any Uppercase character
# Using any() + isupper()

# initializing string
test_str = 'geeksforGeeks'

# printing original string
print("The original string is : " + str(test_str))

# Using any() to check for any element to be uppercase
res = any(ele.isupper() for ele in test_str)

# printing result
print("Does String contain uppercase character : " + str(res))
```

**输出:**

```
The original string is : geeksforGeeks
Does String contain uppercase character : True

```

**方法 3:使用正则表达式()**

可以使用适当的正则表达式来执行此任务。这将检查字符串中的任何大写字母。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if String contains any Uppercase character
# Using re()
import re

# initializing string
test_str = 'geeksforGeeks'

# printing original string
print("The original string is : " + str(test_str))

# Using regex to check for any element to be uppercase
res = bool(re.match(r'\w*[A-Z]\w*', test_str))

# printing result
print("Does String contain uppercase character : " + str(res))
```

**输出:**

```
The original string is : geeksforGeeks
Does String contain uppercase character : True

```

**方法#4:使用任意()+ ASCII 值**

检查每个字符是否在 ASCII 值大写池中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if String contains any Uppercase character
# Using any() + ASCII values

# initializing string
test_str = 'geeksforGeeks'

# printing original string
print("The original string is : " + str(test_str))

# Using ascii values check for any element to be uppercase
res = any(ord(ele) != 32 and ord(ele) <=
          64 or ord(ele) >= 91 for ele in test_str)

# printing result
print("Does String contain uppercase character : " + str(res))
```

**输出:**

```
The original string is : geeksforGeeks
Does String contain uppercase character : True

```