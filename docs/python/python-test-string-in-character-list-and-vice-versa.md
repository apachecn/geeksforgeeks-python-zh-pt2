# Python–字符列表中的测试字符串，反之亦然

> 原文:[https://www . geesforgeks . org/python-test-字符串列表-反之亦然/](https://www.geeksforgeeks.org/python-test-string-in-character-list-and-vice-versa/)

给定一个字符串，检查它是否在字符列表中按顺序出现，反之亦然。

> **输入** : test_str = 'geeks '，K = ['g '，' e '，' K '，' f '，' o '，' r '，' g '，' e '，' e '，' K '，' s'] [字符串在字符列表中]
> **输出** : True
> **解释**:列表中存在 geeks，从第 7 个索引开始到结束。
> 
> **输入** : test_str = 'geeksforgeeks '，K = ['g '，' e '，' K '，' s '][字符串中的字符列表]
> **输出** : True
> **解释** : ['g '，' e '，' e '，' K '，' s '出现在字符串中，从字符串开头开始。

**方法#1:在运算符** **+** [**中使用**](https://www.geeksforgeeks.org/join-function-python/) [**连接()**](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/) **【字符列表中的字符串】**

在本文中，我们使用 join()将字符列表转换为字符串，并将其应用于运算符中，以测试子字符串的存在性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test String in Character List and vice-versa
# Using in operator and join() [String in list]

# initializing string
test_str = 'geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing Character list
K = ['g', 'e', 'e', 'k', 'f', 'o', 'r', 'g', 'e', 'e', 'k', 's']

# joining list
joined_list = ''.join(K)

# checking for presence
res = test_str in joined_list

# printing result
print("Is String present in character list : " + str(res))
```

**Output**

```py
The original string is : geeks
Is String present in character list : True
```

**方法 2:使用 in 运算符+ join() [字符串中的字符列表]**

在这种情况下，目标字符列表被转换为字符串，然后使用 In 运算符签入字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test String in Character List and vice-versa
# Using in operator + join() [ Character List in String ]

# initializing string
test_str = 'geeksforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing Character list
K = ['g', 'e', 'e', 'k', 's']

# joining list
joined_list = ''.join(K)

# checking for presence
res = joined_list in test_str

# printing result
print("Is character list present in String : " + str(res))
```

**Output**

```py
The original string is : geeksforgeeks
Is character list present in String : True
```