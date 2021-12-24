# Python 程序求字符串权重

> 原文:[https://www . geesforgeks . org/python-program-to-find-the-string-weight/](https://www.geeksforgeeks.org/python-program-to-find-the-string-weight/)

给定一个字符串，每个字符映射一个权重(数字)，计算字符串的总权重。

> **输入** : test_str = 'GeeksforGeeks '，{“G”:1，“e”:2，“k”:5，“f”:3，“s”:15，“o”:4，“r”:6 }
> **输出** : 63
> **解释**:2(G * 2)+8(e * 4)+30(s * 2)+10(k * 2)+4(o)+6(r)+3(f)= 63。
> 
> **输入** : test_str = 'Geeks '，{“G”:1，“e”:2，“k”:5，“s”:15 }
> **输出** : 25

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们对所有字符进行迭代，并对字典映射的所有权重进行求和。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# String Weight
# Using loop

# initializing string
test_str = 'GeeksforGeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing sum dictionary
sum_dict = {"G" : 5, "e" : 2, "k" : 10,
            "f" : 3, "s" : 15, "o" : 4, "r" : 6}

# referring dict for sum
# iteration using loop
res = 0
for ele in test_str:
    res += sum_dict[ele]

# printing result
print("The weighted sum : " + str(res))
```

**Output**

```
The original string is : GeeksforGeeks
The weighted sum : 81
```

**方法 2:使用 sum()**

这是执行这项任务的另一种方式。在这种情况下，我们使用生成器表达式，sum()用于计算各个权重的总和。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# String Weight
# Using sum()

# initializing string
test_str = 'GeeksforGeeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing sum dictionary
sum_dict = {"G" : 5, "e" : 2, "k" : 10, "f" : 3,
            "s" : 15, "o" : 4, "r" : 6}

# sum() used to get summation
res = sum(sum_dict[ele] for ele in test_str)

# printing result
print("The weighted sum : " + str(res))
```

**Output**

```
The original string is : GeeksforGeeks
The weighted sum : 81
```