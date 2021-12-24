# Python–用下一个元音替换元音

> 原文:[https://www . geesforgeks . org/python-用下一个元音替换元音/](https://www.geeksforgeeks.org/python-replace-vowels-by-next-vowel/)

给定一个字符串，用序列中的下一个元音替换每个元音。

> **输入**:test _ str = ' geek forgeeks '
> **输出**:giikfurgiks
> **解释**:e 后下一个元音为 I，所有 e 替换为 I。
> 
> **输入**:test _ str = ' geek forgek es best '
> **输出**:giikfurgiks OS BIST
> **解释**:e 之后，下一个元音是 I，所有 e 替换为 I。

**方法一:使用 zip() +列表理解**

这是执行这项任务的方法之一。在这种情况下，我们使用 zip()执行形成替换词典的任务，然后使用列表理解来执行用下一个元音替换的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace vowels by next vowel
# Using list comprehension + zip()

# initializing string
test_str = 'geekforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# constructing dictionary using zip()
vow = 'a e i o u'.split()
temp = dict(zip(vow, vow[1:] + [vow[0]]))

# list comprehension to perform replacement
res = "".join([temp.get(ele, ele) for ele in test_str])

# printing result 
print("The replaced string : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks
The replaced string : giikfurgiiks

```

**方法二:使用词典理解+列表理解**

这是执行这项任务的另一种方式。在本文中，我们使用字典理解来执行映射任务，使用列表理解来执行替换任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Replace vowels by next vowel
# Using list comprehension + dictionary comprehension

# initializing string
test_str = 'geekforgeeks'

# printing original string
print("The original string is : " + str(test_str))

# constructing dictionary using dictionary comprehension
vow = "aeiou"
temp = {vow[idx] : vow[(idx + 1) % len(vow)] for idx in range(len(vow))}

# using get() to map elements to dictionary and join to convert
res = "".join([temp.get(ele, ele) for ele in test_str])

# printing result 
print("The replaced string : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks
The replaced string : giikfurgiiks

```