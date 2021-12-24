# Python–对元组字典进行排序

> 原文:[https://www . geesforgeks . org/python-排序-元组字典/](https://www.geeksforgeeks.org/python-sorting-a-dictionary-of-tuples/)

在本文中，我们将对元组字典进行排序。元组字典意味着元组是字典中的值，或者元组是字典中的键。

**例**:

```
{'key1': (1, 2, 3), 'key2': (3, 2, 1),.............}
or
{ (1, 2, 3):value, (3, 2, 1):value,.............}
```

## 方法 1:使用[排序()](https://www.geeksforgeeks.org/sorted-function-python/)方法

使用这种方法，我们可以根据键、值和项对元组字典进行排序，我们可以使用 for 循环对元组字典中的所有元素进行排序。

**语法**:

```
To sort based on items:
for i in sorted(dictionary.items()) :
     print(i, end = " ")

To sort based on keys:
for i in sorted(dictionary.keys()) :
     print(i, end = " ") 

To sort based on values:
for i in sorted(dictionary.values()) :
     print(i, end = " ")           
```

**例 1:**

## 蟒蛇 3

```
# declare a dictionary of tuple with student data
data = {'student1': ('bhanu', 10), 'student4': ('uma', 12),
        'student3': ('suma', 11), 'student2': ('ravi', 11),
        'student5': ('gayatri', 9)}

# sort student dictionary based  on items
for i in sorted(data.items()):
    print(i, end=" ")
print()

# sort student dictionary based  on values
for i in sorted(data.values()):
    print(i, end=" ")
print()

# sort student dictionary based  on keys
for i in sorted(data.keys()):
    print(i, end=" ")
```

**输出:**

> (‘student 1’，(‘bhanu’，10))(‘student 2’，(‘ravi’，11))(‘student 3’，(‘suma’，11))(‘student 4’，(‘uma’，12))(‘student 5’，(‘gayatri’，9))
> 
> (' bhanu '，10)(' gay atri '，9)(' ravi '，11)(' sum '，11)(' uma '，12))
> 
> 学生 1 学生 2 学生 3 学生 4 学生 5

我们也可以用关键字作为元组来制作元组字典。

**例 2:**

Python 程序，以元组为关键字创建元组字典，并应用 sorted()函数

## 蟒蛇 3

```
# declare a dictionary of tuple with student data
data = {('bhanu', 10): 'student1',
        ('uma', 12): 'student4', 
        ('suma', 11): 'student3', 
        ('ravi', 11): 'student2',
        ('gayatri', 9): 'student5'}

# sort student dictionary based  on items
for i in sorted(data.items()):
    print(i, end=" ")
print()

# sort student dictionary based  on values
for i in sorted(data.values()):
    print(i, end=" ")
print()

# sort student dictionary based  on keys
for i in sorted(data.keys()):
    print(i, end=" ")
```

**输出:**

> (“bhanu”，10)、“student 1”)(“gayatri”，9)、“student 5”)(“ravi”，11)、“student 2”)(“suma”，11)、“student 3”)(“uma”，12)、“student4”)
> 
> 学生 1 学生 2 学生 3 学生 4 学生 5
> 
> (' bhanu '，10)(' gay atri '，9)(' ravi '，11)(' sum '，11)(' uma '，12))

## 方法二:使用[命令](https://www.geeksforgeeks.org/ordereddict-in-python/)

OrderedDict 在 collections 模块中可用，该模块用于使用 sorted()方法对字典进行排序。

**语法**:

```
To sort based on values:
OrderedDict(sorted(dictionary.values())

To sort based on items:
OrderedDict(sorted(dictionary.items())
```

**示例 1:** 对元组字典进行排序的 Python 程序

## 蟒蛇 3

```
# import oOrderedDict module
from collections import OrderedDict

# declare a dictionary of tuple with student data
data = {'student3': ('bhanu', 10), 'student2': ('uma', 12),
        'student4': ('sai', 11), 'student1': ('suma', 11)}

# sort student dictionary of tuple based
# on values using OrderedDict
print(OrderedDict(sorted(data.values())))
print()

# sort student dictionary of tuple based
# on items using OrderedDict
print(OrderedDict(sorted(data.items())))
```

**输出:**

> order ed CT((bhanu，10)，(' sai '，11)，(' sum '，11)，(' one '，12))
> 
> ordereddct([(' student 1 '，(' suma '，11))，(' student2 '，(' uma '，12))，(' student3 '，(' bhanu '，10))，(' student4 '，(' sai '，11))])

**示例 2:** Python 程序，用于对元组字典进行排序，其中元组将是字典中的关键字

## 蟒蛇 3

```
# import orderedDict module
from collections import OrderedDict

# declare a dictionary of tuple with student data
data = {('bhanu', 10): 'student1', 
        ('uma', 12): 'student4', 
        ('suma', 11): 'student3', 
        ('ravi', 11): 'student2',
        ('gayatri', 9): 'student5'}

# sort student dictionary of tuple based 
# on items using OrderedDict
print(OrderedDict(sorted(data.items())))
```

**输出:**

> ordereddct([(“bhanu”，10)、“student1”)、(“gayatri”，9)、“student5”)、(“ravi”，11)、“student2”)、(“suma”，11)、“student3”)、(“uma”，12)、“student 4”)])