# PyQtGraph–获取绘图窗口的最小宽度

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-get-最小绘图窗口宽度/](https://www.geeksforgeeks.org/pyqtgraph-getting-minimum-width-of-plot-window/)

在本文中，我们将看到如何在 PyQtGraph 模块中获得绘图窗口的最小宽度。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。绘图窗口由两个主要部分组成:包含实际绘图图形的绘图面板和控制面板。默认情况下，绘图窗口是可调整大小的，用户可以随时调整大小，通过设置最小宽度，我们可以修复用户不能将宽度减小到最小宽度点之外的问题。可以借助`setMinimumWidth`方法进行设置。

我们可以在下面给出的命令的帮助下创建一个绘图窗口

```py
# creating a pyqtgraph plot window
window = pg.plot()

```

> 为此，我们对绘图窗口对象使用`minimumWidth`方法
> 
> **语法:** window.minimumWidth()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

下面是实现

```py
# importing pyqtgraph as pg
import pyqtgraph as pg

# importing QtCore and QtGui from the pyqtgraph module
from pyqtgraph.Qt import QtCore, QtGui

# importing numpy as np
import numpy as np

import time

# creating a pyqtgraph plot window
window = pg.plot()

# setting window geometry
# left = 100, top = 100
# width = 600, height = 500
window.setGeometry(100, 100, 600, 500)

# title
title = "GeeksforGeeks PyQtGraph"

# setting window title
window.setWindowTitle(title)

# create list for y-axis
y1 = [5, 5, 7, 10, 3, 8, 9, 1, 6, 2]

# create horizontal list i.e x-axis
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# create pyqt5graph bar graph item 
# with width = 0.6
# with bar colors = green
bargraph1 = pg.BarGraphItem(x = x, height = y1, width = 0.6, brush ='g')

# add item to plot window
# adding bargraph item to the window
window.addItem(bargraph1)

# setting minimum width of the window
window.setMinimumWidth(300)

# getting minimum width of the window
value = window.minimumWidth()

# printing the value
print("Min Width : ", end ="")
print(value)

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using 
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()

```

**输出:**

![](img/cff8432bdab8b21dc6d4b1eccc3d543b.png)

```py
Min Width : 300

```