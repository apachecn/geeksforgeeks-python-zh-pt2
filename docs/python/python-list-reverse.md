# Python 列表反向()

> 原文:[https://www.geeksforgeeks.org/python-list-reverse/](https://www.geeksforgeeks.org/python-list-reverse/)

Python List reverse()是 Python 编程语言中的一种内置方法，可以将[列表](https://www.geeksforgeeks.org/python-list/)中的对象反转到位。

> **语法:**
> 
> list_name.reverse()
> 
> **参数:**
> 
> 没有参数。
> 
> **返回:**
> 
> reverse()方法不返回任何值，但从列表中反转给定的对象。
> 
> **错误:**
> 
> 当使用列表以外的任何内容代替列表时，它将返回一个属性错误

### 示例 1:反转列表

## 蟒蛇 3

```
# Python3 program to demonstrate the
# use of reverse method

# a list of numbers
list1 = [1, 2, 3, 4, 1, 2, 6]
list1.reverse()
print(list1)

# a list of characters
list2 = ['a', 'b', 'c', 'd', 'a', 'a']
list2.reverse()
print(list2)
```

**输出:**

```
[6, 2, 1, 4, 3, 2, 1]
['a', 'a', 'd', 'c', 'b', 'a']
```

### **例 2:** 演示**反()方法**中的错误

## **蟒蛇 3**

```
# Python3 program to demonstrate the
# error in reverse() method

# error when string is used in place of list
string = "abgedge"
string.reverse()
print(string)
```

****输出:****

```
Traceback (most recent call last):
  File "/home/b3cf360e62d8812babb5549c3a4d3d30.py", line 5, in 
    string.reverse() 
AttributeError: 'str' object has no attribute 'reverse' 
```

### ****例 3:实际应用****

**给定一个数字列表，检查该列表是否是一个[回文](https://www.geeksforgeeks.org/c-program-check-given-string-palindrome/)。**

> ****注:**回文——向后读和向前读一样的序列。**

## **蟒蛇 3**

```
# Python3 program for the
# practical application of reverse()

list1 = [1, 2, 3, 2, 1]

# store a copy of list
list2 = list1.copy() 

# reverse the list
list2.reverse()

# compare reversed and original list
if list1 == list2:
    print("Palindrome")
else:
    print("Not Palindrome")
```

****输出:****

```
Palindrome
```