# 从 Python 集中检索元素

> 原文:[https://www . geeksforgeeks . org/retrieve-elements-from-python-set/](https://www.geeksforgeeks.org/retrieve-elements-from-python-set/)

**先决条件:** [蟒组](https://www.geeksforgeeks.org/sets-in-python/)

在本文中，我们将讨论如何在 Python 中从集合中检索元素。

## 示例 1:获取用于循环的所有元素

通过使用 for 循环迭代集合中的元素，我们可以得到所有集合元素。

**例**:

## 蟒蛇 3

```py
# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# display set elements using for loop
for i in data:
    print(i)

print("----")

# create a set with string elements
data1 = {"sravan", "harsha", "jyothika"}

# display set elements using for loop
for i in data1:
    print(i)
```

**输出**:

```py
7072
7074
7076
7058
7059
----
sravan
harsha
jyothika
```

## 示例 2:使用索引访问特定元素

在集合中，我们不能执行索引，首先，我们必须将该集合转换为列表，然后执行索引。所以我们用 list()函数把集合转换成列表。

**示例:**

## 蟒蛇 3

```py
# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# retrieve 1 st element
print(list(data)[0])

# retrieve 4 th  element
print(list(data)[3])

# retrieve last  element
print(list(data)[-1])
```

**输出**:

```py
7072
7058
7059
```

## 示例 3:检索最后一个元素

我们可以将其转换成列表，然后使用 [pop()](https://www.geeksforgeeks.org/python-list-pop/) 函数访问最后一个元素。这将获得最后一个元素，或者我们也可以使用 index = -1 来获得最后一个元素。

**例**:

## 蟒蛇 3

```py
# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# retrieve last element
print(list(data)[-1])

# retrieve last element
print(list(data).pop())
```

**输出**:

```py
7076
7076
```

## 示例 4:访问第一个元素

我们可以使用 [iter()](https://www.geeksforgeeks.org/python-iter-method/) 函数访问集合中的第一个项目，我们必须对其应用 [next()](https://www.geeksforgeeks.org/python-next-method/) 来获取第一个元素。

> **语法**:下一个(iter(set))

**例**:

## 蟒蛇 3

```py
# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# retrieve first element
print(next(iter(data)))
```

**输出**:

```py
7058
```

我们还可以使用 iteration_utilities 模块中的 first()方法，该方法将返回第一个元素。

> **语法**:第一个(集)

**例**:

## 蟒蛇 3

```py
# impport iteration_utilities
from iteration_utilities import first

# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# retrieve first element
print(first(data))
```

**输出**:

```py
7058
```

## 示例 5:检索随机元素

我们可以使用 [sample()](https://www.geeksforgeeks.org/python-random-sample-function/) 函数从一个集合中得到 n 个随机元素。这在随机模块中是可用的，这将返回一个样本元素列表。

**例**:

## 蟒蛇 3

```py
# import random module
import random

# create a set with integer elements
data = {7058, 7059, 7072, 7074, 7076}

# retrieve 2 random elements
print(random.sample(data, 2))

# retrieve 1 random element
print(random.sample(data, 1))

# retrieve 4 random elements
print(random.sample(data, 4))
```

**输出**:

```py
[7058, 7074]
[7072]
[7059, 7074, 7058, 7076]
```