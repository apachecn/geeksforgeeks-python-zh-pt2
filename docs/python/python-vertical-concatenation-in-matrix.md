# Python–矩阵中的垂直连接

> 原文:[https://www . geesforgeks . org/python-垂直-矩阵串联/](https://www.geeksforgeeks.org/python-vertical-concatenation-in-matrix/)

给定一个字符串矩阵，执行字符串的列连接，处理可变的列表长度。

> **输入**:[[“Gfg”，“good”]，[“is”，“for”]]
> **输出**:[‘Gfg’，‘good for’]
> **解释**:列式串接字符串，“Gfg”串接“is”等等。
> 
> **输入**:[[“Gfg”、“good”、“极客”]、[“is”、“for”、“best”]]
> **输出**:[“Gfg”、“goodfor”、“极客 best”]
> **解释**:列式串接字符串，“Gfg”串接“is”等等。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们迭代所有的列并执行连接。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Vertical Concatenation in Matrix
# Using loop

# initializing lists
test_list = [["Gfg", "good"], ["is", "for"], ["Best"]]

# printing original list
print("The original list : " + str(test_list))

# using loop for iteration
res = []
N = 0
while N != len(test_list):
    temp = ''
    for idx in test_list:

        # checking for valid index / column
        try: temp = temp + idx[N]
        except IndexError: pass
    res.append(temp)
    N = N + 1

res = [ele for ele in res if ele]

# printing result 
print("List after column Concatenation : " + str(res))
```

**Output**

```py
The original list : [['Gfg', 'good'], ['is', 'for'], ['Best']]
List after column Concatenation : ['GfgisBest', 'goodfor']

```

**方法 2:使用 join() +列表理解+zip _ long()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 zip _ longest 处理空索引值，join()用于执行连接任务。列表理解驱动着一行逻辑。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Vertical Concatenation in Matrix
# Using join() + list comprehension + zip_longest()
from itertools import zip_longest

# initializing lists
test_list = [["Gfg", "good"], ["is", "for"], ["Best"]]

# printing original list
print("The original list : " + str(test_list))

# using join to concaternate, zip_longest filling values using 
# "fill"
res = ["".join(ele) for ele in zip_longest(*test_list, fillvalue ="")]

# printing result 
print("List after column Concatenation : " + str(res))
```

**Output**

```py
The original list : [['Gfg', 'good'], ['is', 'for'], ['Best']]
List after column Concatenation : ['GfgisBest', 'goodfor']

```