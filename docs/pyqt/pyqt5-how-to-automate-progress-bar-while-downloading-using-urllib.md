# pyqt 5–如何在使用 urllib 下载时自动运行进度条？

> 原文:[https://www . geeksforgeeks . org/pyqt 5-如何使用 urllib 自动下载进度条/](https://www.geeksforgeeks.org/pyqt5-how-to-automate-progress-bar-while-downloading-using-urllib/)

[**PyQt5**](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/) 是开发 Python GUI 桌面应用的新兴 GUI 库之一。它拥有丰富而强大的功能，可以确保生产质量的应用程序。学习 PyQt5 库是对你知识的补充。你可以开发你的消费者质量，高度专业的应用。

在本文中，我们将学习如何在 PyQt5 中自动化 [**进度条。通过自动化，我们的意思是动态改变和设置**进度条的值。**假设你在网上下载任何一个文件，想展示下载的进度，那么这篇文章肯定会对你有帮助。**](https://www.geeksforgeeks.org/pyqt5-qprogressbar-how-to-create-progress-bar/)

在本例中，我们使用[**【U】*****【rllib】***](https://www.geeksforgeeks.org/python-urllib-module/)**库来下载文件，作为其最常用的库来使用 python 下载文件。**

> ****语法:****
> 
>  **self . progress bar = qprogress bar(self)
> qprogress bar 类用于创建进度条对象。**

**首先，通过下面的代码，然后我们将解释整个事情是怎么做的。**

****代码:****

## **蟒蛇 3**

```
# importing libraries
import urllib.request
from PyQt5.QtWidgets import *
import sys

class GeeksforGeeks(QWidget):

    def __init__(self):
        super().__init__()

        # calling a defined method to initialize UI
        self.init_UI()

    # method for creating UI widgets
    def init_UI(self):

        # creating progress bar
        self.progressBar = QProgressBar(self)

        # setting its size
        self.progressBar.setGeometry(25, 45, 210, 30)

        # creating push button to start download
        self.button = QPushButton('Start', self)

        # assigning position to button
        self.button.move(50, 100)

        # assigning activity to push button
        self.button.clicked.connect(self.Download)

        # setting window geometry
        self.setGeometry(310, 310, 280, 170)

        # setting window action
        self.setWindowTitle("GeeksforGeeks")

        # showing all the widgets
        self.show()

    # when push button is pressed, this method is called
    def Handle_Progress(self, blocknum, blocksize, totalsize):

        ## calculate the progress
        readed_data = blocknum * blocksize

        if totalsize > 0:
            download_percentage = readed_data * 100 / totalsize
            self.progressBar.setValue(download_percentage)
            QApplication.processEvents()

    # method to download any file using urllib
    def Download(self):

        # specify the url of the file which is to be downloaded
        down_url = '' # specify download url here

        # specify save location where the file is to be saved
        save_loc = 'C:\Desktop\GeeksforGeeks.png'

        # Downloading using urllib
        urllib.request.urlretrieve(down_url,save_loc, self.Handle_Progress)

# main method to call our app
if __name__ == '__main__':

    # create app
    App = QApplication(sys.argv)

    # create the instance of our window
    window = GeeksforGeeks()

    # start the app
    sys.exit(App.exec())
```

****说明:****

**下面是 **urllib** 的语法，我们要研究它需要的所有参数。**

> *****语法:**URL lib . request . URL retrieve(URL、文件名、reporthook)***
> 
> ****参数:**该方法取以下参数 **:****
> 
> ****第一个参数**是要下载的文件的 url。**
> 
> **第二个参数**，如果存在，指定保存文件的文件位置(如果没有传递这个参数，这个位置将是一个自动生成名称的临时文件)。****
> 
> ******第三个参数**是一个可调用的参数，当文件被下载时将被调用，并且一个接一个地读取每个块。可调用(在本例中是一个函数 Handle_Progress)将作为三个参数传递:****
> 
> *   ****到目前为止传输的块数(块数)****
> *   ****以字节为单位的块大小(块大小)****
> *   ****文件的总大小(total size)****

****函数 *Handle_Progress* 因此接收三个参数。文件的当前下载大小通过 blocknum 和 blocksize 相乘来动态计算，并存储在变量 readed_data 中。****

****剩下的工作由计算百分比的公式来完成。我们将 readed_data 乘以 100，再除以文件的总大小。它给出了当前的下载百分比。然后我们使用 progress bar 对象的 setValue()方法将这个下载百分比设置到进度条。****

```
**self.progressBar.setValue(download_percentage)**
```

******输出:******

****<video class="wp-video-shortcode" id="video-436716-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200503011612/PyQt5-Progress-Bar-Demonstration.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200503011612/PyQt5-Progress-Bar-Demonstration.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200503011612/PyQt5-Progress-Bar-Demonstration.mp4)</video>****