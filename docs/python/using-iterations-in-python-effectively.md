# 有效利用 Python 中的迭代

> 原文:[https://www . geeksforgeeks . org/use-iterations-in-python-effective/](https://www.geeksforgeeks.org/using-iterations-in-python-effectively/)

先决条件:[Python 中的迭代器](https://www.geeksforgeeks.org/iterators-in-python/)

下面是使用迭代器的不同方法。

**C 风格方法:**这种方法需要迭代总数的先验知识。

```py
# A C-style way of accessing list elements
cars = ["Aston", "Audi", "McLaren"]
i = 0
while (i < len(cars)):
    print cars[i]
    i += 1
```

**输出:**

```py
Aston
Audi 
McLaren 

```

**要点:**

*   python 程序员很少使用这种循环方式。
*   这种 4 步的方法在单视图循环构造中不会产生紧凑性。
*   这在大规模程序或设计中也容易出错。
*   Python 中没有 C-Style for 循环，即像 for(int I = 0；I < n；i++)

**使用 for-in(或每个的[)样式:](https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/)**
该样式在 python 中使用，包含列表、字典、n 维数组等的迭代器。迭代器获取每个组件，并在循环时打印数据。迭代器在这个构造中自动递增/递减。

```py
# Accessing items using for-in loop

cars = ["Aston", "Audi", "McLaren"]
for x in cars:
    print x
```

**输出:**

```py
Aston
Audi 
McLaren 

```

有关不同数据类型的更多示例，请参见本中的[。](https://www.geeksforgeeks.org/iterators-in-python/)

**使用 range 函数进行索引:**我们也可以在 Python 中使用 Range()进行索引。

```py
# Accessing items using indexes and for-in

cars = ["Aston", "Audi", "McLaren"]
for i in range(len(cars)):
    print cars[i]
```

**输出:**

```py
Aston
Audi 
McLaren 

```

**Enumerate:**
Enumerate 是一个内置的 python 函数，它将输入作为迭代器、列表等，并返回一个包含索引和迭代器序列中该索引处数据的元组。例如，enumerate(cars)，返回一个迭代器，该迭代器将返回(0，cars[0])，(1，cars[1])，(2，cars[2])，等等。

```py
# Accessing items using enumerate()

cars = ["Aston" , "Audi", "McLaren "]
for i, x in enumerate(cars):
    print (x)
```

**输出:**

```py
Aston
Audi
McLaren 
```

下面的解决方案也有效。

```py
# Accessing items and indexes enumerate()

cars = ["Aston" , "Audi", "McLaren "]
for x in enumerate(cars):
    print (x[0], x[1])
```

**输出:**

```py
(0, 'Aston')
(1, 'Audi')
(2, 'McLaren ')
```

我们也可以直接打印 enumerate()的返回值，看看它返回了什么。

```py
# Printing return value of enumerate() 

cars = ["Aston" , "Audi", "McLaren "]
print enumerate(cars)
```

**输出:**

```py
[(0, 'Aston'), (1, 'Audi'), (2, 'McLaren ')]
```

枚举采用默认设置为零的参数 start。我们可以将该参数更改为任何我们喜欢的值。在下面的代码中，我们使用 start 作为 1。

```py
# demonstrating the use of start in enumerate

cars = ["Aston" , "Audi", "McLaren "]
for x in enumerate(cars, start=1):
    print (x[0], x[1])
```

**输出:**

```py
(1, 'Aston')
(2, 'Audi')
(3, 'McLaren ')
```

enumerate()有助于将访问每个数据项的解决方案嵌入到迭代器中，并获取每个数据项的索引。

**循环扩展:**
**【I)**单个循环构造的两个迭代器:在这种情况下，使用枚举函数，列表和字典将用于单个循环块中的每次迭代。让我们看看例子。

```py
# Two separate lists
cars = ["Aston", "Audi", "McLaren"]
accessories = ["GPS kit", "Car repair-tool kit"]

# Single dictionary holds prices of cars and 
# its accessories.
# First three items store prices of cars and
# next two items store prices of accessories.
prices = {1:"570000{content}quot;, 2:"68000{content}quot;, 3:"450000{content}quot;,
          4:"8900{content}quot;, 5:"4500{content}quot;}

# Printing prices of cars
for index, c in enumerate(cars, start=1):
    print "Car: %s Price: %s"%(c, prices[index])

# Printing prices of accessories
for index, a in enumerate(accessories,start=1):
    print ("Accessory: %s Price: %s"\
           %(a,prices[index+len(cars)]))
```

**输出:**

```py
Car: Aston Price: 570000$
Car: Audi Price: 68000$
Car: McLaren Price: 450000$
Accessory: GPS kit Price: 8900$
Accessory: Car repair-tool kit Price: 4500$

```

**ii) zip 函数(两个迭代器都在单循环构造中使用):**
该函数有助于将相似类型的迭代器(list-list 或 dict- dict 等)组合在同一个位置的数据项。它使用这些输入迭代器中最短的长度。其他长度更大的迭代器被跳过。如果迭代器为空，则返回 No 输出。

例如，对两个列表(迭代器)使用 zip 有助于组合一辆车及其所需的附件。

```py
# Python program to demonstrate the working of zip

# Two separate lists
cars = ["Aston", "Audi", "McLaren"]
accessories = ["GPS", "Car Repair Kit", 
               "Dolby sound kit"]

# Combining lists and printing
for c, a in zip(cars, accessories):
    print "Car: %s, Accessory required: %s"\
          %(c, a)
```

**输出:**

```py
Car: Aston, Accessory required: GPS
Car: Audi, Accessory required: Car Repair Kit
Car: McLaren, Accessory required: Dolby sound kit
```

与 zip 函数中的迭代器相反的是使用“*”运算符进行解压缩。

枚举函数和 zip 函数的使用有助于实现 python 中迭代逻辑的有效扩展，并解决一个巨大任务或问题的更多子问题。

```py
# Python program to demonstrate unzip (reverse 
# of zip)using * with zip function

# Unzip lists
l1,l2 = zip(*[('Aston', 'GPS'), 
              ('Audi', 'Car Repair'), 
              ('McLaren', 'Dolby sound kit') 
           ])

# Printing unzipped lists      
print(l1)
print(l2)
```

**输出:**

```py
('Aston', 'Audi', 'McLaren')
('GPS', 'Car Repair', 'Dolby sound kit')

```

**参考文献:**
1。[https://docs.python.org/2/library/functions.html#enumerate](https://docs.python.org/2/library/functions.html#enumerate)T5【2】。[https://docs.python.org/2/library/functions.html#zip](https://docs.python.org/2/library/functions.html#zip)

本文由 **克里希纳萨加尔·亚赫达帕奇** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。