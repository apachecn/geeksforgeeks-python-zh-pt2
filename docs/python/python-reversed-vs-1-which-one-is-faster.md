# Python–reversed()VS[::-1]，哪个更快？

> 原文:[https://www . geesforgeks . org/python-reversed-vs-1-哪一个更快/](https://www.geeksforgeeks.org/python-reversed-vs-1-which-one-is-faster/)

Python [**列出了**](https://www.geeksforgeeks.org/python-list/) 可以使用多种 *python* 方法进行反转比如使用 [**切片**](https://www.geeksforgeeks.org/python-reverse-slicing-of-given-string/) 方法或者使用 [**反转()**](https://www.geeksforgeeks.org/python-reversed-function/) 功能。本文讨论这两者是如何工作的，以及哪一个似乎更快，以及为什么。

**代码:**使用**切片**反转列表。

## 蟒 3

```
# Python code to reverse
# a list using slicing

ls = [110, 220, 330, 
      440, 550]
print('Original list :', ls)

# list reverse
ls = ls[::-1]

print('Reversed list elements :')
for element in ls:
  print(element)
```

**输出:**

```
Original list : [110, 220, 330, 440, 550]
Reversed list elements :
550
440
330
220
110
```

**说明:**切片中的格式【a : b : c】表示从 a 包含到 b 不包含，以 c 为增量计数，在上面的代码中，a 和 b 为空，c 为-1。所以它迭代整个列表，从最后一个元素计数到第一个元素，产生一个反向列表。

**代码:**使用**反向()**内置功能反向列表。

## 蟒 3

```
# Python code to reverse 
# a list using reversed()

ls = [110, 220, 330, 440, 550]
print('Original list :', ls)

# list reverse
ls = reversed(ls)
print('Iterator object :', ls)

print('Reversed list elements :')
for element in ls:
  print(element)
```

**输出:**

```
Original list : [110, 220, 330, 440, 550]
Iterator object : <list_reverseiterator object at 0x7fbd84e0b630>
Reversed list elements :
550
440
330
220
110
```

**解释:**Python 中内置的 reversed()函数返回的是迭代器对象，而不是整个列表。

## **结论:**

对于相对较大的列表，在时间限制下，似乎 reversed()函数比 slicing 方法执行得更快。这是因为 reversed()只返回一个迭代器，它以相反的顺序迭代原始列表，而不复制任何东西，而 slicing 创建一个全新的列表，从原始列表中复制每个元素。对于具有 **10 <sup>6</sup>** 值的列表，反向()的性能比切片方法好将近 20，000。如果需要存储数据的反向副本，则可以使用切片，但是如果只想以反向方式迭代列表，那么 reversed()无疑是更好的选择。