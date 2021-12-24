# Python 中不重复从列表中随机选择元素

> 原文:[https://www . geesforgeks . org/python 中不重复从列表中随机选择元素/](https://www.geeksforgeeks.org/randomly-select-elements-from-list-without-repetition-in-python/)

`random`模块中 Python 的内置模块用于处理随机数据。`random`模块提供各种方法，从列表、元组、集合、字符串或字典中随机选择元素，无需任何重复。下面是一些方法，它们描述了从列表中随机选择元素而不重复，方法如下:

**方法 1:** 使用[随机样本()](https://www.geeksforgeeks.org/python-random-sample-function/)

使用`random`模块中的`sample()`方法。`sample()`是随机模块的一种内置方法，它将选择的顺序和数量作为参数，并返回从顺序中选择的特定长度的项目列表，即列表、元组、字符串或集合。它用于从项目列表中随机选择，无需任何替换。
**例 1:**

```
# importing the required module
import random

# list of items
List = [10, 20, 30, 40, 50, 40,
        30, 20, 10]

# using the sample() method
UpdatedList = random.sample(List, 3)

# displaying random selections from 
# the list without repetition
print(UpdatedList)
```

**输出:**

```
[50, 20, 10]

```

我们也可以对一个数字序列使用`sample()`方法，但是，选择的数量应该大于序列的大小。
**例 2:**

```
# importing the required module
import random

# using the sample() method on a
# sequence of numbers
UpdatedList = random.sample(range(1, 100), 5)

# displaying random selections without
# repetition
print(UpdatedList)
```

**输出:**

```
[51, 50, 97, 22, 6]

```

**方法 2:** 使用[随机选择()](https://www.geeksforgeeks.org/random-choices-method-in-python/)

使用`random`库中的`choices()`方法，`choices()`方法需要列表中的两个参数，k(选择数)通过替换从列表中返回多个随机元素。但是，我们需要将列表转换为集合，以避免元素重复。
**例 1:**

```
# importing the required module
import random

# converting the list into a set
Set = set([10, 20, 30, 40, 50, 40,
          30, 20, 10])

# using the choices() method on the 
# given dataset
UpdatedList = random.choices(list(Set), k = 3)

# displaying random selections without 
# repetition
print(UpdatedList)
```

**输出:**

```
[30, 20, 40]

```

如果对唯一数字序列应用`choices()`方法，那么只有当`k`参数(即选择数)大于列表的大小时，它才会返回唯一随机选择的列表。
T3】例 2:

```
# importing the required module
import random

# converting the list into set
List = [i for i in range(1, 100)]

# using the choices() method on a
# sequence of numbers
UpdatedList = random.choices(List, k = 5)

# displaying random selections without
# repetition
print(UpdatedList)
```

**输出:**

```
[46, 32, 85, 12, 68]

```

**方法 3:** 使用[随机选择()](https://www.geeksforgeeks.org/python-numbers-choice-function/)

使用`random`模块中的`choice()`方法，`choice()`方法从列表、元组或字符串中返回单个随机项。
以下是在项目列表中使用`choice()`方法的程序。
**例 1:**

```
# importing the required module
import random

# list of items
List = [10, 20, 30, 40, 50, 40, 
        30, 20, 10]

# using the choice() method to return a
# single item from the dataset
print(random.choice(List))
```

**输出:**

```
20

```

下面是一个程序，其中选择方法被用于数字序列。
**例 2:**

```
# importing the required module
import random

# using the choice() method to return a
# single item from the dataset
print(random.choice(range(1, 100)))
```

**输出:**

```
56
```