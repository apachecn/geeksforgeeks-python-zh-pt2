# Python 中 PyQtGraph 模块介绍

> 原文:[https://www . geesforgeks . org/introduction-to-pyqtgraph-module-in-python/](https://www.geeksforgeeks.org/introduction-to-pyqtgraph-module-in-python/)

**PyQtGraph** 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。
PyQtGraph 大量使用 Qt 图形用户界面平台(通过 PyQt 或 PySide)来获得高性能图形，使用 numpy 来进行大量的数字处理。特别是，pyqtgraph 使用了 Qt 的 GraphicsView 框架，这是一个独立的高性能图形系统，这为该框架带来了优化和简化的原语，从而允许以最小的努力实现数据可视化。
为了安装 PyQtGraph，我们使用下面给出的命令

```py
pip install pyqtgraph
```

**要求:** PyQtGraph 可以在支持以下软件包的任何平台上运行:
1。Python 2.7 和 3+
2。PyQt 4.8+或 PySide
3。NumPy
4。3D 图形需要 python-opengl 绑定
**示例:**在本例中，我们将使用 python 中的 PyQtGraph 模块
创建一个简单的条形图

## 蟒蛇 3

```py
# importing pyqtgraph as pg
import pyqtgraph as pg

# importing QtCore and QtGui from the pyqtgraph module
from pyqtgraph.Qt import QtCore, QtGui

# importing numpy as np
import numpy as np

# creating a pyqtgraph plot window
window = pg.plot()

# title
title = "GeeksforGeeks PyQtGraph"

# setting window title
window.setWindowTitle(title)

# create list for y-axis
y1 = [5, 5, 7, 10, 3, 8, 9, 1, 6, 2]

# create horizontal list i.e x-axis
x = [1, 10, 4, 5, 7, 3, 6, 8, 9, 2]

# create pyqt5graph bar graph item
# with bar colors = green
bargraph1 = pg.BarGraphItem(x = x, height = y1, width = 0.6, brush ='g')

# adding bargraph item to the window
window.addItem(bargraph1)

# main method
if __name__ == '__main__':

    # importing system
    import sys

    # Start Qt event loop unless running in interactive mode or using
    if (sys.flags.interactive != 1) or not hasattr(QtCore, 'PYQT_VERSION'):
        QtGui.QApplication.instance().exec_()
```