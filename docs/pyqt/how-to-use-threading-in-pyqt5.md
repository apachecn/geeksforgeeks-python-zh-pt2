# PyQt5 中如何使用线程？

> 原文:[https://www . geeksforgeeks . org/如何使用 pyqt5 中的线程/](https://www.geeksforgeeks.org/how-to-use-threading-in-pyqt5/)

**先决条件:** [PyQt5](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/) 和[多线程](https://www.geeksforgeeks.org/multithreading-python-set-1/)

多线程是指通过在线程之间快速切换对 CPU 的控制来同时执行多个线程(称为上下文切换)。Python 全局解释器锁限制一次只能运行一个线程，即使机器包含多个处理器。​

在本文中，我们将学习如何在 Pyqt5 中使用线程。创建图形用户界面时，需要在后端进行多项工作/操作。假设我们想同时执行 4 个操作。这里的问题是，每个操作都是逐个执行的。在一个操作的执行过程中，图形用户界面窗口也不会移动，这就是为什么我们需要线程。下面给出了两种实现，这显然有助于更好地理解它们的区别。

**接近**

*   需要导入库
*   创建一个简单的窗口
*   带命令的添加按钮
*   运行 Pyqt5

**无螺纹**

在没有线程的情况下工作，会使进程延迟。此外，在完全执行之前，窗口不会移动。

## 蟒蛇 3

```
# Import Module
import sys
from PyQt5.QtWidgets import *
import time

class ListBox(QWidget):

    def __init__(self):
        super().__init__()

        self.Button()

    def Button(self):
        # Add Push Button
        clear_btn = QPushButton('Click Me', self)
        clear_btn.clicked.connect(self.Operation)

        # Set geometry
        self.setGeometry(200, 200, 200, 200)

        # Display QlistWidget
        self.show()

    def Operation(self):
        print("time start")
        time.sleep(10)
        print("time stop")

if __name__ == '__main__':
    app = QApplication(sys.argv)

    # Call ListBox Class
    ex = ListBox()

    # Close the window
    sys.exit(app.exec_())
```

**输出:**

<video class="wp-video-shortcode" id="video-558260-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210214121328/FreeOnlineScreenRecorderProject14.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210214121328/FreeOnlineScreenRecorderProject14.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210214121328/FreeOnlineScreenRecorderProject14.mp4)</video>

**带螺纹**

每当我们点击**“点击我”**按钮，它就会调用**线程()**方法。在线程方法内部，我们正在创建一个**线程对象**，在这里我们定义我们的函数名。

## 蟒蛇 3

```
# Import Module
import sys
from PyQt5.QtWidgets import *
import time
from threading import *

class ListBox(QWidget):

    def __init__(self):
        super().__init__()

        self.Button()

    def Button(self):
        # Add Push Button
        clear_btn = QPushButton('Click Me', self)
        clear_btn.clicked.connect(self.thread)

        # Set geometry
        self.setGeometry(200, 200, 200, 200)

        # Display QlistWidget
        self.show()

    def thread(self):
        t1=Thread(target=self.Operation)
        t1.start()

    def Operation(self):
        print("time start")
        time.sleep(10)
        print("time stop")

if __name__ == '__main__':
    app = QApplication(sys.argv)

    # Call ListBox Class
    ex = ListBox()

    # Close the window
    sys.exit(app.exec_())
```

**输出:**

<video class="wp-video-shortcode" id="video-558260-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210214121330/FreeOnlineScreenRecorderProject15.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210214121330/FreeOnlineScreenRecorderProject15.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210214121330/FreeOnlineScreenRecorderProject15.mp4)</video>