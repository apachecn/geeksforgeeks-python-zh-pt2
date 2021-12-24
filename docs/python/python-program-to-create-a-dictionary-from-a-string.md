# Python 程序从字符串创建字典

> 原文:[https://www . geesforgeks . org/python-program-to-create-a-dictionary-from-string/](https://www.geeksforgeeks.org/python-program-to-create-a-dictionary-from-a-string/)

[python 中的字典](https://www.geeksforgeeks.org/python-dictionary/)是一种非常有用的数据结构，很多时候我们会看到关于将字符串转换为字典的问题。
那么，让我们讨论一下如何解决这个问题。
**方法# 1:** 使用 eval()
如果我们得到一个完全像字典对象的字符串输入**(如果字符串看起来像 python 中的字典)，那么我们可以很容易地使用 Python 中的
[eval()](https://contribute.geeksforgeeks.org/eval-in-python/) 将其转换为字典。**

```py
# Python3 code to convert 
# a string to a dictionary

# Initializing String 
string = "{'A':13, 'B':14, 'C':15}"

# eval() convert string to dictionary
Dict = eval(string)
print(Dict)
print(Dict['A'])
print(Dict['C'])
```

**Output:**

```py
{'C': 15, 'B': 14, 'A': 13}
13
15

```

**方法 2:** 使用 python 中的[生成器表达式](https://contribute.geeksforgeeks.org/python-list-comprehensions-vs-generator-expressions/)
如果我们得到的字符串输入不完全类似于字典对象，那么我们可以使用生成器表达式将其转换为字典。

```py
# Python3 code to convert 
# a string to a dictionary

# Initializing String 
string = "A - 13, B - 14, C - 15"

# Converting string to dictionary
Dict = dict((x.strip(), y.strip())
             for x, y in (element.split('-') 
             for element in string.split(', ')))

print(Dict)
print(Dict['A'])
print(Dict['C'])
```

**Output:**

```py
{'C': '15', 'A': '13', 'B': '14'}
13
15

```

上面给出的代码没有将整数转换为 int 类型，

如果**整数键存在**，那么第 8 行就可以了

```py
string = "11 - 13, 12 - 14, 13 - 15"

Dict = dict((x.strip(), int(y.strip())) 
             for x, y in (element.split('-') 
             for element in string.split(', ')))

print(Dict)
```

**Output:**

```py
{'13': 15, '12': 14, '11': 13}

```