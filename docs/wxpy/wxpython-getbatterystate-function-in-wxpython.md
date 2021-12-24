# wxPython–wxPython

中的 GetBatteryState()函数

> 原文:[https://www . geeksforgeeks . org/wxpython-getbatterystate-function-in-wxpython/](https://www.geeksforgeeks.org/wxpython-getbatterystate-function-in-wxpython/)

在本文中，我们将了解 wx。GetBatteryState()是 wxPython 中存在的内置父函数。GetBatteryState()以电池 _ 正常 _ 状态、电池 _ 低 _ 状态、电池 _ 临界 _ 状态、电池 _ 关机 _ 状态或电池 _ 未知 _ 状态之一返回电池状态。

BATTERY_UNKNOWN_STATE 也是未实现此功能的平台上的默认设置(目前除了 MS Windows 外，其他地方都有)。

> **语法:** wx。GetBatteryState()
> 
> **参数:**无参数
> 
> **返回类型:** wx。BatteryState

**代码示例:**

```py
import wx

class Example(wx.Frame):

    def __init__(self, *args, **kwargs):
        super(Example, self).__init__(*args, **kwargs)

        self.InitUI()

    def InitUI(self):

        self.locale = wx.Locale(wx.LANGUAGE_ENGLISH)
        # print battery state
        # 0 for wx.BATTERY_NORMAL_STATE
        # 1 for wx.BATTERY_LOW_STATE
        # 2 for wx.BATTERY_CRITICAL_STATE
        # 3 for wx.BATTERY_SHUTDOWN_STATE
        # 4 for wx.BATTERY_UNKNOWN_STATE
        print(wx.GetBatteryState())

def main():
    app = wx.App()
    ex = Example(None)
    ex.Show()
    app.MainLoop()

if __name__ == '__main__':
    main()
```

**输出:**

```py
1

```

也就是 wx。电池低状态。