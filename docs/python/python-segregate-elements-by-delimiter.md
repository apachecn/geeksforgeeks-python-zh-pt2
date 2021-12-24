# Python–通过分隔符

分隔元素

> 原文:[https://www . geesforgeks . org/python-按分隔符分隔元素/](https://www.geeksforgeeks.org/python-segregate-elements-by-delimiter/)

给定字符串列表，用分隔符分隔每个字符串，并输出不同的前缀和后缀列表。

> **输入**:test _ list =[“7 $ 2”、“8$5”、“9 $ 1”]，delim =“{ content }”# x201；
> **输出** : ['7 '，' 8 '，' 9']，['2 '，' 5 '，' 1']
> **解释**:不同的“{content}”前缀后缀列表；
> 
> **输入**:test _ list =[“7 * 2”、“8*5”、“9 * 1”]，delim =“*”
> **输出**:[‘7’、‘8’、‘9’]，[‘2’、‘5’、‘1’]
> **解释**:前缀和后缀“*”的不同列表

**方法一:使用列表理解+拆分()**

是执行此任务的方法之一。在本文中，我们使用 split()执行分离，split 的第一部分被编译为一个列表理解，然后是另一个。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Segregate elements by delimiter
# Using list comprehension + split()

# initializing list
test_list = ["7$2", "8$5", "9$1", "8$10", "32$6"]

# printing original list
print("The original list : " + str(test_list))

# using delim 
delim = "{content}quot;

# using split() to split and different list comprehension
# assigns results to different lists 
res1, res2 = [ele.split(delim)[0] for ele in test_list], [ele.split(delim)[1] for ele in test_list]

# printing result 
print("The filtered list 1 : " + str(res1))
print("The filtered list 2 : " + str(res2))
```

**Output**

```
The original list : ['7$2', '8$5', '9$1', '8$10', '32$6']
The filtered list 1 : ['7', '8', '9', '8', '32']
The filtered list 2 : ['2', '5', '1', '10', '6']

```

**方法 2:使用 map() + list + zip() +生成器表达式**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 map()扩展了列表构造逻辑，并使用 zip()对每个元素执行 split()功能。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Segregate elements by delimiter
# Using map() + list + zip() + generator expression

# initializing list
test_list = ["7$2", "8$5", "9$1", "8$10", "32$6"]

# printing original list
print("The original list : " + str(test_list))

# using delim 
delim = "{content}quot;

# map() used to cast different sections to different lists
res1, res2 = map(list, zip(*(ele.split(delim) for ele in test_list)))

# printing result 
print("The filtered list 1 : " + str(res1))
print("The filtered list 2 : " + str(res2))
```

**Output**

```
The original list : ['7$2', '8$5', '9$1', '8$10', '32$6']
The filtered list 1 : ['7', '8', '9', '8', '32']
The filtered list 2 : ['2', '5', '1', '10', '6']

```