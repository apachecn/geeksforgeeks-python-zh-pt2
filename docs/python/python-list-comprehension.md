# Python–列表理解

> 原文:[https://www.geeksforgeeks.org/python-list-comprehension/](https://www.geeksforgeeks.org/python-list-comprehension/)

Python 以鼓励开发人员和程序员编写高效、易于理解且几乎易于阅读的代码而闻名。该语言最有特色的方面之一是 python 列表和列表压缩特性，可以在一行代码中使用这些特性来构建强大的功能。

列表理解用于从元组、字符串、数组、列表等其他项创建新列表。列表理解由包含表达式的括号组成，该表达式与 for 循环一起对每个元素执行，以迭代每个元素。

**语法:**

> 新列表**=****【**表达式(元素)**为**元素**在**旧列表**中如果**条件**】**

## 列表理解的优势

*   比循环更节省时间和空间。
*   需要更少的代码行。
*   将迭代语句转换为公式。

## 列表理解与 For 循环

有多种方法可以遍历列表。然而，最常见的方法是将 [*用于*循环](https://www.geeksforgeeks.org/python-for-loops/)。让我们看看下面的例子:

## 蟒蛇 3

```py
# Empty list
List = []

# Traditional approach of iterating
for character in 'Geeks 4 Geeks!':
    List.append(character)

# Display list
print(List)
```

**输出:**

> ['G '，' e '，' e '，' k '，' s '，' '，' 4 '，' '，' G '，' e '，' e '，' k '，' s '，'！']

上面是迭代列表、字符串、元组等传统方法的实现。现在列表理解做同样的任务，也使程序更简单。

列表理解将用于循环的传统迭代方法转化为简单的公式，从而使它们易于使用。下面是遍历列表、字符串、元组等的方法。使用列表理解。

## 蟒蛇 3

```py
# Using list comprehension to iterate through loop
List = [character for character in 'Geeks 4 Geeks!']

# Displaying list
print(List)
```

**输出:**

> ['G '，' e '，' e '，' k '，' s '，' '，' 4 '，' '，' G '，' e '，' e '，' k '，' s '，'！']

列表理解在计算和编码空间和时间方面都比 for 循环更有效。通常，它们用一行代码编写。下面的程序描述了 for 循环和基于表现的列表理解之间的区别。

## 蟒蛇 3

```py
# Import required module
import time

# define function to implement for loop
def for_loop(n):
    result = []
    for i in range(n):
        result.append(i**2)
    return result

# define function to implement list comprehension
def list_comprehension(n):
    return [i**2 for i in range(n)]

# Driver Code 

# Calculate time takens by for_loop()
begin = time.time()
for_loop(10**6)
end = time.time()

# Display time taken by for_loop()
print('Time taken for_loop:',round(end-begin,2))

# Calculate time takens by list_comprehension()
begin = time.time()
list_comprehension(10**6)
end = time.time()

# Display time taken by for_loop()
print('Time taken for list_comprehension:',round(end-begin,2))
```

**输出:**

```py
Time taken for_loop: 0.56
Time taken for list_comprehension: 0.47
```

从上面的程序中，我们可以看到列表理解比循环理解要快得多。

## 嵌套列表理解

[嵌套列表理解](https://www.geeksforgeeks.org/nested-list-comprehensions-in-python/)只不过是另一个列表理解中的列表理解，与循环的嵌套非常相似。下面是实现嵌套循环的程序:

## 蟒蛇 3

```py
matrix = []

for i in range(3):

    # Append an empty sublist inside the list
    matrix.append([])

    for j in range(5):
        matrix[i].append(j)

print(matrix)
```

**输出:**

> [[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]

现在，通过使用嵌套列表理解，可以在更少的代码行中生成相同的输出。

## 蟒蛇 3

```py
# Nested list comprehension
matrix = [[j for j in range(5)] for i in range(3)]

print(matrix)
```

**输出:**

> [[0, 1, 2, 3, 4], [0, 1, 2, 3, 4], [0, 1, 2, 3, 4]]

## 列表理解和λ

[Lambda 表达式](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)不过是 Python 函数的简写表示。对 lambda 使用列表理解可以创建一个有效的组合。让我们看看下面的例子:

## 蟒蛇 3

```py
# using lambda to print table of 10
numbers = []

for i in range(1, 6):
    numbers.append(i*10)

print(numbers)
```

**输出:**

```py
[10, 20, 30, 40, 50]
```

这里，我们已经用 for 循环打印了 10 个表。

## 蟒蛇 3

```py
numbers= [i*10 for i in range(1,6)]

print(numbers)
```

**输出:**

```py
[10, 20, 30, 40, 50]
```

现在，我们只使用列表理解来显示 10 个表。

## 蟒蛇 3

```py
# using lambda to print table of 10
numbers = list(map(lambda i: i*10, [i for i in range(1,6)]))

print(numbers)
```

**输出:**

```py
[10, 20, 30, 40, 50]
```

最后，我们使用 lambda +列表理解来显示表 10。这种组合对于在更少的代码行中获得复杂问题的高效解决方案非常有用。

## 列表理解中的条件句

我们还可以在列表理解中添加条件语句。我们可以使用 [range()、](https://www.geeksforgeeks.org/python-range-function/) [运算符](https://www.geeksforgeeks.org/python-operators/)等创建列表。cal 还使用 [if 语句](https://www.geeksforgeeks.org/python-if-else/)对列表应用了一些条件。

**以下是一些描述使用列表理解而不是传统方法来迭代 iterables 的例子:**

### **示例 1:** 显示从 1 到 10 的数字的平方。

## 蟒蛇 3

```py
# Getting square of even numbers from 1 to 10
squares = [n**2 for n in range(1, 11) if n%2==0]

# Display square of even numbers
print(squares)
```

**输出:**

```py
[4, 16, 36, 64, 100]
```

### **示例 2:** 显示随机数列表中的偶数元素。

## 蟒蛇 3

```py
# Assign matrix
twoDMatrix = [[10, 20, 30],
              [40, 50, 60],
              [70, 80, 90]]

# Generate transpose
trans = [[i[j] for i in twoDMatrix] for j in range(len(twoDMatrix))]

print(trans)
```

**输出:**

```py
[++++[+10, 40, 70], [20, 50, 80], [30, 60, 90]]
```

### **示例 3:** 切换字符串中每个字符的大小写。

## 蟒蛇 3

```py
# Initializing string
string = 'Geeks4Geeks'

# Toggle case of each character
List = list(map(lambda i: chr(ord(i)^32), string))

# Display list
print(List)
```

**输出:**

> ['g '，' E '，' E '，' K '，' S '，' \x14 '，' g '，' E '，' E '，' K '，' S '，' \x01']

### **示例 4:** 反转元组中的每个字符串。

## 蟒蛇 3

```py
# Reverse each string in tuple
List = [string[::-1] for string in ('Geeks', 'for', 'Geeks')]

# Display list
print(List)
```

**输出:**

```py
['skeeG', 'rof', 'skeeG']
```

### **例 5:** 显示列表中所有奇数元素的位数之和。

## 蟒蛇 3

```py
# Explicit function
def digitSum(n):
    dsum = 0
    for ele in str(n):
        dsum += int(ele)
    return dsum

# Initializing list
List = [367, 111, 562, 945, 6726, 873]

# Using the function on odd elements of the list
newList = [digitSum(i) for i in List if i & 1]

# Displaying new list
print(newList)
```

**输出:**

```py
[16, 3, 18, 18]
```

### **要点**

*   对列表的理解是基于当前列表描述和构建列表的有效手段。
*   一般来说，列表理解比标准的列表形成函数和循环更轻量级和简单。
*   为了确保用户友好的代码，我们不应该为列表理解编写长代码。
*   列表的每个理解都可以在 for 循环中重写，但是在列表解释的上下文中，每个 for 循环都不能重写。