# PyQtGraph–使用条形图添加 Qt 小部件

> 原文:[https://www . geeksforgeeks . org/pyqtgraph-add-Qt-widgets-with-the-bar-graph/](https://www.geeksforgeeks.org/pyqtgraph-adding-qt-widgets-with-the-bar-graph/)

在本文中，我们将看到如何使用 PyQtGraph 模块中的条形图添加 Qt 小部件。PyQtGraph 是 Python 的图形和用户界面库，提供设计和科学应用程序通常需要的功能。它的主要目标是为显示数据(图表、视频等)提供快速的交互式图形。)第二是提供工具来帮助快速应用程序开发(例如，属性树，如在 Qt Designer 中使用的属性树)。条形图或条形图是用矩形条表示分类数据的图表，矩形条的高度或长度与它们所代表的值成比例。条形图可以垂直或水平绘制。垂直条形图有时也称为柱形图。Qt 有许多多用途的小部件，可以添加到条形图中，这样它可以变得更具交互性。
我们可以借助下面给出的命令创建一个绘图窗口和条形图

```py
# creating a pyqtgraph plot window
window = pg.plot()

# creating a bar graph of green color
bargraph = pg.BarGraphItem(x=x, height=y1, width=0.6, brush='g')
```

> 为了做到这一点，我们必须做以下
> 1。从 PyQt5
> 2 导入 QWidgets。导入 pyqtgraph 模块
> 3。创建主窗口类
> 4。向主窗口类添加各种功能
> 5。创建不同类型的 QtWidgets
> 6。创建一个添加条形图的绘图窗口
> 7。创建一个网格布局，并添加不同的小部件和绘图窗口
> 8。将布局小部件设置为窗口的中心小部件

下面是实现

## 蟒蛇 3

```py
# importing Qt widgets
from PyQt5.QtWidgets import * import sys

# importing pyqtgraph as pg
import pyqtgraph as pg

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("PyQtGraph")

        # setting geometry
        self.setGeometry(100, 100, 600, 500)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for components
    def UiComponents(self):

        # creating a widget object
        widget = QWidget()

        # creating a push button object
        btn = QPushButton('Push Button')

        # creating a line edit widget
        text = QLineEdit("Line Edit")

        # creating a check box widget
        check = QCheckBox("Check Box")

        # creating a plot window
        plot = pg.plot()

        # create list for y-axis
        y1 = [5, 5, 7, 10, 3, 8, 9, 1, 6, 2]

        # create horizontal list i.e x-axis
        x = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

        # create pyqt5graph bar graph item
        # with width = 0.6
        # with bar colors = green
        bargraph = pg.BarGraphItem(x = x, height = y1, width = 0.6, brush ='g')

        # add item to plot window
        # adding bargraph item to the plot window
        plot.addItem(bargraph)

        # Creating a grid layout
        layout = QGridLayout()

        # setting this layout to the widget
        widget.setLayout(layout)

        # adding widgets in the layout in their proper positions
        # button goes in upper-left
        layout.addWidget(btn, 0, 0)

        # text edit goes in middle-left
        layout.addWidget(text, 1, 0)

        # check box widget goes in bottom-left
        layout.addWidget(check, 3, 0)

        # plot window goes on right side, spanning 3 rows
        layout.addWidget(plot, 0, 1, 3, 1)

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

![](img/e6b555f5669fba191d7311359c8bf206.png)