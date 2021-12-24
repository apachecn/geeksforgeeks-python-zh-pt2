# Python |初始化列表哪个更快？

> 原文:[https://www . geeksforgeeks . org/python-哪个列表初始化速度更快/](https://www.geeksforgeeks.org/python-which-is-faster-to-initialize-lists/)

Python 是一种非常灵活的语言，其中单个任务可以通过多种方式执行，例如初始化列表可以通过多种方式执行。然而，这些看似相似的方法之间存在细微的差异。Python 因其简单性和可读性而广受欢迎，但与 C++或 Java 相比，它同样因速度慢而臭名昭著。“for”循环特别慢，而 map()和 filter()之类的方法更快，因为它们是用 c 语言编写的。知道更好更快的初始化列表的方法可能会让你在竞争性编程中稍有优势。

以下是 Python 中初始化列表的一些方法(我们创建大小为 1000 的列表，并用零初始化)。

**使用 for 循环并追加()**
我们创建一个空的 an 列表，并使用 append()方法运行 for 循环 n 次，以向列表中添加元素。

```
arr = []
for i in range(1000):
    arr.append(0)

```

**使用带有计数器变量的 while 循环**
这类似于上面的方法。然而，我们使用 while 循环来代替。

```
arr = []
i = 0
while(i<1000):
    arr.append(0)

```

**使用列表理解**
它由方括号组成，包含一个表达式，后跟一个 for 子句，以及一个可选的 if 子句。表达式可以是我们想要放在列表中的任何类型的对象。因为我们用零初始化列表，所以我们的表达式将只是 0。

```
arr = [0 for i in range(1000)]

```

**使用*运算符**
可以将*运算符用作[对象]*n，其中 n 是数组中的元素个数。

```
arr = [0]*1000

```

让我们看看他们每个人所花的时间。我们将计算这些方法中的每一个初始化 10000 个元素的数组超过 500 次所花费的平均时间。

```
# import time module to calculate times
import time

# initialize lists to save the times
forLoopTime = []
whileLoopTime = []
listComprehensionTime = []
starOperatorTime = []

# repeat the process for 500 times
# and calculate average of times taken.
for k in range(500): 

    # start time
    start = time.time()
    # declare empty list
    a = []
    # run a for loop for 10000 times
    for i in range(10000):
        a.append(0)
    # stop time
    stop = time.time()
    forLoopTime.append(stop-start)

    # start time
    start = time.time()
    # declare an empty list
    a = []
    i = 0
    # run a for loop 10000 times
    while(i<10000):
        a.append(0)
        i+= 1
    stop = time.time()
    whileLoopTime.append(stop-start)

    start = time.time()
    # list comprehension to initialize list
    a = [0 for i in range(10000)] 
    stop = time.time()
    listComprehensionTime.append(stop-start)

    start = time.time()
    # using the * operator
    a = [0]*10000 
    stop = time.time()
    starOperatorTime.append(stop-start)

print("Average time taken by for loop: " + str(sum(forLoopTime)/100))
print("Average time taken by while loop: " + str(sum(whileLoopTime)/100))
print("Average time taken by list comprehensions: " + str(sum(listComprehensionTime)/100))
print("Average time taken by * operator: " + str(sum(starOperatorTime)/100))    
```

**输出**

```
Average time taken by for loop: 0.012432687282562256
Average time taken by while loop: 0.017907898426055908
Average time taken by list comprehensions: 0.0034629487991333007
Average time taken by * operator: 0.0001951146125793457

```

注意:时间会因执行代码的平台而异。这些时间只是为了研究这些初始化方法的相对性能。

*   可以看出，for 和 while 循环所用的时间几乎与 for 循环具有轻微边缘的时间相同。
*   列表理解比 for 和 while 循环要好得多，前者快 3-5 倍左右。当我们试图创建一个从 1 到 1000 的数字列表时，可以看到这种差异的另一个例子。使用列表理解比使用 append()好得多。

    ```
    a = [i for  i in range(1, 1001)]
    ```

*   使用*运算符比其他方法快得多，这是初始化列表的方式

然而，使用*运算符的一个缺点是在声明 2d 数组时。使用该操作符将创建浅列表，即只创建一个列表对象，所有索引都将引用该对象。这可能会造成不必要的复杂情况。因此，使用列表理解是创建 2d 列表的更安全的方法。

```

Using * operator would create shallow lists
arr = [[0]*no_of_cols]*no_of_rows

Using list comprehensions is better for 2d arrays
arr = [[0 for i in range(no_of_cols)] for j in range(no_of_rows)]

```