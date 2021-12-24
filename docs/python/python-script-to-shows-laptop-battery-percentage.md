# Python 脚本显示笔记本电脑电池百分比

> 原文:[https://www . geesforgeks . org/python-脚本到显示-笔记本电脑-电池百分比/](https://www.geeksforgeeks.org/python-script-to-shows-laptop-battery-percentage/)

[psutil](https://www.geeksforgeeks.org/psutil-module-in-python/) 是一个跨平台库，用于在 Python 中检索运行进程和系统利用率(CPU、内存、磁盘、网络、传感器)的信息。下面的 Python 脚本可以在 Windows 和 Linux 中运行。通过

```py
pip install psutil

```

将 psutil 安装在车窗上

通过以下方式在 Linux 中安装 psutil:

```py
sudo apt-get install gcc python3-dev
sudo pip3 install psutil

```

**代码:**

## 计算机编程语言

```py
# python script showing battery details
import psutil

# function returning time in hh:mm:ss
def convertTime(seconds):
    minutes, seconds = divmod(seconds, 60)
    hours, minutes = divmod(minutes, 60)
    return "%d:%02d:%02d" % (hours, minutes, seconds)

# returns a tuple
battery = psutil.sensors_battery()

print("Battery percentage : ", battery.percent)
print("Power plugged in : ", battery.power_plugged)

# converting seconds to hh:mm:ss
print("Battery left : ", convertTime(battery.secsleft))
```

**输出:**

```py
Battery percentage :  57
Power plugged in :  False
Battery left :  1:58:32

```

**说明:**

PSU til . sensors . battle()返回由以下值组成的命名元组。如果未安装电池或无法确定指标，则返回无。

*   **percentage:** percentage of remaining power.
*   **Seconds:** There are about a few seconds left before the battery runs out. It is set to psutil. If charging is in progress, the power supply time is unlimited. If the value cannot be determined, set it to psutil. Power _ time _ unknown.
*   **Power supply _ plugged in:** The power supply is plugged in to be true, and it is not charged to be false, so it cannot be determined as none.