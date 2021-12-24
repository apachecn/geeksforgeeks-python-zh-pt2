# 在绘图中使用 graph_objects 类的树形图

> 原文:[https://www . geesforgeks . org/tree map-using-graph _ objects-class-in-plot/](https://www.geeksforgeeks.org/treemap-using-graph_objects-class-in-plotly/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## 使用 graph_objects 类的树图

Treemapping 是一个数据可视化程序，可以用封闭的矩形演示分级数据。通过使用矩形、尺寸和绘图颜色表示，数据被组织为分支和子分支。树形图显然有助于区分数据值之间的类别。

> **语法:【plotly.graph _ objects 类。树形图(参数=无，分支值=无，计数=无，自定义数据=无，悬停信息=无，**kwargs)**
> 
> **参数:**
> 
> **arg:** 与此构造函数或 plotly.graph_objects 实例兼容的属性集合。树形图
> 
> **branchvalues:** 确定值中的项目如何求和。
> 
> **计数:**通过为每个“叶”和/或“枝”推断 1，确定未提供值时的默认值，否则为 0。
> 
> **自定义数据:**为每个数据分配额外的数据。这在收听悬停、点击和选择事件时可能很有用。请注意，“分散”跟踪还会在标记 DOM 元素中追加自定义数据项
> 
> **悬停信息:**确定悬停时出现哪些跟踪信息。如果设置了无或跳过，悬停时不会显示任何信息。但是，如果没有设置，点击和悬停事件仍然会触发。

**示例:**

## 蟒蛇 3

```
import plotly.graph_objects as go

fig = go.Figure(go.Treemap(
    labels = ["A", "B", "C", "D", "E"],
    parents = ["", "A", "B", "C", "A"] 
))

fig.show()
```