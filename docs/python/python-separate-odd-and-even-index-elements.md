# Python |分离奇偶索引元素

> 原文:[https://www . geesforgeks . org/python-分离奇偶索引元素/](https://www.geeksforgeeks.org/python-separate-odd-and-even-index-elements/)

Python 列表非常流行，无论你在编码什么类型的字段，你都必须处理列表及其各种应用。在这篇特别的文章中，我们讨论了分离奇数和偶数索引元素及其重构连接的方法。让我们讨论实现这一点的方法。

**方法#1:使用天真方法**
使用天真方法，这个任务可以通过使用循环来执行。可以使用两个容器，每个容器存储一个替换元素，然后将它们连接起来。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Separating odd and even index elements
# using naive method

# initializing list
test_list = [3, 6, 7, 8, 9, 2, 1, 5]

# printing original list
print("The original list : " + str(test_list))

# using naive method
# Separating odd and even index elements
odd_i = []
even_i = []
for i in range(0, len(test_list)):
    if i % 2:
        even_i.append(test_list[i])
    else :
        odd_i.append(test_list[i])

res = odd_i + even_i

# print result
print("Separated odd and even index list: " + str(res))
```

**Output**

```
The original list : [3, 6, 7, 8, 9, 2, 1, 5]
Separated odd and even index list: [3, 7, 9, 1, 6, 8, 2, 5]
```

**方法#2:使用列表切片**
使用列表切片方法可以更紧凑高效地轻松执行这个特定任务，这是解决这个问题的推荐方法。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Separating odd and even index elements
# Using list slicing

# initializing list
test_list = [3, 6, 7, 8, 9, 2, 1, 5]

# printing original list
print("The original list : " + str(test_list))

# Using list slicing
# Separating odd and even index elements
res = test_list[::2] + test_list[1::2]

# print result
print("Separated odd and even index list : " + str(res))
```

**Output**

```
The original list : [3, 6, 7, 8, 9, 2, 1, 5]
Separated odd and even index list : [3, 7, 9, 1, 6, 8, 2, 5]
```