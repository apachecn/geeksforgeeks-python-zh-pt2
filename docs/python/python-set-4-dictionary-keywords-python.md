# Python |第 4 集(字典，Python 中的关键词)

> 原文:[https://www . geesforgeks . org/python-set-4-dictionary-keywords-python/](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)

在前两篇文章([第 2 集](https://www.geeksforgeeks.org/python-set-2-variables-expressions-conditions-and-functions/)[第 3 集](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/))中，我们讨论了 python 的基础知识。在本文中，我们将学习更多关于 python 的知识，感受 python 的强大。

### **Python 中的字典**

在 python 中，字典类似于其他语言中的哈希或映射。它由键值对组成。该值可以通过字典中的唯一键来访问。

## 蟒蛇 3

```py
# Create a new dictionary
d = dict() # or d = {}

# Add a key - value pairs to dictionary
d['xyz'] = 123
d['abc'] = 345

# print the whole dictionary
print (d)

# print only the keys
print (d.keys())

# print only values
print (d.values())

# iterate over dictionary
for i in d :
    print ("%s  %d" %(i, d[i]))

# another method of iteration
for index, key in enumerate(d):
    print (index, key, d[key])

# check if key exist
print ('xyz' in d)

# delete the key-value pair
del d['xyz']

# check again
print ("xyz" in d)
```

**输出:**

```py
{'xyz': 123, 'abc': 345}
['xyz', 'abc']
[123, 345]
xyz 123
abc 345
0 xyz 123
1 abc 345
True
False
```

### **中断，继续，用 Python 传递**

*   **break:** 带你脱离当前循环。
*   **继续:**结束循环中的当前迭代，并移动到下一个迭代。
*   **pass:**pass 语句不做任何事情。它可以在需要语句时使用。但是程序不需要任何动作。

它通常用于创建最小类。

## 蟒蛇 3

```py
# Function to illustrate break in loop
def breakTest(arr):
    for i in arr:
        if i == 5:
            break
        print (i)
    # For new line
    print("")

# Function to illustrate continue in loop
def continueTest(arr):
    for i in arr:
        if i == 5:
            continue
        print (i)

    # For new line
    print("")

# Function to illustrate pass
def passTest(arr):
        pass

# Driver program to test above functions

# Array to be used for above functions:
arr = [1, 3 , 4, 5, 6 , 7]

# Illustrate break
print ("Break method output")
breakTest(arr)

# Illustrate continue
print ("Continue method output")
continueTest(arr)

# Illustrate pass- Does nothing
passTest(arr)
```

**输出:**

```py
Break method output
1 3 4
Continue method output
1 3 4 6 7
```

### **贴图、滤镜、λ**

*   **map:**map()函数对 iterable 的每个成员应用一个函数，并返回结果。如果有多个参数，map()将返回一个由元组组成的列表，这些元组包含所有 iterables 中的相应项。
*   **过滤器:**它接受一个返回真或假的函数，并将其应用于一个序列，只返回该函数返回真的序列成员的列表。
*   **lambda:** Python 提供了创建一个称为 lambda 函数的简单(内部不允许任何语句)匿名内联函数的能力。使用 lambda 和 map，一行中可以有两个 for 循环。

## 蟒蛇 3

```py
# python program to test map, filter and lambda
items = [1, 2, 3, 4, 5]

#Using map function to map the lambda operation on items
cubes = list(map(lambda x: x**3, items))
print(cubes)

# first parentheses contains a lambda form, that is 
# a squaring function and second parentheses represents
# calling lambda
print( (lambda x: x**2)(5))

# Make function of two arguments that return their product
print ((lambda x, y: x*y)(3, 4))

#Using filter function to filter all
# numbers less than 5 from a list
number_list = range(-10, 10)
less_than_five = list(filter(lambda x: x < 5, number_list))
print(less_than_five)
```

**输出:**

```py
[1, 8, 27, 64, 125]
25
12
[-10, -9, -8, -7, -6, -5, -4, -3, -2, -1, 0, 1, 2, 3, 4]
```

为了更清楚地了解 map、filter 和 lambda，您可以查看下面的示例:

## 蟒蛇 3

```py
#code without using map, filter and lambda

# Find the number which are odd in the list
# and multiply them by 5 and create a new list

# Declare a new list
x = [2, 3, 4, 5, 6]

# Empty list for answer
y = []

# Perform the operations and print the answer
for v in x:
    if v % 2:
        y += [v*5]
print (y)
```

**输出:**

```py
[15, 25]
```

使用 map、filter 和 lambda 可以在两行中执行相同的操作，如下所示:

## 蟒蛇 3

```py
#above code with map, filter and lambda

# Declare a list
x = [2, 3, 4, 5, 6]

# Perform the same operation as  in above post
y = map(lambda v : v * 5, filter(lambda u : u % 2, x))
print (y)
```

**输出:**

```py
[15, 25]
```

**参考文献:**

*   https://docs.python.org/2/tutorial/controlflow.html#break-and-continue-statements-and-else-clauses-on-loops
*   http://www.u.arizona.edu/~erdmann/mse350/topics/list_comprehensions.html

本文由 [**尼基尔·库马尔·辛格**](https://www.facebook.com/nikhilkumar.singh.don) 供稿

如果发现有不正确的地方，请写评论，或者想分享更多关于以上讨论话题的信息