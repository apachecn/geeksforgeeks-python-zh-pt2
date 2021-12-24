# Python 程序反转字符串中的替换字符

> 原文:[https://www . geesforgeks . org/python-程序到反向-字符串中的替代字符/](https://www.geeksforgeeks.org/python-program-to-reverse-alternate-characters-in-a-string/)

给定一个字符串，反转它的替换字符串。

> **输入**:test _ str = ' geeks 4 geeks '
> **输出**:keekr 4 geeks
> **解释**:只有 g、e、s、r、e、k 是反转的，其余都是相同的位置。
> 
> **输入** : test_str = 'geeks'
> **输出** : seekg
> **解释**:只有 g、e、s 是反转的，其余都是相同的位置。

**方法#1:使用循环+切片+反向()**

这是执行这项任务的方法之一。在这种情况下，我们使用切片提取替换，然后使用反转来反转字符串。字符串的重建是使用循环完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Alternate characters reverse in String 
# Using loop + slicing + reversed()

# initializing string
test_str = 'geeks4rgeeks'

# printing original string
print("The original string is : " + str(test_str))

# extracting alternate string 
alt = test_str[::2]
not_alt = test_str[1::2]

# performing reverse 
alt = "".join(reversed(alt))

res = ''
# remaking string 
for idx in range(len(alt)):
    res += alt[idx]
    res += not_alt[idx]

# printing result 
print("Is alternate reversed string : " + str(res)) 
```

**Output**

```
The original string is : geeks4rgeeks
Is alternate reversed string : keekr4sgeegs

```

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。在这种情况下，我们通过使用列表理解的单行功能来执行与上面类似的功能。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Alternate characters reverse in String 
# Using list comprehension

# initializing string
test_str = 'geeks4rgeeks'

# printing original string
print("The original string is : " + str(test_str))

# using one-liner to solve the problem 
res = "".join(["".join(reversed(test_str[::2]))[idx] + test_str[1::2][idx]
      for idx in range(len("".join(reversed(test_str[::2]))))])

# printing result 
print("Is alternate reversed string : " + str(res)) 
```

**Output**

```
The original string is : geeks4rgeeks
Is alternate reversed string : keekr4sgeegs

```