# Python 中使用 Plotly 绘制的树形图

> 原文:[https://www . geesforgeks . org/tree map-使用 python 中的 plotly/](https://www.geeksforgeeks.org/treemap-using-plotly-in-python/)

**Plotly** 是一个 Python 库，用来设计图形，尤其是交互图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。plotly 是一个交互式可视化库。

## Plotly 中的树形图

**plotly . express 中的 Treemap** 使用方便，高级终端可进行 plotly，完成多种类型的数据，生成风格简单的图形。树形图提供了数据的分层视图，并使模式变得简单。树分支由矩形表示，每个子分支以较小的矩形显示。

> **语法:**plot . express . tree map(data _ frame =None，name=None，values=None，parents=None，ids=None，path=None，color_continuous_scale=None，range_color=None，color _ continuous _ 中点= None，color _ distributed _ sequence = None，color _ distributed _ map ={}，hover_name=None，hover_data=None，custom_data=None，标签= { }，title=None，template=None，width=None，height=None，branchvalues
> 
> **参数:**
> 
> **data_frame:** 需要传递此参数才能使用列名(而不是关键字名)。类数组和字典在内部被转换成熊猫数据帧。
> 
> **名称:**data _ frame 中列的名称，或者 pandas Series 或 array_like 对象。此列或 array_like 中的值用作扇区的标签。
> 
> **值:**data _ frame 中列的名称，或者 pandas Series 或 array_like 对象。来自该列或 array_like 的值用于设置与扇区相关联的值。
> 
> **路径:**data _ frame 中的列名，或 pandas Series，或 array_like 对象列名列表或矩形数据框的列，定义从根到叶的扇区层次结构。
> 
> **颜色:**data _ frame 中列的名称，或者 pandas Series 或 array_like 对象。此列或 array_like 中的值用于为标记指定颜色。

**示例:**

## 蟒蛇 3

```py
import plotly.express as px

fig = px.treemap(
    names = ["A","B", "C", "D", "E"],
    parents = ["", "A", "B", "C", "A"]
)

fig.show()
```