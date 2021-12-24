# Python 列表理解与生成器表达式

> 原文:[https://www . geesforgeks . org/python-list-explorations-vs-generator-expressions/](https://www.geeksforgeeks.org/python-list-comprehensions-vs-generator-expressions/)

**什么是列表理解？**
这是一种定义和创建列表的优雅方式。列表理解允许我们用较少的代码创建一个使用 for 循环的列表。通常需要 3-4 行代码，可以压缩成一行。

**示例:**

```
# initializing the list
list = []

for i in range(11):
    if i % 2 == 0:
        list.append(i)

# print elements
print(list)
```

**输出:**

```
 0 2 4 6 8 10
```

现在，同样的输出可以从一行代码中得到。

```
list = [i for i in range(11) if i % 2 == 0]
print(list)
```

**输出:**

```
 0 2 4 6 8 10
```

**什么是生成器表达式？**
生成器表达式有点类似于列表理解，但前者不构造列表对象。生成器不是创建一个列表并将整个序列保存在内存中，而是根据需要生成下一个元素。
当一个带有返回语句的普通函数被调用时，只要它得到一个返回语句，它就终止。但是带有 yield 语句的函数保存了函数的状态，并且可以在下次调用该函数时从相同的状态中提取。
生成器表达式允许我们创建一个没有 yield 关键字的生成器。

**句法差异:**括号代替方括号。

```
# List Comprehension
list_comprehension = [i for i in range(11) if i % 2 == 0]

print(list_comprehension)
```

**输出:**

```
 0 2 4 6 8 10
```

```
# Generator Expression
generator_expression = (i for i in range(11) if i % 2 == 0)

print(generator_expression)
```

**输出:**

```
<generator object  at 0x000001452B1EEC50>

```

在上面的例子中，如果我们想要打印生成器表达式的输出，我们可以简单地在生成器对象上迭代它。

```
for i in generator_expression:
    print(i, end=" ")
```

**输出:**

```
0 2 4 6 8 10
```

**那么生成器表达式和列表理解有什么区别呢？**
生成器一次生成一个项目，并且仅在需要时生成项目。然而，在列表理解中，Python 为整个列表保留内存。因此，我们可以说生成器表达式比列表更节省内存。
我们可以在下面的例子中看到这一点。

```
# import getsizeof from sys module
from sys import getsizeof

comp = [i for i in range(10000)]
gen = (i for i in range(10000))

#gives size for list comprehension
x = getsizeof(comp) 
print("x = ", x)

#gives size for generator expression
y = getsizeof(gen) 
print("y = ", y)
```

**输出:**

```
x =  87624
y =  88

```

我们刚刚看到生成器表达式具有内存效率。但是，它们也有时间效率吗？让我们用一个例子来验证这一点。

```
#List Comprehension: 
import timeit

print(timeit.timeit('''list_com = [i for i in range(100) if i % 2 == 0]''', number=1000000))
```

**输出:**

```
8.118047142050102
```

```
#Generator Expression:
import timeit

print(timeit.timeit('''gen_exp = (i for i in range(100) if i % 2 == 0)''', number=1000000))
```

**输出:**

```
0.7548244756850693
```

执行时间有显著差异。因此，生成器表达式比列表理解更快，因此时间效率高。