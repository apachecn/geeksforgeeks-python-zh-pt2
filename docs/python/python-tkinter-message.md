# python tkinter–message

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-tkinter-message/

Python 为开发图形用户界面提供了多种选择。在所有的 GUI 方法中，Tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 搭配 Tkinter 是创建 GUI 应用程序最快最简单的方法。使用 Tkinter 创建图形用户界面是一项简单的任务。

**注意:**更多信息请参考[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

## 消息小部件

消息小部件用于向用户显示关于 python 应用程序行为的消息。消息文本包含多行。

**语法:**
下面给出了使用该消息的语法。

```py
w = Message( master, options)
```

**参数:**

*   **主**:此参数用于表示父窗口。
*   **选项**:有很多可用的选项，可以作为键值对使用，用逗号分隔。

**选项:**
以下是常用选项，可用于此小部件:-

*   **锚点:**此选项用于决定文本在空间内的确切位置。它的默认值是“中心”。
*   **bg:** 此选项用于表示正常的背景颜色。
*   **位图:**此选项用于显示单色图像。
*   **bd:** 此选项用于表示边框的大小，默认值为 2 像素。
*   **光标:**使用该选项，鼠标光标在打字时会变成该模式。
*   **字体:**该选项用于表示文本使用的字体。
*   **fg:** 此选项用于表示渲染文本所用的颜色。
*   **高度:**此选项用于表示消息上的文本行数。
*   **图像:**该选项用于在小部件上显示图形图像。
*   **对齐:**此选项用于控制文本的对齐方式:居中、向左或向右。
*   **padx:** 该选项用于表示小部件和文本的左右留出多少空间。它的默认值是 1 像素。
*   **pady:** 这个选项用来表示在小部件上面和下面要留多少空间。它的默认值是 1 像素。
*   **浮雕:**小部件边框的类型。它的默认值设置为“平面”。
*   **文本:**此选项用于使用换行符(" \n ")显示多行文本。
*   **变量:**该选项用于表示跟踪小部件状态的关联变量。
*   **宽度:**该选项用于表示小部件的宽度。并且还以文本形式表示的字符数量来表示。
*   **包裹长度:**该选项将文本分成若干段。

**示例:**

```py
from tkinter import *

root = Tk()
root.geometry("300x200")

w = Label(root, text ='GeeksForGeeks', font = "50") 
w.pack()

msg = Message( root, text = "A computer science portal for geeks")  

msg.pack()  

root.mainloop() 
```

**输出:**
![](img/58117149e6e8ddc0ff2100fe726c90fe.png)