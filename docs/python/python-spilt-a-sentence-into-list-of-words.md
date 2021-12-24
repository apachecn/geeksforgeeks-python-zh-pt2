# Python |将一个句子拆分成单词列表

> 原文:[https://www . geesforgeks . org/python-一句话变成一串单词/](https://www.geeksforgeeks.org/python-spilt-a-sentence-into-list-of-words/)

给定一个句子，编写一个 Python 程序，将给定的句子转换成单词列表。

**示例:**

```py
Input : ['Hello World']
Output : ['Hello', 'world']

Input : ['Geeks For geeks']
Output : ['Geeks', 'for', 'geeks']
```

Python 提供的将给定的句子列表转换成具有独立索引的单词的最简单方法是使用 [**split()**](https://www.geeksforgeeks.org/python-string-split/) 方法。这个方法将一个字符串分割成一个列表，其中每个单词都是一个列表项。为了获得所需的输出，我们有其他方法来使用这个函数。

**方法#1 :** 拆分第一个索引元素

## 蟒蛇 3

```py
# Python3 program to Convert single
# indexed list into multiple indexed list

def convert(lst):
    return (lst[0].split())

# Driver code
lst =  ["Geeks For geeks"]
print( convert(lst))
```

**Output:** 

```py
['Geeks', 'For', 'geeks']
```

**方法 2 :** 使用 for 循环
我们也可以使用 for 循环来拆分第一个元素。如果我们有一个以上的元素，这种方法也是有益的。

## 蟒蛇 3

```py
# Python3 program to Convert single
# indexed list into multiple indexed list

def convert(lst):
    return ([i for item in lst for i in item.split()])

# Driver code
lst =  ['Geeksforgeeks is a portal for geeks']
print( convert(lst))
```

**Output:** 

```py
['Geeksforgeeks', 'is', 'a', 'portal', 'for', 'geeks']
```

**方法#3 :** 使用 join()
我们可以拆分给定的列表，然后使用 join()函数进行连接。当列表中有字符串或单个字符串的列表时，我们也可以使用它。

## 蟒蛇 3

```py
# Python3 program to Convert single
# indexed list into multiple indexed list

def convert(lst):
    return ' '.join(lst).split()

# Driver code
lst =  ['Hello Geeks for geeks']
print( convert(lst))
```

**Output:** 

```py
['Hello', 'Geeks', 'for', 'geeks']
```