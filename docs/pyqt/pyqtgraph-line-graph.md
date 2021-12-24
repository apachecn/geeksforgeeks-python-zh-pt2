# PyQtGraph–线图

> 原文:[https://www.geeksforgeeks.org/pyqtgraph-line-graph/](https://www.geeksforgeeks.org/pyqtgraph-line-graph/)

在本文中，我们将看到如何在 PyQtGraph 模块中创建折线图。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。
折线图或线图或线图或曲线图是一种图表类型，它将信息显示为一系列由直线段连接的数据点，称为“标记”。它是许多领域中常见的一种基本图表类型。线图是借助 PyQtGraph 中的绘图类创建的。

> 为了在 PyQtGraph 中绘制条形图，我们必须执行以下操作
> 1。导入 PyQtgraph 模块
> 2。创建一个绘图窗口
> 3。创建或获取绘图数据，即两条线的水平和两个垂直数据
> 4。将范围设置到绘图窗口
> 5。在绘图窗口中绘制线条并指定线条的属性

下面是实现

## 蟒蛇 3

```py
# importing pyqtgraph as pg
import pyqtgraph as pg

# importing QtCore and QtGui from the pyqtgraph module
from pyqtgraph.Qt import QtCore, QtGui

# importing numpy as np
import numpy as np

# define the data
title = "GeeksforGeeks PyQtGraph"

# y values to plot by line 1
y = [2, 8, 6, 8, 6, 11, 14, 13, 18, 19]

# y values to plot by line 2
y2 = [3, 1, 5, 8, 9, 11, 16, 17, 14, 16]
x = range(0, 10)

# create plot window object
plt = pg.plot()

# showing x and y grids
plt.showGrid(x = True, y = True)

# adding legend
plt.addLegend()

# set properties of the label for y axis
plt.setLabel('left', 'Vertical Values', units ='y')

# set properties of the label for x axis
plt.setLabel('bottom', 'Horizontal Values', units ='s')

# setting horizontal range
plt.setXRange(0, 10)

# setting vertical range
plt.setYRange(0, 20)

# setting window title to the plot window
plt.setWindowTitle(title)

# ploting line in green color
# with dot symbol as x, not a mandatory field
line1 = plt.plot(x, y, pen ='g', symbol ='x', symbolPen ='g',
                          symbolBrush = 0.2, name ='green')

# ploting line2 with blue color
# with dot symbol as o
line2 = plt.plot(x, y2, pen ='b', symbol ='o', symbolPen ='b',
                             symbolBrush = 0.2, name ='blue')

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()
```

**输出:**

<video class="wp-video-shortcode" id="video-488696-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200918010106/GeeksforGeeks-PyQtGraph-2020-09-18-01-00-44.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200918010106/GeeksforGeeks-PyQtGraph-2020-09-18-01-00-44.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200918010106/GeeksforGeeks-PyQtGraph-2020-09-18-01-00-44.mp4)</video>