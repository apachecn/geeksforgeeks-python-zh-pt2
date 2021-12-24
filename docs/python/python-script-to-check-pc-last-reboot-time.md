# Python 脚本检查电脑上次重启时间

> 原文:[https://www . geesforgeks . org/python-脚本检查-PC-最后一次重新启动-时间/](https://www.geeksforgeeks.org/python-script-to-check-pc-last-reboot-time/)

[psutil](https://www.geeksforgeeks.org/psutil-module-in-python/) 是一个跨平台的库，用于在 Python 中检索关于正在运行的进程和系统利用率(CPU、内存、磁盘、网络、传感器)的信息。下面的 Python 脚本可以在 Windows 和 Linux 中运行。可以通过以下方式使用终端安装 psutil 库:

**在窗口:**

```
pip install psutil
```

**在**T2【Linux:

```
sudo apt-get install gcc python3-dev
sudo pip3 install psutil
```

**代码:**

## 蟒蛇 3

```
import psutil
import datetime

# returns the time in seconds since the epoch
last_reboot = psutil.boot_time()

# converting the date and time in readable format
print(datetime.datetime.fromtimestamp(last_reboot))
```

**输出:**

```
2020-08-20 16:46:48
```

**说明:**

**psutil.boot_time()** 返回自纪元以来以秒为单位的系统启动时间。它是自 Unix 纪元以来经过的秒数减去闰秒；Unix 纪元是世界协调时 1970 年 1 月 1 日 00:00:00。
要将此时间转换为日期时间，我们使用**frontimestage()**，它返回本地日期和时间。