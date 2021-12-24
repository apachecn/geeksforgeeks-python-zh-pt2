# PyQtGraph–设置绘图窗口的最小高度

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-setting-最小绘图高度-窗口/](https://www.geeksforgeeks.org/pyqtgraph-setting-minimum-height-of-plot-window/)

在本文中，我们将看到如何在 PyQtGraph 模块中设置绘图窗口的最小高度。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。绘图窗口由两个主要部分组成:包含实际绘图图形的绘图面板和控制面板。默认情况下，绘图窗口是可调整大小的，用户可以随时调整大小，通过设置最小高度，我们可以修复用户不能降低高度超过最小高度点的问题。

我们可以在下面给出的命令的帮助下创建一个绘图窗口

```
# creating a pyqtgraph plot window
window = pg.plot()

```

> 为此，我们对绘图窗口对象使用`setMinimumHeight`方法
> 
> **语法:** window.setMinimumHeight(高度)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回无

下面是实现

```
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

# setting minimum height of the window
window.setMinimumHeight(300)

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using 
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()

```

**输出:**
当我们尝试减小尺寸时高度并没有缩小到设定点之外
![](img/a0e29e4c6471c28443e1705072ba7eb8.png)