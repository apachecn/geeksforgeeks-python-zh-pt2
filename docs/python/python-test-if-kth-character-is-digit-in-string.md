# Python–测试字符串中的第 k 个字符是否是数字

> 原文:[https://www . geesforgeks . org/python-test-if-kth-character-is-digits-in-string/](https://www.geeksforgeeks.org/python-test-if-kth-character-is-digit-in-string/)

给定一个字符串，检查 Kth 索引是否是一个数字。

> **输入** : test_str = 'geeks9geeks '，K = 5
> **输出**:真
> **解释**:第 5 个 idx 元素是 9，一个数字，因此为真。
> **输入** : test_str = 'geeks9geeks '，K = 4
> **输出** : False
> **解释**:第 4 个 idx 元素是 s，不是数字，因此为 False。

**方法#1:在操作员中使用**

在这种情况下，我们创建一个数字串，然后使用 In 运算符检查该数字串中是否有 Kth 个数字。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if Kth character is digit in String
# Using in operator

# initializing string
test_str = 'geeks4geeks'

# printing original String
print("The original string is : " + str(test_str))

# initializing K
K = 5

# checking if Kth digit is string
# getting numeric str
num_str = "0123456789"
res = test_str[K] in num_str

# printing result
print("Is Kth element String : " + str(res))
```

**Output**

```
The original string is : geeks4geeks
Is Kth element String : True
```

**方法 2:使用 isdigit()**

在这种情况下，我们使用内置的 Py。函数来解决这个问题，并检查 Kth 元素是否是数字。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if Kth character is digit in String
# Using isdigit()

# initializing string
test_str = 'geeks4geeks'

# printing original String
print("The original string is : " + str(test_str))

# initializing K
K = 5

# isdigit checks for digit
res = test_str[K].isdigit()

# printing result
print("Is Kth element String : " + str(res))
```

**Output**

```
The original string is : geeks4geeks
Is Kth element String : True
```