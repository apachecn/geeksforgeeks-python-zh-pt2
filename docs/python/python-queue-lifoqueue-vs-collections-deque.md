# python–伫列。LIFOQueue vs 集合。deque〔t1〕

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-queue-LIFO queue-vs 集合-deque/

*LIFOQueue* 和 *Deque* 都可以使用 Python 中内置的模块 *Queue* 和 *Collections* 来使用，两者都是数据结构，用途广泛，但用途不同。在本文中，我们将考虑两种*队列的区别。后进先出队列*和*集合。关于可用性、执行时间、工作、实现等方面的德格*。在 Python 中。

[**排队。后进先出队列:**](https://www.geeksforgeeks.org/stack-in-python/) 模块*队列*提供了一个后进先出队列，在技术上作为堆栈工作。它通常用于同一进程中不同线程之间的通信。

**下面是一个描述** ***后进先出的实现的程序。队列*** **:**

## 蟒蛇 3

```
# Import required module
import queue

# Initialize LIFO Queue
LIFOq = queue.LifoQueue(maxsize=3)

# qsize() give the maxsize of
# the Queue
print(LIFOq.qsize())

# Data Inserted as 5->9->1->7,
# same as Queue
LIFOq.put(1)
LIFOq.put(2)
LIFOq.put(3)

# Displaying if the Queue is full
print("Full: ", LIFOq.full())

# Displaying size of queue
print("Size: ", LIFOq.qsize())

# Data will be accessed in the
# reverse order Reverse of that
# of Queue
print(LIFOq.get())
print(LIFOq.get())
print(LIFOq.get())

# Displaying if the queue is empty or not
print("Empty: ", LIFOq.empty())
```

**输出:**

```
0
Full:  True
Size:  3
3
2
1
Empty:  True
```

Python 中的[**collections . de Queue:**](https://www.geeksforgeeks.org/deque-in-python/)de Queue(双端队列)使用模块 *collections* 实现。这种数据结构主要用于队列。先进先出队列机制由 *append()* 和 *popleft()* 实现。与列表相比，它的操作速度相当快。

**下面是一个说明** ***实现的程序***

## 蟒蛇 3

```
# Import required modules
import collections

# Initialize deque
Deque = collections.deque([10, 20, 30])

# Using append() to insert element at right end
# Inserts 0 at the end of deque
Deque.append(0)

# Printing modified deque
print("The deque after appending at right is:", Deque)

# Using appendleft() to insert element at left end
# Inserts 100 at the beginning of deque
Deque.appendleft(100)

# Printing modified deque
print("The deque after appending at left is: ", Deque)

# Using pop() to delete element from right end
# Deletes 0 from the right end of deque
Deque.pop()

# Printing modified deque
print("The deque after deleting from right is:", Deque);

# Using popleft() to delete element from left end
# Deletes 100 from the left end of deque
Deque.popleft()

# Printing modified deque
print("Queue:", Deque)
```

**输出:**

```
The deque after appending at right is: deque([10, 20, 30, 0])
The deque after appending at left is:  deque([100, 10, 20, 30, 0])
The deque after deleting from right is: deque([100, 10, 20, 30])
Queue: deque([10, 20, 30])
```

### **立峰队列和德格的区别:**

<figure class="table">

| 不，先生。 | LIFO 队列 | 出列 |
| --- | --- | --- |
| one | 它实现堆栈 | 它实现了一个双刃队列 |
| Two | 出现在*队列*模块中 | 出现在*集合*模块中 |
| three | 允许各种线程使用排队的数据或消息进行通信 | 只是为了成为一个数据结构 |
| four | 更少的功能(操作和方法) | 各种各样的功能(操作和方法) |
| five | 遵循后进先出原则 | 遵循先进先出原则 |
| six | 操作缓慢(执行时间长) | 高操作(非常短的执行时间) |
| six | 不常用，通常用于线程通信操作。 | 主要用于数据结构操作。 |

</figure>