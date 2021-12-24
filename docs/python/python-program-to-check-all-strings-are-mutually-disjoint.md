# Python 程序检查所有字符串是否互不相交

> 原文:[https://www . geesforgeks . org/python-程序检查-所有字符串都是相互分离的/](https://www.geeksforgeeks.org/python-program-to-check-all-strings-are-mutually-disjoint/)

给定一个字符串列表，我们的任务是编写一个 Python 程序来检查所有字符串是否相互分离。

**示例:**

> **输入:**test _ list =[“gfg”、“is”、“bet”]
> 
> **输出:**真
> 
> **说明:**其他字符串中无字符串重复。
> 
> **输入:**test _ list =[“gfg”、“is”、“best”]
> 
> **输出:**假
> 
> **解释:** s 在“是”和“最好”两个方向重复，因此为假。

**方法#1:使用** [**任意()**](https://www.geeksforgeeks.org/python-any-function/) **+** [**相交()**](https://www.geeksforgeeks.org/intersection-function-python/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在本例中，我们使用交集()执行获取公共元素的任务，使用枚举()在所有字符串组合之间执行交集，使用 any()测试任何字符串是否有任何字符出现在其他字符串中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if all strings are mutually disjoint
# Using any() + intersection() + enumerate()

# initializing list
test_list = ["gfg", "is", "bet"]

# printing original list
print("The original list is : " + str(test_list))

# performing intersection of each string with every other
res = not any(set(list(sub1)).intersection(set(list(sub2)))
              for idx, sub1 in enumerate(test_list) 
              for sub2 in test_list[idx + 1:])

# printing result
print("Are strings mutually disjoint? : " + str(res))
```

**输出:**

```
The original list is : ['gfg', 'is', 'bet']
Are strings mutually disjoint? : True
```

**方法 2:使用**[**join()**](https://www.geeksforgeeks.org/join-function-python/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**set()**](https://www.geeksforgeeks.org/python-set-method/)

这个问题可以通过匹配连接的字符串长度并检查字符串和转换集的长度是否相等来解决。如果相似的字符串包含重复的元素，则失败。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test if all strings are mutually disjoint
# Using 

# initializing list
test_list = ["gfg", "is", "bet"]

# printing original list
print("The original list is : " + str(test_list))

# performing concatenation and checking 
# for lengths 
concats = ''.join(test_list) 
res = len(concats) == len(set(concats))

# printing result
print("Are strings mutually disjoint? : " + str(res))
```

**输出:**

```
The original list is : ['gfg', 'is', 'bet']
Are strings mutually disjoint? : False
```