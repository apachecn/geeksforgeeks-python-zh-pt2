# PyQt5 QSlider | Python

> 哎哎哎::1230【https://www . geeksforgeeks . org/pyqt 5-qslider-python/

PyQt5 中的**滑块**用于在指示器的帮助下设置一个值，该指示器可以在图形幻灯片或条上来回移动。很多时候，我们需要提供介于一个范围内的值，在这种情况下，滑块非常有用。`QSlider` 是用于在应用程序中添加滑块的类。

**示例:**

窗口有一个滑块和一个标签。移动滑块的指示器时，文本的大小会放大或缩小。

```
from PyQt5 import QtCore, QtGui, QtWidgets
import sys

class Ui_MainWindow(object):

    def setupUi(self, MainWindow):

        MainWindow.resize(550, 393)
        self.centralwidget = QtWidgets.QWidget(MainWindow)
        self.centralwidget.setObjectName("centralwidget")

        self.slider = QtWidgets.QSlider(self.centralwidget)
        self.slider.setGeometry(QtCore.QRect(190, 100, 160, 16))
        self.slider.setOrientation(QtCore.Qt.Horizontal)

        # After each value change, slot "scaletext" will get invoked.
        self.slider.valueChanged.connect(self.scaletext)

        self.label = QtWidgets.QLabel(self.centralwidget)
        self.label.setGeometry(QtCore.QRect(230, 150, 301, 161))

        # set initial font size of label.
        self.font = QtGui.QFont()
        self.font.setPointSize(7)
        self.label.setFont(self.font)
        MainWindow.setCentralWidget(self.centralwidget)

        self.retranslateUi(MainWindow)
        QtCore.QMetaObject.connectSlotsByName(MainWindow)

    def retranslateUi(self, MainWindow):
        _translate = QtCore.QCoreApplication.translate
        MainWindow.setWindowTitle(_translate("MainWindow", "MainWindow"))
        self.label.setText(_translate("MainWindow", "QSlider"))

    def scaletext(self, value):
        # Change font size of label. Size value could 
        # be anything consistent with the dimension of label.
        self.font.setPointSize(7 + value//2)
        self.label.setFont(self.font)

if __name__ == "__main__": 
    app = QtWidgets.QApplication(sys.argv) 

    MainWindow = QtWidgets.QMainWindow() 
    ui = Ui_MainWindow() 
    ui.setupUi(MainWindow) 
    MainWindow.show() 
    sys.exit(app.exec_()) 
```

**输出:**

<video class="wp-video-shortcode" id="video-346224-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://contribute.geeksforgeeks.org/wp-content/uploads/qslider.mp4?_=1">[https://contribute.geeksforgeeks.org/wp-content/uploads/qslider.mp4](https://contribute.geeksforgeeks.org/wp-content/uploads/qslider.mp4)</video>