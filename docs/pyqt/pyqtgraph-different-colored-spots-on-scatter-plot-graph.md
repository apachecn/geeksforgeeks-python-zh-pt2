# PyQtGraph–散点图上的不同色点

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-散点图上的不同颜色斑点/](https://www.geeksforgeeks.org/pyqtgraph-different-colored-spots-on-scatter-plot-graph/)

在本文中，我们将看到如何在 PyQtGraph 模块中创建具有不同色点的散点图。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。).散点图(又称散点图，散点图)使用点来表示两个不同数值变量的值。这是一种使用笛卡尔坐标来显示一组数据的两个变量的值的绘图或数学图表。水平轴和垂直轴上每个点的位置表示单个数据点的值。显示不同颜色斑点的主要概念是，我们将以字典的形式创建斑点，该字典将具有颜色和位置属性。
我们可以在下面给出的命令的帮助下，创建一个绘图窗口并在其上创建散点图

```
# creating a pyqtgraph plot window
plt = pg.plot()

# creating a scatter plot graph of size = 10
scatter = pg.ScatterPlotItem(size=10)
```

为了做到这一点，我们必须做到以下几点

1.  导入 pyqtgraph、pyqt5 和 numpy 模块
2.  创建主窗口类
3.  创建绘图窗口对象
4.  创建散点图项目对象
5.  为存储每个地点创建一个空列表
6.  在循环的帮助下，创建一个斑点字典，其关键字为“位置”、“颜色”、“笔”、“大小”，用于斑点的位置、颜色、笔和大小。
7.  将这些现场词典添加到列表中
8.  将列表作为斑点添加到散点图项目列表中
9.  将此散点图添加到绘图窗口中，并使用标签等其他额外的小部件将此图进一步添加到网格布局中

下面是实现

## 蟒蛇 3

```
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

from collections import namedtuple

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

        # text
        text = "Geeksforgeeks Scatter Plot Graph with different color spots"

        # creating a label
        label = QLabel(text)

        # setting minimum width
        label.setMinimumWidth(130)

        # making label do word wrap
        label.setWordWrap(True)

        # setting configuration options
        pg.setConfigOptions(antialias = True)

        # creating a plot window
        plt = pg.plot()

        # creating scatter plot item
        ## Set pxMode=False to allow spots to transform with the view
        scatter = pg.ScatterPlotItem(pxMode = False)

        # creating empty list for spots
        spots = []

        # creating loop for rows and column
        for i in range(10):

            for j in range(10):

                # creating  spot position which get updated after each iteration
                # of color which also get updated
                spot_dic = {'pos': (1e-6 * i, 1e-6 * j), 'size': 1e-6,
                            'pen': {'color': 'w', 'width': 2},
                            'brush': pg.intColor(i * 10 + j, 100)}

                # adding spot_dic in the list of spots
                spots.append(spot_dic)

        # adding spots to the scatter plot
        scatter.addPoints(spots)

        # adding scatter plot to the plot window
        plt.addItem(scatter)

        # Creating a grid layout
        layout = QGridLayout()

        # minimum width value of the label
        label.setMinimumWidth(130)

        # setting this layout to the widget
        widget.setLayout(layout)

        # adding label in the layout
        layout.addWidget(label, 1, 0)

        # plot window goes on right side, spanning 3 rows
        layout.addWidget(plt, 0, 1, 3, 1)

        # setting this widget as central widget of the main window
        self.setCentralWidget(widget)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-504137-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201001001711/PyQtGraph-2020-10-01-00-16-55.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201001001711/PyQtGraph-2020-10-01-00-16-55.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201001001711/PyQtGraph-2020-10-01-00-16-55.mp4)</video>