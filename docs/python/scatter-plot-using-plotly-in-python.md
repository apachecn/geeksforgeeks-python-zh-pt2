# 使用 Python 中的 Plotly 绘制散点图

> 原文:[https://www . geeksforgeeks . org/散点图-使用 python 中的 plotly/](https://www.geeksforgeeks.org/scatter-plot-using-plotly-in-python/)

**Plotly** 是一个 Python 库，用来设计图形，尤其是交互图形。它可以绘制各种图形和图表，如直方图、条形图、箱线图、展开图等。它主要用于数据分析以及财务分析。Plotly 是一个交互式可视化库。

## 散点图

一个**散点图**是一个用点图表示每个值的图。散点图需要相同长度的数组，一个用于 x 轴的值，另一个用于 y 轴的值。每个数据都表示为一个点，其位置由 x 和 y 列给出。它可以使用 plotly.express 的散点()方法创建

> **语法:**plot . express . scatter(data _ frame =无，x =无，y =无，color =无，symbol =无，size =无，hover _ name =无，hover _ data =无，custom _ data =无，text =无，facet _ row =无，facet _ col =无，facet_col_wrap=0，error _ x =无，error _ x _ 减=无，error _ y =无，error _ y _ 减=无，animation _ frame =无，animation _ group =无，category _ orders

**参数:**

<figure class="table">

| 名字 | 价值 | 描述 |
| --- | --- | --- |
| x，y | 类数组，形状(n，) | 数据位置 |
| s | 标量或类数组，shape (n，)，可选 | 标记大小以磅为单位**2。默认值为 rcParams[' line . marker size ']* * 2。 |
| c | 颜色、序列或颜色序列，可选 | 标记颜色。可能的值:单一颜色格式字符串。长度为 n 的一系列颜色规格。使用 cmap 和 norm 映射到颜色的 n 个数字的序列。行是 RGB 或 RGBA 的二维阵列 |
| 标记 | 标记样式，可选 | 标记样式。标记可以是类的实例，也可以是特定标记的文本速记。默认为无，在这种情况下，它采用 rcParams["散点.标记"] = 'o' = 'o '的值。有关标记样式的更多信息，请参见标记。 |

</figure>

**示例:**

## 蟒蛇 3

```py
import plotly.express as px
import numpy as np 

# creating random data through randomint 
# function of numpy.random 
np.random.seed(42) 

random_x= np.random.randint(1,101,100) 
random_y= np.random.randint(1,101,100) 

plot = px.scatter(random_x, random_y)
plot.show()
```