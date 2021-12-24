# Tkit 菜单中的“撕掉”属性有什么作用？

> 原文:[https://www . geesforgeks . org/what-the-the-tear off-attribute-do-in-a-tkinter-menu/](https://www.geeksforgeeks.org/what-does-the-tearoff-attribute-do-in-a-tkinter-menu/)

**先决条件:**

*   [python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)
*   [菜单](https://www.geeksforgeeks.org/python-menu-widget-in-tkinter/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中，tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 和 tkinter 是创建图形用户界面应用程序最快最简单的方法。使用 tkinter 创建图形用户界面是一项简单的任务。

### 重要术语

*   **菜单**用于创建顶层、下拉等各种类型的菜单..在 Tkinter。顶层菜单，显示在主窗口的标题栏下。

**语法:**

创建菜单

```py
menubar = Menu(root)
```

在菜单中添加文本

```py
file = Menu(menubar) 
menubar.add_cascade(label ='Your Text', menu = file)
```

*   一个**撕掉**允许你分离大多数窗口的菜单，形成浮动菜单。如果您生成一个菜单，您可以在单击顶部菜单项后在顶部看到虚线。要解决这个问题，需要在菜单声明时设置为 0。

```py
file = Menu(menubar,tearoff=0)
edit = Menu(menubar,tearoff=0)
help_ = Menu(menubar,tearoff=0)
```

*   级联用于在主菜单下创建子菜单。
*   一个**子菜单**是插入另一个菜单对象的菜单。通过将菜单添加到文件菜单而不是菜单栏，我们创建了一个子菜单。

**语法:**

```py
Object_Name.add_command(label ='Write Text')
```

### 方法

*   导入模块
*   创建普通 Tkinter 窗口
*   添加菜单
*   添加子菜单

**程序:**

## 蟒蛇 3

```py
# import Module
from tkinter import *

# creating tkinter window
root = Tk()

# set geometry
root.geometry("400x400")

# Add title
root.title('Menu Demonstration')

# Creating Menubar
menubar = Menu(root)

# Adding File Menu and SubMenus
file = Menu(menubar, tearoff=0)
menubar.add_cascade(label='File', menu=file)
file.add_command(label='New File')
file.add_command(label='Open...')
file.add_command(label='Save')

# Adding Edit Menu and SubMenus
edit = Menu(menubar, tearoff=0)
menubar.add_cascade(label='Edit', menu=edit)
edit.add_command(label='Cut')
edit.add_command(label='Copy')
edit.add_command(label='Paste')
edit.add_command(label='Select All')

# Adding Help Menu and SubMenus
help_ = Menu(menubar, tearoff=0)
menubar.add_cascade(label='Help', menu=help_)
help_.add_command(label='Tk Help')
help_.add_command(label='Demo')

# display Menu
root.config(menu=menubar)

# Execute Tkinter
root.mainloop()
```

**输出:**

不使用剥离方法

<video class="wp-video-shortcode" id="video-523594-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201203162358/FreeOnlineScreenRecorderProject2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201203162358/FreeOnlineScreenRecorderProject2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201203162358/FreeOnlineScreenRecorderProject2.mp4)</video>

**输出:**

用撕裂法

<video class="wp-video-shortcode" id="video-523594-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201203162806/FreeOnlineScreenRecorderProject3.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20201203162806/FreeOnlineScreenRecorderProject3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201203162806/FreeOnlineScreenRecorderProject3.mp4)</video>