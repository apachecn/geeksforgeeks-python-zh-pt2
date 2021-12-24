# 使用 graphlib Python 模块进行拓扑排序

> 原文:[https://www . geesforgeks . org/拓扑-排序-使用-graphlib-python-module/](https://www.geeksforgeeks.org/topological-sorting-using-graphlib-python-module/)

[拓扑排序](https://www.geeksforgeeks.org/topological-sorting/)是有向无环图顶点的线性排序。对于每个有向边 u ^ v，顶点 u 在拓扑排序中位于 v 之前。

Python 3.9.0 中引入的 Python 模块 graphlib 给出了一个图的拓扑排序，图在字典中表示。假设图没有平行边，图可以用以顶点为键的字典来表示，值是它们所连接的节点。

要安装此模块，请在您的终端上运行此命令。

```
pip install graphlib
```

我们将使用 graphlib 类。**拓扑排序器(图=无)**，以及拓扑排序器实例的下列函数:

> **添加(节点，*前置任务):**
> 
> 将新节点及其依赖项添加到图形中。例如，ts.add(3，2，1)将键值 3 及其前置值 2，1 添加到图表中。
> 
> **static_order():**
> 
> 以拓扑顺序返回节点列表。

检查下面的程序，用 graphlib 进行拓扑排序。拓扑分类器()

**示例 1:** 使用未初始化图形的拓扑排序器进行拓扑排序。

## 蟒蛇 3

```
# Python 3.9.0 program for
# topological sorting using
# graphlib module
from graphlib import TopologicalSorter

# creating an instance of TopologicalSorter
# initial graph is optional
ts = TopologicalSorter()

# adding vertex and it's nodes
ts.add(3, 2, 1)
# adding more node and predecessor
ts.add(1, 0)

# printing the topological order
# returned by static_order()
print([*ts.static_order()])
```

**输出:**

```
[2, 0, 1, 3]
```

**示例 2:** 使用初始化图的拓扑排序器进行拓扑排序。

## 蟒蛇 3

```
# Python program for topological sorting
# through graphlib module

from graphlib import TopologicalSorter

# making graph
graph = {2: {3}, 3: {1}, 4: {0, 1}, 5: {0, 2}}

# creating an instance of TopolocialSorter
# with initial graph(initial graph is optional)
ts = TopologicalSorter(graph)

# printing the topological order
# returned by static_order()
print([*ts.static_order()])
```

**输出:**

```
[1, 0, 3, 4, 2, 5]
```