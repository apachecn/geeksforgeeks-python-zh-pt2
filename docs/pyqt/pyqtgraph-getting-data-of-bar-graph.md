# PyQtGraph–获取条形图数据

> 原文:[https://www . geesforgeks . org/pyqtgraph-get-data-of-bar-graph/](https://www.geeksforgeeks.org/pyqtgraph-getting-data-of-bar-graph/)

在本文中，我们将看到如何在 PyQtGraph 模块中获取条形图的数据。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。条形图或条形图是用矩形条表示分类数据的图表，矩形条的高度或长度与它们所代表的值成比例。条形图可以垂直或水平绘制。垂直条形图有时也称为柱形图。条形图使用两个列表中的两个数据，即 x 轴数据和条形高度数据。

借助下面给出的命令，我们可以创建一个绘图窗口和条形图

```py
# creating a pyqtgraph plot window
window = pg.plot()

# creating a bar graph of green color
bargraph = pg.BarGraphItem(x=x, height=y1, width=0.6, brush='g')

```

> 为此，我们对条形图对象使用`getData`方法
> 
> **语法:**条形图. getData()
> 
> **论证:**不需要论证
> 
> **返回:**返回元组

下面是实现

```py
# importing QtGui to use QIcon
from PyQt5.QtGui import * from PyQt5.QtCore import Qt 

# importing pyqtgraph as pg
import pyqtgraph as pg

# importing QtCore and QtGui from the pyqtgraph module
from pyqtgraph.Qt import QtCore, QtGui

# importing numpy as np
import numpy as np

import time

# creating a pyqtgraph plot window
window = pg.plot()

# icon for plot window
icon = QIcon("logo.png")

# setting icon to the plot window
window.setWindowIcon(icon)

# setting window geometry
# left = 100, top = 100
# width = 600, height = 500
window.setGeometry(100, 100, 600, 500)

# title for the plot window
title = "GeeksforGeeks PyQtGraph"

# setting window title to plot window
window.setWindowTitle(title)

# create list for y-axis
y1 = [5, 5, 7, 10, 3, 8, 9, 1, 6, 2]

# create horizontal list i.e x-axis
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# create pyqt5graph bar graph item 
# with width = 0.6
# with bar colors = green
bargraph = pg.BarGraphItem(x = x, height = y1, width = 0.6, brush ='g')

# add item to plot window
# adding bargraph item to the window
window.addItem(bargraph)

# getting data of the bar graph
value = bargraph.getData()

# printing the value
print("Data  : " + str(value))

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using 
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()

```

**输出:**

![](img/34f9044c9d0f6acb3c458654309b1de8.png)

```py
Data  : ([1, 2, 3, 4, 5, 6, 7, 8, 9, 10], [5, 5, 7, 10, 3, 8, 9, 1, 6, 2])

```