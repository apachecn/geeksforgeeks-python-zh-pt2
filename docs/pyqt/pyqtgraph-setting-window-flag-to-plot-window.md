# PyQtGraph–将窗口标志设置为绘图窗口

> 原文:[https://www . geesforgeks . org/pyqtgraph-setting-window-flag-to-plot-window/](https://www.geeksforgeeks.org/pyqtgraph-setting-window-flag-to-plot-window/)

在本文中，我们将看到如何在 PyQtGraph 模块中为绘图窗口设置窗口标志。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。绘图窗口由两个主要部分组成:包含实际绘图图形的绘图面板和控制面板。窗口标志用于更改与操作系统和绘图窗口的内部交互。
我们可以借助下面给出的命令
创建一个绘图窗口

```
# creating a pyqtgraph plot window
window = pg.plot()
```

> 为了做到这一点，我们使用 setWindowFlag 方法与绘图窗口对象
> **语法:** window.setWindowFlag(Qt。无框架窗口提示)
> **参数:**它以 Qt 对象作为参数
> **返回:**它不返回

下面是实现

## 蟒蛇 3

```
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
bargraph1 = pg.BarGraphItem(x = x, height = y1, width = 0.6, brush ='g')

# add item to plot window
# adding bargraph item to the window
window.addItem(bargraph1)

# setting window flag
# this will not allow the window to get opened
window.setWindowFlag(Qt.CustomizeWindowHint)

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()

```

**输出:**
屏幕上不会出现窗口