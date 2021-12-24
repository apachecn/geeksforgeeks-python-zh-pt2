# Python 中的堆栈和队列

> 原文:[https://www.geeksforgeeks.org/stack-and-queues-in-python/](https://www.geeksforgeeks.org/stack-and-queues-in-python/)

先决条件:[列出](https://www.geeksforgeeks.org/list-methods-python/)和[蟒蛇](https://www.geeksforgeeks.org/deque-in-python/)中的得克。

与 C++ STL 和 Java Collections 不同，Python 确实为[栈](https://www.geeksforgeeks.org/stack-data-structure/)和[队列](https://www.geeksforgeeks.org/queue-data-structure/)提供了特定的类/接口。下面是用 Python 实现的不同方法

**1)使用列表**
**堆叠**按照“后进先出”的原则工作。此外，Python 中内置的函数使代码变得简短。要将一个项目添加到列表的顶部，即推送一个项目，我们使用 **append()** 函数，要弹出一个元素，我们使用 **pop()** 函数。这些功能在终端操作中安静、高效、快速地工作。

我们来看一个例子，试着理解 push()和 pop()函数的工作原理:
例子:

```
# Python code to demonstrate Implementing 
# stack using list
stack = ["Amar", "Akbar", "Anthony"]
stack.append("Ram")
stack.append("Iqbal")
print(stack)

# Removes the last item
print(stack.pop())

print(stack)

# Removes the last item
print(stack.pop())

print(stack)
```

**Output:**

```
['Amar', 'Akbar', 'Anthony', 'Ram', 'Iqbal']
Iqbal
['Amar', 'Akbar', 'Anthony', 'Ram']
Ram
['Amar', 'Akbar', 'Anthony']

```

**排队**按照“先进先出”的原则工作。下面是队列的实现列表。我们使用 pop(0)从列表中移除第一项。

```
# Python code to demonstrate Implementing 
# Queue using list
queue = ["Amar", "Akbar", "Anthony"]
queue.append("Ram")
queue.append("Iqbal")
print(queue)

# Removes the first item
print(queue.pop(0))

print(queue)

# Removes the first item
print(queue.pop(0))

print(queue)
```

**Output:**

```
['Amar', 'Akbar', 'Anthony', 'Ram', 'Iqbal']
Amar
['Akbar', 'Anthony', 'Ram', 'Iqbal']
Akbar
['Anthony', 'Ram', 'Iqbal']

```

**2)使用德格**
在堆栈的情况下，列表实现工作正常，并且在 O(1)时间内提供了 append()和 pop()。当我们使用 deque 实现时，我们得到相同的时间复杂度。

```
# Python code to demonstrate Implementing 
# Stack using deque
from collections import deque
queue = deque(["Ram", "Tarun", "Asif", "John"])
print(queue)
queue.append("Akbar")
print(queue)
queue.append("Birbal")
print(queue)
print(queue.pop())                 
print(queue.pop())                 
print(queue)
```

**Output:**

```
deque(['Ram', 'Tarun', 'Asif', 'John'])
deque(['Ram', 'Tarun', 'Asif', 'John', 'Akbar'])
deque(['Ram', 'Tarun', 'Asif', 'John', 'Akbar', 'Birbal'])
Birbal
Akbar
deque(['Ram', 'Tarun', 'Asif', 'John'])

```

但是说到队列，上面的列表实现效率不高。当 pop()从慢的列表开始时在队列中。这是由于 list 的属性造成的，list 在结束操作时很快，但在开始操作时很慢，因为所有其他元素都必须一个接一个地移动。
所以，比起 list，我们更喜欢使用 queue，list 是专门设计的，可以从前端和后端快速追加和弹出。

让我们看一个例子，并尝试使用集合来理解队列。

```
# Python code to demonstrate Implementing 
# Queue using deque
from collections import deque
queue = deque(["Ram", "Tarun", "Asif", "John"])
print(queue)
queue.append("Akbar")
print(queue)
queue.append("Birbal")
print(queue)
print(queue.popleft())                 
print(queue.popleft())                 
print(queue)
```

**Output:**

```
deque(['Ram', 'Tarun', 'Asif', 'John'])
deque(['Ram', 'Tarun', 'Asif', 'John', 'Akbar'])
deque(['Ram', 'Tarun', 'Asif', 'John', 'Akbar', 'Birbal'])
Ram
Tarun
deque(['Asif', 'John', 'Akbar', 'Birbal'])

```

本文由**钦莫伊·蕾恩卡**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。