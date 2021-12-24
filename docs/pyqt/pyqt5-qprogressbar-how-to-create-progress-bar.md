# PyQt5 qprogress bar–如何创建进度条？

> 原文:[https://www . geesforgeks . org/pyqt5-qprogressbar-如何创建进度条/](https://www.geeksforgeeks.org/pyqt5-qprogressbar-how-to-create-progress-bar/)

在本文中，我们将看到如何在 PyQt5 中创建进度条。为了创建进度条对象，我们将使用`**QProgressBar**`。

一个**进度条**是一个图形控制元素，用于可视化扩展计算机操作的进程，如下载、文件传输或安装。有时，图形伴随着以百分比格式表示的进度文本。

**语法:**

```
pbar = QProgressBar(self)
```

**代码:**

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
import sys
import time

class Example(QWidget):

    def __init__(self):
        super().__init__()

        # calling initUI method
        self.initUI()

    # method for creating widgets
    def initUI(self):

        # creating progress bar
        self.pbar = QProgressBar(self)

        # setting its geometry
        self.pbar.setGeometry(30, 40, 200, 25)

        # creating push button
        self.btn = QPushButton('Start', self)

        # changing its position
        self.btn.move(40, 80)

        # adding action to push button
        self.btn.clicked.connect(self.doAction)

        # setting window geometry
        self.setGeometry(300, 300, 280, 170)

        # setting window action
        self.setWindowTitle("Python")

        # showing all the widgets
        self.show()

    # when button is pressed this method is being called
    def doAction(self):

        # setting for loop to set value of progress bar
        for i in range(101):

            # slowing down the loop
            time.sleep(0.05)

            # setting value to progress bar
            self.pbar.setValue(i)

# main method
if __name__ == '__main__':

    # create pyqt5 app
    App = QApplication(sys.argv)

    # create the instance of our Window
    window = Example()

    # start the app
    sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-391333-1" width="640" height="388" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200323235746/Python-23-03-2020-23_47_46.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200323235746/Python-23-03-2020-23_47_46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200323235746/Python-23-03-2020-23_47_46.mp4)</video>