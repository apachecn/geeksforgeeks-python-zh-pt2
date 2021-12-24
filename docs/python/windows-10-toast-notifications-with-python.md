# 带 Python 的 Windows 10 吐司通知

> 原文:[https://www . geesforgeks . org/windows-10-toast-notifications-with-python/](https://www.geeksforgeeks.org/windows-10-toast-notifications-with-python/)

Python 是一种通用语言，可以用来开发桌面和网络应用程序。通过使用 Python 中名为 **win10toast** 的包，我们可以创建桌面通知。当某个事件发生时，获得通知是一种简单的方法。

该软件包在 Pypi 中可用，并使用 pip 安装。

```py
pip install win10toast
```

关于`show_toast()`功能:

> **语法:**show _ toast(title = ' Notification '，message= '消息来了'，icon_path=None，duration=5，threaded=False)
> 
> **参数:**
> **标题**:包含通知标题。
> **消息**:包含通知消息。
> **图标 _ 路径**:包含到的路径。ico 文件。
> **持续时间**":指定通知销毁活动持续时间。

要创建通知，我们必须导入 win10toast 模块。然后创建一个对象到`ToastNotifier` 类，通过使用方法`show_toast`我们创建一个通知。它包含*标题*或通知标题、实际消息、通知持续时间和通知图标。`show_toast` 方法是通知设置的一个实例。

**代码#1:**

```py
# import win10toast 
from win10toast import ToastNotifier

# create an object to ToastNotifier class
n = ToastNotifier()

n.show_toast("GEEKSFORGEEKS", "You got notification", duration = 10,
 icon_path ="https://media.geeksforgeeks.org/wp-content/uploads/geeks.ico")
```

**输出:**
![null](img/c6bc7baac37b3406163791ff2a60b391.png)

**代码#2:**

```py
# import win10toast 
from win10toast import ToastNotifier

# create an object to ToastNotifier class
n = ToastNotifier()

n.show_toast("GEEKSFORGEEKS", "Notification body", duration = 20,
  icon_path ="https://media.geeksforgeeks.org/wp-content/uploads/geeks.ico")
```

**输出:**
![null](img/81b328f97096b6c0fc029c5404876657.png)