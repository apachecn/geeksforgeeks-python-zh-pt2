# Python 中使用 Plotly 的小提琴剧情

> 原文:[https://www . geesforgeks . org/violin-plot-use-plot-in-python/](https://www.geeksforgeeks.org/violin-plot-using-plotly-in-python/)

**小提琴图**是一种可视化不同变量数值数据分布的方法。它类似于箱线图，但每侧都有一个旋转图，提供了更多关于 y 轴上密度估计的信息。密度被镜像和翻转，最终的形状被填充，创建一个类似小提琴的图像。小提琴情节的优势在于，它可以显示出在盒式情节中无法察觉的分布细微差别。另一方面，箱线图更清楚地显示了数据中的异常值。

小提琴情节比盒子情节拥有更多的信息，它们不太受欢迎。由于它们不受欢迎，对于许多不熟悉小提琴情节表现的读者来说，它们的意义可能更难理解。

Plotly 是一个开源的 python 模块，是一个非常强大的数据可视化工具。它支持各种图来方便地表示和研究数据。本文讨论了如何使用 Plotly 借助于它的两个类，即 express 和 graph_objects 来获得小提琴的情节。

可以根据个人的方便来选择类，但是方法保持不变。

**方法:**

*   Import module
*   Import data
*   Call violin batch with required parameters.
*   Display diagram

Plotly.express 支持的功能

**语法:**

> 小提琴( *data_frame=None* ， *x=None* ， *y=None* ， *color=None* ， *facet_row=None* ， *facet_col=None* ， *facet_col_wrap=0* ，*facet _ row _ space = None*，*facet _ wrap *方位=无*，*小提琴音=无*，*log _ x =假*，*log _ y =假*，*range _ x =无*，*range _ y =无*，*点数=无*，*框=假*，*标题=无*，*模板=无**

*plotly . graph _ objects 支持的功能*

***语法:***

> 小提琴( *arg* 、 *alignmentgroup* 、*带宽*、 *box_visible* 、 *customdata* 、*customdatarc*、 *fillcolor* 、 *hoverinfo* 、 *hoverinfosrc* 、 *hoverlabel【 *legendgroup* 、 *line* 、 *marker* 、 *meanline* 、 *meta* 、 *metasrc* 、 *name* 、 *offsetgroup* 、*不透明度*、*方位*、*点 pos* 、*点 *流*、*文本*、 *textsrc* 、 *uid* 、*uir vision*、*未选中*、*可见*、*宽度*、 *x* 、 *x0* 、 *xaxis* 、 *x***

**使用中的数据:** [畅销书](https://drive.google.com/file/d/1KhtJuBtO73gItNku98y5ekCRWobzBify/view?usp=sharing)

### 基本小提琴情节

### 方法

*   导入模块
*   创建或加载数据帧
*   使用小提琴绘制()
*   显示图

**例 1:使用 plotly . express**

## python 3

```py
import plotly.express as pt
import pandas as pd

data = pd.read_csv("C:\\Users\\Vanshi\\Desktop\\gfg\\bestsellers.csv")
df = pd.DataFrame(data)
data = df.head()

fig = pt.violin(data, y="Year")
fig.show()
```