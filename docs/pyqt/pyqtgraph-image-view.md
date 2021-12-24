# pyqtgraph–图像视图

> 原文:[https://www.geeksforgeeks.org/pyqtgraph-image-view/](https://www.geeksforgeeks.org/pyqtgraph-image-view/)

*PyQtGraph* 模块是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。).用于显示和分析图像数据的小部件。实现许多功能，如显示 2D 和三维图像数据。对于 3D 数据，显示 z 轴滑块，允许用户选择显示哪个帧。显示图像数据直方图，可移动区域定义暗/亮级别，可编辑渐变提供颜色查找表，也可以使用*左/右*箭头键以及 *pgup* 、 *pgdn、home、*和 *end* 移动帧滑块。

**基本分析特征包括:**
1。跨帧测量图像值的感兴趣区域和嵌入式绘图
2。图像归一化/背景减法
我们可以借助下面给出的命令创建一个图像视图:

```py
# creating a pyqtgraph image view object
img = pg.ImageView()
```

**分步方法:**

1.  导入 *pyqtgraph* 、 *pyqt5* 和 *numpy* 模块。
2.  创建主*窗口*类。
3.  创建图像视图对象。
4.  使用 *pyqtgraph* 模块的 *numpy* 和*高斯*滤镜创建图像。
5.  创建自定义颜色映射，并将其设置为图像视图。
6.  将图像视频视图与其他小部件一起添加到网格布局中。
7.  将网格布局小部件设置为主窗口的中心小部件。

**以下是基于上述方法的实现:**

## 蟒蛇 3

```py
# import required modules
from PyQt5.QtWidgets import *
import sys
import numpy as np
import pyqtgraph as pg
from PyQt5.QtGui import *
from PyQt5.QtCore import *
from collections import namedtuple

# Main window class
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
        label = QLabel("Geeksforgeeks Image View")

        # setting minimum width
        label.setMinimumWidth(130)

        # making label do word wrap
        label.setWordWrap(True)

        # setting configuration options
        pg.setConfigOptions(antialias=True)

        # creating image view view object
        imv = pg.ImageView()

        # Create random 3D data set with noisy signals
        img = pg.gaussianFilter(np.random.normal(
            size=(200, 200)), (5, 5)) * 20 + 100

        # setting new axis to image
        img = img[np.newaxis, :, :]

        # decay data
        decay = np.exp(-np.linspace(0, 0.3, 100))[:, np.newaxis, np.newaxis]

        # random data
        data = np.random.normal(size=(100, 200, 200))
        data += img * decay
        data += 2

        # adding time-varying signal
        sig = np.zeros(data.shape[0])
        sig[30:] += np.exp(-np.linspace(1, 10, 70))
        sig[40:] += np.exp(-np.linspace(1, 10, 60))
        sig[70:] += np.exp(-np.linspace(1, 10, 30))

        sig = sig[:, np.newaxis, np.newaxis] * 3
        data[:, 50:60, 30:40] += sig

        # Displaying the data and assign each frame a time value from 1.0 to 3.0
        imv.setImage(data, xvals=np.linspace(1., 3., data.shape[0]))

        # Set a custom color map
        colors = [
            (0, 0, 0),
            (45, 5, 61),
            (84, 42, 55),
            (150, 87, 60),
            (208, 171, 141),
            (255, 255, 255)
        ]

        # color map
        cmap = pg.ColorMap(pos=np.linspace(0.0, 1.0, 6), color=colors)

        # setting color map to the image view
        imv.setColorMap(cmap)

        # Creating a grid layout
        layout = QGridLayout()

        # minimum width value of the label
        label.setFixedWidth(130)

        # setting this layout to the widget
        widget.setLayout(layout)

        # adding label in the layout
        layout.addWidget(label, 1, 0)

        # plot window goes on right side, spanning 3 rows
        layout.addWidget(imv, 0, 1, 3, 1)

        # setting this widget as central widget of the main window
        self.setCentralWidget(widget)

# Driver Code

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-504230-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201002011447/PyQtGraph-2020-10-02-01-14-22.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201002011447/PyQtGraph-2020-10-02-01-14-22.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201002011447/PyQtGraph-2020-10-02-01-14-22.mp4)</video>