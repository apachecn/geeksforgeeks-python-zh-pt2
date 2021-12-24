# 印度的冠状病毒详情–使用 Python PyQt5

> 原文:[https://www . geesforgeks . org/corona-virus-details-in-India-using-python-pyqt 5/](https://www.geeksforgeeks.org/corona-virus-details-in-india-using-python-pyqt5/)

在本文中，我们将了解如何创建 PyQt5 应用程序，该应用程序讲述冠状病毒病例的详细信息，即印度各地的总病例、恢复病例和总死亡人数，即各州的结果。

> **所需模块和安装:**
> 
> **[PyQt5](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/) :** PyQt 是跨平台 GUI 工具包 Qt 的 Python 绑定，实现为 Python 插件。PyQt 是由英国河岸计算公司开发的自由软件。
> 
> **[Requests](https://www.geeksforgeeks.org/python-introduction-to-pyqt5/):**Requests 可以让你极其轻松的发送 HTTP/1.1 请求。没有必要手动添加查询字符串到你的网址。
> 
> **美人汤:**美人汤是一个库，可以方便的从网页上刮取信息。它位于 HTML 或 XML 解析器之上，为迭代、搜索和修改解析树提供了 Pythonic 习惯用法。

> **实施步骤:**
> 
> 1.获取冠状病毒状态列表并将其存储在列表中
> 2。创建一个不可编辑的组合框，设置其几何形状
> 3。从列表中获取州名并将其添加到组合框
> 4 中。创建三个标签来显示关于总病例、恢复病例和死亡病例的信息
> 5。为每个标签设置几何图形、对齐方式和边框
> 6。向组合框
> 7 添加动作。在动作过滤列表中获取所需信息
> 8。借助标签在屏幕上显示输出

下面是实现

```py
# importing libraries
from PyQt5.QtWidgets import * 
from PyQt5 import QtCore, QtGui
from PyQt5.QtGui import * 
from PyQt5.QtCore import * 
from bs4 import BeautifulSoup
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
        self.corona()

        # calling method
        self.UiComponents()

        # showing all the widgets
        self.show()

    def corona(self):
        extract_contents = lambda row: [x.text.replace('\n', '') for x in row]
        URL = 'https://www.mohfw.gov.in/'

        SHORT_HEADERS = ['SNo', 'State', 'Indian-Confirmed',
                         'Foreign-Confirmed', 'Cured', 'Death']

        response = requests.get(URL).content
        soup = BeautifulSoup(response, 'html.parser')
        header = extract_contents(soup.tr.find_all('th'))

        self.stats = []
        all_rows = soup.find_all('tr')

        for row in all_rows:
            stat = extract_contents(row.find_all('td'))
            if stat:
                if len(stat) == 5:
                    # last row
                    stat = ['', *stat]
                    self.stats.append(stat)
                elif len(stat) == 6:
                    self.stats.append(stat)

        self.stats[-1][1] = "Total Cases"

        self.stats.remove(self.stats[-1])

        # method for widgets
    def UiComponents(self):

        # creating a combo box widget
        self.combo_box = QComboBox(self)

        # setting geometry to combo box
        self.combo_box.setGeometry(100, 50, 200, 40)

        # setting font
        self.combo_box.setFont(QFont('Times', 10))

        # adding items to combo box
        for i in self.stats:

            self.combo_box.addItem(i[2])

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

        # getting index
        index = self.combo_box.currentIndex()

        # getting data
        total = self.stats[index][3]
        recovered = self.stats[index][4]
        deaths = self.stats[index][5]

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

<video class="wp-video-shortcode" id="video-406380-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200423124645/screen_recorder_video_2020_23_4_12_44_10.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200423124645/screen_recorder_video_2020_23_4_12_44_10.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200423124645/screen_recorder_video_2020_23_4_12_44_10.mp4)</video>