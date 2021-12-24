# PyQtGraph–获取绘图窗口的工具提示持续时间

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-get-tool-tip-绘图窗口持续时间/](https://www.geeksforgeeks.org/pyqtgraph-getting-tool-tip-duration-of-plot-window/)

在本文中，我们将看到如何在 PyQtGraph 模块中获得绘图窗口的工具提示持续时间。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。绘图窗口由两个主要部分组成:包含实际绘图图形的绘图面板和控制面板。工具提示、信息提示或提示是一种常见的图形用户界面元素，当悬停在某个项目上时显示为信息文本框。用户将指针悬停在某个项目上，而不单击它，工具提示可能会显示一个小的“悬停框”，其中包含有关该项目的信息。可以借助`setToolTip`方法进行设置。刀尖持续时间是刀尖消失后出现的时间。可以借助`setToolTipDuration`方法进行设置。

我们可以在下面给出的命令的帮助下创建一个绘图窗口

```
# creating a pyqtgraph plot window
window = pg.plot()

```

> 为此，我们对绘图窗口对象使用`toolTipDuration`方法
> 
> **语法:** window.toolTipDuration()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

下面是实现

```
# importing QtGui to use QIcon
from PyQt5.QtGui import * 

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

# text for tool tip
text = "This is Bar Graph"

# setting window tool tip
window.setToolTip(text)

# setting toop tip duration = 2seconds
window.setToolTipDuration(2000)

# getting tool tip duration of plot window
value = window.toolTipDuration()

# printing the value
print("Tool Tip Duration : " + str(value))

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using 
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()

```

**输出:**
![](img/aa7d187595ef6cee1ea040dc44b11b34.png)

```
Tool Tip Duration : 2000

```