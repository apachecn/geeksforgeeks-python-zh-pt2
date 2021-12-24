# Python Tkinter–无框架窗口

> 原文:[https://www . geesforgeks . org/python-tkinter-无框架-window/](https://www.geeksforgeeks.org/python-tkinter-frameless-window/)

**先决条件:** [Python 图形用户界面–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中，tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。

要创建无框架窗口，我们将使用*overrided direct()*方法。

**语法:**

```py
root.overrideredirect(value)
```

要创建无框窗口，我们将在 *over ride redirect()* 方法中传递值 **True** 或 **1** 作为参数。

### **创建正常窗口**

下面是创建正常 *tkinter* 窗口的程序。

## 蟒蛇 3

```py
# Import module
from tkinter import *

# Create object
root = Tk()

# Adjust size
root.geometry("400x400")

# Execute tkinter
root.mainloop()
```

**输出:**

![](img/4f4f1781fc990854e5f4409d992e969e.png)

**框架窗**

### **创建无框窗口**

下面是使用*overrided direct()*方法在 python 中创建无框架 *tkinter* 窗口的程序。

## 蟒蛇 3

```py
# Import module
from tkinter import *

# Create object
root = Tk()

# Adjust size
root.geometry("400x400")

# Use overrideredirect() method
root.overrideredirect(True)

# Execute tkinter
root.mainloop()
```

**输出:**

![](img/32783ee2875df1003891d206a4456362.png)

**无框窗**