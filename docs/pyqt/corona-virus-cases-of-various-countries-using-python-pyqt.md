# 各国冠状病毒病例–使用 Python PyQt

> 原文:[https://www . geeksforgeeks . org/corona-virus-case-of-of-conventi-of-country-use-python-pyqt/](https://www.geeksforgeeks.org/corona-virus-cases-of-various-countries-using-python-pyqt/)

在本文中，我们将了解如何创建 PyQt5 应用程序，该应用程序仅通过键入国家/地区的名称来讲述冠状病毒病例的详细信息，即总病例数、恢复病例数和总死亡人数。

> **所需模块和安装:**
> 
> **[PyQt5](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/) :** PyQt 是跨平台 GUI 工具包 Qt 的 Python 绑定，实现为 Python 插件。PyQt 是由英国河岸计算公司开发的自由软件。
> 
> **[Requests](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/):**Requests 可以让你极其轻松的发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。
> 
> **美人汤:**美人汤是一个库，可以方便的从网页上刮取信息。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

> **实施步骤:**
> 
> 1.创建一个不可编辑的组合框，设置其几何图形
> 2。创建包含国家名称的国家列表，并将其添加到组合框
> 3 中。创建三个标签来显示关于总病例、恢复病例和死亡病例的信息
> 4。为每个标签
> 5 设置几何图形、对齐和边框。将动作添加到组合框
> 6。在行动中，在请求美化程序
> 7 的帮助下，获取国家名称并从网站上删除数据。将原始数据转换成 html 代码，然后过滤得到所需的输出
> 8。借助标签在屏幕上显示输出

下面是实现

```
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
from bs4 import BeautifulSoup as BS
import requests
import sys

class Window(QMainWindow):

    def __init__(self):
        super().__init__()

        # setting title
        self.setWindowTitle("Python ")

        # setting geometry
        self.setGeometry(100, 100, 400, 500)

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    # method for widgets
    def UiComponents(self):

        # countries list // user can add other countries as well
        self.country = ["india", "us", "spain", "china", "russia", 
                            "pakistan", "nepal", "italy", "spain",
                                                   "uk", "brazil"]

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry to combo box
        self.combo_box.setGeometry(100, 50, 200, 40)

        # setting font
        self.combo_box.setFont(QFont('Times', 10))

        # adding items to combo box
        for i in self.country:
            i = i.upper()
            self.combo_box.addItem(i)

        # adding action to the combo box
        self.combo_box.activated.connect(self.get_cases)

        # creating label to show the total cases
        self.label_total = QLabel("Total Cases ", self)

        # setting geometry
        self.label_total.setGeometry(100, 300, 200, 40)

        # setting alignment to the text
        self.label_total.setAlignment(Qt.AlignCenter)

        # adding border to the label
        self.label_total.setStyleSheet("border : 2px solid black;")

        # creating label to show the recovered cases
        self.label_reco = QLabel("Recovered Cases ", self)

        # setting geometry
        self.label_reco.setGeometry(100, 350, 200, 40)

        # setting alignment to the text
        self.label_reco.setAlignment(Qt.AlignCenter)

        # adding border
        self.label_reco.setStyleSheet("border : 2px solid black;")

        # creating label to show death cases
        self.label_death = QLabel("Total Deaths ", self)

        # setting geometry
        self.label_death.setGeometry(100, 400, 200, 40)

        # setting alignment to the text
        self.label_death.setAlignment(Qt.AlignCenter)

        # adding border to the label
        self.label_death.setStyleSheet("border : 2px solid black;")

    # method called by push
    def get_cases(self):

        # getting country name
        index = self.combo_box.currentIndex()
        country_name = self.country[index]

        # creating url using country name
        url = "https://www.worldometers.info/coronavirus/country/" + country_name + "/"

        # getting the request from url
        data = requests.get(url)

        # converting the text
        soup = BS(data.text, 'html.parser')

        # finding meta info for cases
        cases = soup.find_all("div", class_="maincounter-number")

        # getting total cases number
        total = cases[0].text

        # filtering it
        total = total[1: len(total) - 2]

        # getting recovered cases number
        recovered = cases[2].text

        # filtering it
        recovered = recovered[1: len(recovered) - 1]

        # getting death cases number
        deaths = cases[1].text

        # filtering it
        deaths = deaths[1: len(deaths) - 1]

        # show data through labels
        self.label_total.setText("Total Cases : " + total)
        self.label_reco.setText("Recovered Cases : " + recovered)
        self.label_death.setText("Total Deaths : " + deaths)

# create pyqt5 app
App = QApplication(sys.argv)

# create the instance of our Window
window = Window()

window.show()

# start the app
sys.exit(App.exec())
```

**输出:**

<video class="wp-video-shortcode" id="video-406378-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200423025548/screen_recorder_video_2020_23_4_02_55_12.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200423025548/screen_recorder_video_2020_23_4_02_55_12.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200423025548/screen_recorder_video_2020_23_4_02_55_12.mp4)</video>