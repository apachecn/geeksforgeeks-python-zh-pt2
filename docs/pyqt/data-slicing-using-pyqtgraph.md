# 使用 PyQtGraph 进行数据切片

> 原文:[https://www.geeksforgeeks.org/data-slicing-using-pyqtgraph/](https://www.geeksforgeeks.org/data-slicing-using-pyqtgraph/)

在本文中，我们将看到如何使用 Python 中的 PyQtGraph 模块来执行数据切片。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。

为了安装 PyQtGraph，我们使用下面给出的命令

```py
pip install pyqtgraph

```

多维数组中的切片是对应于维度的一个或多个成员的单个值的数据列。切片是分割立方体以提取给定切片的信息的行为。它很重要，因为它有助于用户可视化和收集特定维度的信息。当您想到切片时，请将其视为维度中特定值的专用筛选器。一个简单的数据切片任务是为给定的三维数据选择一个 2D 平面，并沿该平面插值数据以生成切片图像。

为了做到这一点，我们必须做到以下几点

*   导入所需的库，如 pyqtgraph、pyqt5 和 numpy
*   使用 pyqt5 创建一个主窗口类
*   创建一个图形窗口来添加显示切片所需的小部件
*   在布局中创建两个图像视图对象，首先显示整个 3d 数据，其次显示切片
*   创建一个 roi 对象，并将其添加到第一个图像视图中以选择切片
*   创建 3d 数据并将其添加到图像视图中
*   当区域改变时，将更新方法连接到 roi 对象，在更新方法中获取区域并将其设置为第二个图像视图
*   将此图形窗口添加到主窗口布局中，并添加任何其他小部件。

下面是实现。

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
        self.setGeometry(100, 100, 700, 550)

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
        text = "Data Slicing"

        # creating a label
        label = QLabel(text)

        # setting minimum width
        label.setMinimumWidth(130)

        # making label do word wrap
        label.setWordWrap(True)

        # creating a window for graphs
        win = QMainWindow()

        # creating a widget object
        cwid = QWidget()

        # setting central widget to the graph window
        win.setCentralWidget(cwid)

        # creating a grid layout
        lay = QGridLayout()

        # setitng grid layout to central widget of graphs
        cwid.setLayout(lay)

        # creating a image view objects
        imv1 = pg.ImageView()
        imv2 = pg.ImageView()

        # adding image view objects to the layout
        lay.addWidget(imv1, 0, 0)
        lay.addWidget(imv2, 1, 0)

        # creating a ROI object for selecting slice
        roi = pg.LineSegmentROI([[30, 64], [100, 64]], pen='r')

        # add roi to image view 1
        imv1.addItem(roi)

        # creating 3d data
        # x value using numpy
        x1 = np.linspace(-30, 10, 128)[:, np.newaxis, np.newaxis]
        x2 = np.linspace(-20, 20, 128)[:, np.newaxis, np.newaxis]

        # y value using numpy
        y = np.linspace(-30, 10, 128)[np.newaxis, :, np.newaxis]
        z = np.linspace(-20, 20, 128)[np.newaxis, np.newaxis, :]

        # dimension 1 values
        d1 = np.sqrt(x1 ** 2 + y ** 2 + z ** 2)

        # dimension 2 values
        d2 = 2 * np.sqrt(x1[::-1] ** 2 + y ** 2 + z ** 2)

        # dimension 3 value
        d3 = 4 * np.sqrt(x2 ** 2 + y[:, ::-1] ** 2 + z ** 2)

        # whole data ie all 3 dimensions
        data = (np.sin(d1) / d1 ** 2) + \
            (np.sin(d2) / d2 ** 2) + (np.sin(d3) / d3 ** 2)

        # method to update the image view 2
        def update():

            # get the roi selected data from image view 1
            d2 = roi.getArrayRegion(data, imv1.imageItem, axes=(1, 2))

            # update the image view 2 data
            imv2.setImage(d2)

        # adding update method to the roi
        # when region is changed this method get called
        roi.sigRegionChanged.connect(update)

        # Display the data in both image view
        imv1.setImage(data)

        # setting the range of image view
        imv1.setHistogramRange(-0.01, 0.01)

        # setting levels of the image view
        imv1.setLevels(-0.003, 0.003)

        # call the update method
        update()

        # Creating a grid layout
        layout = QGridLayout()

        # minimum width value of the label
        label.setMinimumWidth(130)

        # setting this layout to the widget
        widget.setLayout(layout)

        # adding label in the layout
        layout.addWidget(label, 1, 0)

        # plot window goes on right side, spanning 3 rows
        layout.addWidget(win, 0, 1, 3, 1)

        # setting this widget as central widget of the main widow
        self.setCentralWidget(widget)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-509158-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201018004955/PyQtGraph-2020-10-18-00-48-37.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201018004955/PyQtGraph-2020-10-18-00-48-37.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201018004955/PyQtGraph-2020-10-18-00-48-37.mp4)</video>