# 使用 PyQtGraph 的图像分析工具

> 原文:[https://www . geeksforgeeks . org/image-analysis-tool-use-pyqtgraph/](https://www.geeksforgeeks.org/image-analysis-tool-using-pyqtgraph/)

在本文中，我们将看到如何使用 Python 中的 PyQtGraph 模块来执行常见的图像分析。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。

为了安装 PyQtGraph，我们使用下面给出的命令。

```py
pip install pyqtgraph
```

图像分析是从图像中提取有意义的信息；主要通过数字图像处理技术从数字图像中提取。图像分析任务可以像读取条形码标签一样简单，也可以像从人脸识别一个人一样复杂。

为了做到这一点，我们必须做到以下几点。

1.  导入所需的库，如 pyqtgraph、pyqt5 和 numpy。
2.  使用 pyqt5 创建一个主窗口类。
3.  创建一个图形窗口来添加显示图像分析所需的小部件。
4.  创建两个绘图区域，并添加一个图像项目，将 roi 对象添加到第一个绘图区域。
5.  创建一个等曲线对象，并将其添加到图像项中。
6.  为图像创建数据并将其添加到图像项目中。
7.  当区域改变时，将更新方法连接到 roi 对象，在更新方法中获取区域并将其设置到第二个绘图区域。
8.  创建鼠标移动事件，并根据鼠标位置设置标题的位置、像素值。
9.  将此图形窗口添加到主窗口布局中，并添加任何其他小部件。

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
        self.setGeometry(100, 100, 900, 550)

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
        text = "Image Analysis"

        # creating a label
        label = QLabel(text)

        # setting minimum width
        label.setMinimumWidth(130)

        # making label do word wrap
        label.setWordWrap(True)

        # creating a graphic layout widget

        win = pg.GraphicsLayoutWidget()

        # plot area (ViewBox + axes) for displaying the image
        p1 = win.addPlot(title="")

        # item for displaying image data
        img = pg.ImageItem()

        # adding image to the plot area
        p1.addItem(img)

        # Custom ROI for selecting an image region
        roi = pg.ROI([-10, 14], [5, 5])
        roi.addScaleHandle([0.5, 1], [0.5, 0.5])
        roi.addScaleHandle([0, 0.5], [0.5, 0.5])

        # adding roi to the plot area
        p1.addItem(roi)

        # setting z value to roi
        # making sure ROI is drawn above image
        roi.setZValue(10)

        # creating a Isocurve drawing on the image
        iso = pg.IsocurveItem(level=1.2, pen='r')

        # setting parent as image
        iso.setParentItem(img)

        # setting z axis value of isocurve
        iso.setZValue(5)

        # Contrast/color control
        hist = pg.HistogramLUTItem()

        # setting image to the control
        hist.setImageItem(img)

        # adding control widget to the plot window
        win.addItem(hist)

        # creating draggable line for setting isocurve level
        isoLine = pg.InfiniteLine(angle=0, movable=True, pen='r')
        hist.vb.addItem(isoLine)

        # making user interaction a little easier
        hist.vb.setMouseEnabled(y=False)
        isoLine.setValue(0.8)

        # bring iso line above contrast controls
        isoLine.setZValue(1000)

        # going to next row of graphic window
        win.nextRow()

        # another plot area for displaying ROI data
        p2 = win.addPlot(colspan=2)

        # setting maximum height of plot area
        p2.setMaximumHeight(250)

        # generating image data
        data = np.random.normal(size=(200, 100))
        data[20:80, 20:80] += 2.

        # setting gaussian filter to the data
        data = pg.gaussianFilter(data, (3, 3))
        data += np.random.normal(size=(200, 100)) * 0.1

        # setting data to the image
        img.setImage(data)

        # setting level
        hist.setLevels(data.min(), data.max())

        # build isocurves from smoothed data
        iso.setData(pg.gaussianFilter(data, (2, 2)))

        # set position and scale of image
        img.scale(0.2, 0.2)
        img.translate(-50, 0)

        # zoom to fit image
        p1.autoRange()

        # method for updating the plot
        def updatePlot():

            # getting the selected region by the roi
            selected = roi.getArrayRegion(data, img)

            # plot the selected region
            p2.plot(selected.mean(axis=0), clear=True)

        # connecting the update plot method
        # it get called when the region is changed
        roi.sigRegionChanged.connect(updatePlot)

        # call the update plot method
        updatePlot()

        # method for updating the isocurve
        def updateIsocurve():
            # setting iso level
            iso.setLevel(isoLine.value())

        isoLine.sigDragged.connect(updateIsocurve)

        # method for image hover event
        def imageHoverEvent(event):

            # showing the position, pixel, and value under the mouse cursor
            # if cursor is not on the plot area
            if event.isExit():
                # set title as blank
                p1.setTitle("")
                return

            # getting cursor position
            pos = event.pos()
            i, j = pos.y(), pos.x()

            # pixel values
            i = int(np.clip(i, 0, data.shape[0] - 1))
            j = int(np.clip(j, 0, data.shape[1] - 1))

            # value of point
            val = data[i, j]
            ppos = img.mapToParent(pos)
            x, y = ppos.x(), ppos.y()

            # setting plot title data
            p1.setTitle(
                "pos: (%0.1f, %0.1f)  pixel: (%d, %d)  value: %g" % (x, y, i, j, val))

        # Monkey-patch the image to use our custom hover function.
        img.hoverEvent = imageHoverEvent

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

<video class="wp-video-shortcode" id="video-505032-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201018013146/PyQtGraph-2020-10-18-01-30-45.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201018013146/PyQtGraph-2020-10-18-01-30-45.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201018013146/PyQtGraph-2020-10-18-01-30-45.mp4)</video>