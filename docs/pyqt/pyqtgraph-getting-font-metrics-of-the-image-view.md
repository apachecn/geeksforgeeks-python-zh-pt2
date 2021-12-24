# PyQtGraph–获取图像视图的字体度量

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-get-font-metrics-of-image-view/](https://www.geeksforgeeks.org/pyqtgraph-getting-font-metrics-of-the-image-view/)

本文讨论如何在 PyQTGraph 中获取图像视图对象的字体度量。在金属排版技术中，字体具有特定的尺寸、重量和字体风格。每种字体都有一套匹配的字体和一种由一系列字体组成的字体，这些字体共享一个整体设计。可以借助 setFont 方法进行设置。字体度量是对特定字体中字符的度量，它允许您均匀地分隔和对齐文本行。

PyQtGraph 是一个图形和用户界面 Python 库，用于设计和科学应用程序中通常需要的功能。它为显示数据(图表、视频等)提供了快速的交互式图形。).实现许多功能，如显示 2D 和三维图像数据。对于 3D 数据，显示 z 轴滑块，允许用户选择要显示的帧。显示图像数据的直方图，可移动区域定义暗/亮级别，可编辑渐变提供颜色查找表供参考。

为了创建图像视图，使用了 image view()

**语法:**

> imv = pg。ImageView()

要获取图像视图的字体度量，请使用 font metrics()。它不接受任何参数，并返回一个 QFontMetrics 对象。

**语法:**

> imv.fontMetrics()

**执行:**

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

        # setting fixed size of window
        #self.setFixedSize(QSize(600, 500))

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
        imv = ImageView()

        # Create random 3D data set with noisy signals
        img = pg.gaussianFilter(np.random.normal(size=(200, 200)), (5, 5)) * 20 + 100

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

        # setting image to image view
        # Displaying the data and assign each frame a time value from 1.0 to 3.0
        imv.setImage(data, xvals=np.linspace(1., 3., data.shape[0]))

        ## Set a custom color map
        colors = [
            (0, 0, 0),
            (4, 5, 61),
            (84, 42, 55),
            (15, 87, 60),
            (208, 17, 141),
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

        # creating a font object
        font = QFont('Arial', 11)

        # making font italic and bold
        font.setItalic(True)
        font.setBold(True)

        # setting font to the image view
        imv.setFont(font)

        # getting font metrics of the image view
        value = imv.fontMetrics()

        # setting text to the label
        label.setText("Font Metrics : " + str(value))

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

# start the app
sys.exit(App.exec())
```

**输出:**

![](img/b30449a494f61f78a32a99f232d6fb40.png)