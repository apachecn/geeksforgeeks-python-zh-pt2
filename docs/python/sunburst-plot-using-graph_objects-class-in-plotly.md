# 在绘图中使用 graph_objects 类绘制太阳爆发图

> 原文:[https://www . geesforgeks . org/sunburst-plot-use-graph _ objects-class-in-plot/](https://www.geeksforgeeks.org/sunburst-plot-using-graph_objects-class-in-plotly/)

Plotly 是一个 Python 库，用于设计图形，尤其是交互式图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## 使用图形对象类绘制太阳爆发图

如果 Plotly Express 不能提供良好的起点，也可以从更通用的 go 中进行自定义。来自 plotly.graph_objects 的 Sunburst 类。sunbrust 是展示分层数据的原型。层次结构的每一级都由一个环或圆表示，最里面的圆是层次结构的顶部。没有任何分层数据的 sunbrust 图表看起来类似于圆环图。

> **语法:【plotly.graph _ objects 类。sunburst(arg =无，branchvalues =无，count =无，customdata =无，hoverinfo =无，**kwargs)**
> 
> **参数:**
> 
> **arg:** 与此构造函数或 plotly.graph_objects 实例兼容的属性集合。阳光爆发
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

fig = go.Figure(go.Sunburst(
    labels =["A", "B", "C", "D", "E", "F", "G", "H", "I"],
    parents =["", "A", "A", "C", "C", "A", "A", "G", "A" ],
    values =[11, 24, 2, 6, 7, 1, 1, 5, 4],
))

fig.update_layout(margin = dict(t = 0, l = 0, r = 0, b = 0))

fig.show()
```