# PyQtGraph–关闭绘图窗口

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-closing-plot-window/](https://www.geeksforgeeks.org/pyqtgraph-closing-plot-window/)

在本文中，我们将看到如何在 PyQtGraph 模块中关闭绘图窗口。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。

绘图窗口由两个主要部分组成:包含实际绘图图形的绘图面板(默认位于顶部)和控制面板(默认位于底部)。控制面板是您配置将要绘制的内容的地方。对于一个简单的散点图来说，它可能只是一个选择哪些列相互对照的情况，但是它可以变得非常详细。

> 为此，我们对绘图窗口对象使用`close`方法
> 
> **语法:**窗口.关闭()
> 
> **论证:**不需要论证
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

# title
title = "GeeksforGeeks PyQtGraph"

# setting window title
window.setWindowTitle(title)

# create list for y-axis
y1 = [5, 5, 7, 10, 3, 8, 9, 1, 6, 2]

# create horizontal list i.e x-axis
x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# create pyqt5graph bar graph item 
# with bar colors = green
bargraph1 = pg.BarGraphItem(x = x, height = y1, width = 0.6, brush ='g')

# adding bargraph item to the window
window.addItem(bargraph1)

# window will get closed
window.close()

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using 
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()

    print("window is closed")    
```

**输出:**

```
window is closed

```