# 散点图–将光标设置为散点图

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-setting-光标到散点图-graph/](https://www.geeksforgeeks.org/pyqtgraph-setting-cursor-to-scatter-plot-graph/)

在本文中，我们将看到如何在 PyQtGraph 模块中为散点图设置自定义光标。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。).散点图(又称散点图，散点图)使用点来表示两个不同数值变量的值。这是一种使用笛卡尔坐标来显示一组数据的两个变量的值的绘图或数学图表。水平轴和垂直轴上每个点的位置表示单个数据点的值。在计算机用户界面中，光标是一种指示器，用于在计算机监视器或其他显示设备上显示用户交互的当前位置，这些显示设备将响应来自文本输入或定点设备的输入。鼠标光标也被称为指针，因为它在用法上类似于指示杆。
我们可以在下面给出的命令的帮助下，创建一个绘图窗口并在其上创建散点图

```py
# creating a pyqtgraph plot window
plt = pg.plot()

# creating a scatter plot graph of size = 10
scatter = pg.ScatterPlotItem(size=10)
```

为此，我们对散点图对象使用**设置光标()**方法

> **语法:**散点. setCursor(cursor)
> **参数:**它以 QCursor 对象为参数
> **返回:**它返回 None

下面是实现

## 蟒蛇 3

```py
# importing Qt widgets
from PyQt5.QtWidgets import *

# importing system
import sys

# importing numpy as np
import numpy as np

# importing pyqtgraph as pg
import pyqtgraph as pg
from PyQt5.QtGui import *
from PyQt5.QtCore import *

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("PyQtGraph")

        # setting geometry
        self.setGeometry(100, 100, 600, 500)

        # icon
        icon = QIcon("skin.png")

        # setting icon to the window
        self.setWindowIcon(icon)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a widget object
        widget = QWidget()

        # creating a label
        label = QLabel("Geeksforgeeks Scatter Plot")

        # making label do word wrap
        label.setWordWrap(True)

        # creating a plot window
        plot = pg.plot()

        # number of points
        n = 300

        # creating a scatter plot item
        # of size = 10
        # using brush to enlarge the of green color
        scatter = pg.ScatterPlotItem(size = 10, brush = pg.mkBrush(30, 255, 35, 255))

        # data for x-axis
        x_data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

        # data for y-axis
        y_data = [5, 4, 6, 4, 3, 5, 6, 6, 7, 8]

        # setting data to the scatter plot
        scatter.setData(x_data, y_data)

        # add item to plot window
        # adding scatter plot item to the plot window
        plot.addItem(scatter)

        # Creating a grid layout
        layout = QGridLayout()

        # minimum width value of the label
        label.setMinimumWidth(130)

        # setting this layout to the widget
        widget.setLayout(layout)

        # adding label in the layout
        layout.addWidget(label, 1, 0)

        # plot window goes on right side, spanning 3 rows
        layout.addWidget(plot, 0, 1, 3, 1)

        # setting this widget as central widget of the main window
        self.setCentralWidget(widget)

        # creating a cursor
        cursor = Qt.PointingHandCursor

        # setting cursor to scatter plot
        scatter.setCursor(cursor)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-502143-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200927021000/PyQtGraph-2020-09-27-02-08-52.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200927021000/PyQtGraph-2020-09-27-02-08-52.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200927021000/PyQtGraph-2020-09-27-02-08-52.mp4)</video>