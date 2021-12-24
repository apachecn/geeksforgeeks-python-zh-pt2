# PyQtGraph–显示视频

> 原文:[https://www.geeksforgeeks.org/pyqtgraph-showing-video/](https://www.geeksforgeeks.org/pyqtgraph-showing-video/)

在本文中，我们将看到如何在 PyQTGraph 中显示视频。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。).用于显示和分析图像数据的小部件。实现许多功能，如显示 2D 和三维图像数据。对于 3D 数据，显示 z 轴滑块，允许用户选择显示哪个帧。显示图像数据的直方图，可移动区域定义暗/亮级别，可编辑渐变提供颜色查找表。使用图像视图对象显示视频，并随时更新帧。
我们可以借助下面给出的命令
创建一个图像视图

```py
# creating a pyqtgraph image view object
imv = pg.ImageView()
```

> **语法:** ImageView(parent=None，name='ImageView '，view=None，imageItem=None，levelmode= ' mono '，*args)
> 
> **参数:**
> 
> *   **父代** **(QWidget):** 指定此 ImageView 将属于的父代 Widget。如果没有，则创建没有父级的图像视图。
> *   **名称(字符串):**用于注册内部视图框和用于显示感兴趣区域数据的绘图项目的名称。
> *   **视图(视图框或绘图项目):**如果指定，这将用作包含显示图像的显示区域。
> *   **imageItem (ImageItem):** 如果指定，该对象将用于显示图像。必须是 ImageItem 或其他兼容对象的实例。
> *   **等级模式:**指定*等级模式*参数
> 
> **返回:【ImageView 类的对象**

为了绘制视频，我们必须执行以下操作

1.  导入 pyqtgraph、pyqt5 和 numpy 模块
2.  创建主窗口类
3.  创建一个图形布局小部件，并向其中添加图像视图框
4.  创建一个图像项目对象并将其添加到图像视图中
5.  为图像项目创建随机数据
6.  创建一个不断更新图像数据的更新数据方法，使其看起来像视频，并调用此方法
7.  将图形布局添加到主窗口的网格布局中，并将该小部件设置为中心小部件

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
import pyqtgraph.ptime as ptime

# Image View class
class ImageView(pg.ImageView):

    # constructor which inherit original
    # ImageView
    def __init__(self, *args, **kwargs):
        pg.ImageView.__init__(self, *args, **kwargs)

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
        label = QLabel("Geeksforgeeks Video")

        # setting minimum width
        label.setMinimumWidth(130)

        # making label do word wrap
        label.setWordWrap(True)

        # setting configuration options
        pg.setConfigOptions(antialias = True)

        # creating a graphics layout widget
        win = pg.GraphicsLayoutWidget()

        # adding view box object to graphic window
        view = win.addViewBox()

        ##lock the aspect ratio so pixels are always square
        view.setAspectLocked(True)

        # Create image item
        self.img = pg.ImageItem(border='w')

        # adding image item to the view box
        view.addItem(self.img)

        # Set initial view bounds
        view.setRange(QRectF(0, 0, 600, 600))

        #  Create random image
        self.data = np.random.normal(size=(15, 600, 600),
                                     loc = 1024, scale = 64).astype(np.uint16)

        # helps in incrementing
        self.i = 0

        # getting time
        self.updateTime = ptime.time()

        # fps
        self.fps = 0

        # method to update the data of image
        def updateData():

            ## Display the data
            self.img.setImage(self.data[self.i])

            # creating new value of i
            self.i = (self.i + 1) % self.data.shape[0]

            # creating a qtimer
            QTimer.singleShot(1, updateData)

            # getting current time
            now = ptime.time()

            # temporary fps
            fps2 = 1.0 / (now - self.updateTime)

            # updating the time
            self.updateTime = now

            # setting original fps value
            self.fps = self.fps * 0.9 + fps2 * 0.1

        # call the update method
        updateData()

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

<video class="wp-video-shortcode" id="video-498879-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201006002440/PyQtGraph-2020-10-06-00-24-21.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201006002440/PyQtGraph-2020-10-06-00-24-21.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201006002440/PyQtGraph-2020-10-06-00-24-21.mp4)</video>