# 使用 get()方法从元素列表中创建 Python 字典

> 原文:[https://www . geesforgeks . org/use-get-method-to-create-in-python-dictionary-from-list-of-elements/](https://www.geeksforgeeks.org/use-get-method-to-create-a-dictionary-in-python-from-a-list-of-elements/)

**先决条件:**[Python 中字典的 Get()方法](https://www.geeksforgeeks.org/get-method-dictionaries-python/)

从我们可以使用 for 循环的项目列表中创建字典的简单方法。为了更好的理解，请看下面的例子。

**示例:**

```py
li =['a', 'b', 'c', 'a', 'd', 'e', 'b', 'a']
di ={}

for ele in li:

    # Increase the value of key
    # if exists
    if ele in di:
        di[ele]= di[ele]+1
    else:

        # Insert the new key:value
        # pair
        di[ele]= 1

print(di)
```

**输出:**

```py
{'a': 3, 'b': 2, 'c': 1, 'd': 1, 'e': 1}
```

在上面的代码中，循环用于迭代列表中的元素。如果该关键字已经存在于字典中，那么它的值将增加 1，否则它将在字典中为该元素创建一个新的关键字，并为其赋值 1。

可以使用的另一种方法是使用 Python 库中内置的`.get()`函数。为了更好的理解

```py
li =['a', 'b', 'c', 'a', 'd', 'e', 'b', 'a']
di ={}

for ele in li:
    di[ele]= di.get(ele, 0)+1

print(di)
```

，请看下面的例子

**输出:**

```py
{'a': 3, 'b': 2, 'c': 1, 'd': 1, 'e': 1}
```

在上面的代码中，循环用于迭代列表中的元素。第 5 行的代码为列表中的每个元素创建一个键。如果该键已经存在于字典中，那么它会将 1 添加到它的值中，否则它会创建一个对应于该元素的新键，并将 0 作为默认值分配给它。然后加 1 增加计数。