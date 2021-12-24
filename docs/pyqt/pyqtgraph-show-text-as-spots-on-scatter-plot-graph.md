# 散点图–在散点图上显示文本为点

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-show-text-as-spots-on-spots-plot-graph/](https://www.geeksforgeeks.org/pyqtgraph-show-text-as-spots-on-scatter-plot-graph/)

在本文中，我们将看到如何在 PyQtGraph 模块中创建散点图，它将文本而不是符号显示为点。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。).散点图(又称散点图，散点图)使用点来表示两个不同数值变量的值。这是一种使用笛卡尔坐标来显示一组数据的两个变量的值的绘图或数学图表。水平轴和垂直轴上每个点的位置表示单个数据点的值。将文本显示为点的主要概念是，我们将创建一个充当点的文本。

我们可以创建一个绘图窗口，并在下面给出的命令的帮助下在上面创建散点图。

```py
# creating a pyqtgraph plot window
plt = pg.plot()

# creating a scatter plot graph of size = 10
scatter = pg.ScatterPlotItem(size=10)
```

**进场:**
1。导入 pyqtgraph、pyqt5 和 numpy 模块
2。创建主窗口类
3。创建绘图窗口对象
4。创建一个创建标签的方法，标签返回名为元组
5 的文本符号。使用 numpy
6 创建随机字符串。使用 numpy 绘制字符串创建随机位置
7。创建散点图项目
8。使用随机字符串和位置创建斑点，并将它们添加到散点图中
9。将散点图添加到绘图窗口
10。将绘图窗口和额外标签小部件添加到主窗口的网格布局中

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

        # creating a label
        label = QLabel("Geeksforgeeks Scatter Plot Graph with Text")

        # setting minimum width
        label.setMinimumWidth(130)

        # making label do word wrap
        label.setWordWrap(True)

        # setting configuration options
        pg.setConfigOptions(antialias=True)

        # creating a plot window
        plt = pg.plot()

        # text symbols
        TextSymbol = namedtuple("TextSymbol", "label symbol scale")

        # number of text
        n = 150

        # method for creating label
        def createLabel(label, angle):

            # QPainterPath
            symbol = QPainterPath()

            # creating QFont object
            f = QFont()

            # setting font size
            f.setPointSize(10)

            # adding text
            symbol.addText(0, 0, f, label)

            # getting bounding rectangle
            br = symbol.boundingRect()

            # getting scale
            scale = min(1\. / br.width(), 1\. / br.height())

            # getting transform object
            tr = QTransform()

            # setting scale to transform object
            tr.scale(scale, scale)

            # rotate the transform
            tr.rotate(angle)

            # translating
            tr.translate(-br.x() - br.width() / 2., -br.y() - br.height() / 2.)

            # returning text symbol
            return TextSymbol(label, tr.map(symbol), 0.1 / scale)

        # creating a random string
        def random_str(): return (
            ''.join([chr(np.random.randint(ord('A'), ord('z')))
                     for i in range(np.random.randint(1, 5))]),
            np.random.randint(0, 360))

        # plotting the scatter plot
        scatter = pg.ScatterPlotItem(size=10, pen=pg.mkPen('w'), pxMode=True)

        # getting random position
        pos = np.random.normal(size=(2, n), scale=1e-5)

        # creating spots
        spots = [{'pos': pos[:, i], 'data': 1, 'brush': pg.intColor(i, n), 'symbol': i % 5, 'size': 5 + i / 10.} for i
                 in range(n)]

        # adding spots to the scatter plot
        scatter.addPoints(spots)

        # spots
        spots = [{'pos': pos[:, i], 'data': 1, 'brush': pg.intColor(i, n), 'symbol': label[1],
                  'size': label[2] * (5 + i / 10.)} for (i, label) in
                 [(i, createLabel(*random_str())) for i in range(n)]]

        # adding points to the scatter plot
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

<video class="wp-video-shortcode" id="video-503434-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200929233330/PyQtGraph-2020-09-29-23-33-12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200929233330/PyQtGraph-2020-09-29-23-33-12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200929233330/PyQtGraph-2020-09-29-23-33-12.mp4)</video>