# 创建单圈计时器的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-to-create-a-lap-timer/](https://www.geeksforgeeks.org/python-program-to-create-a-lap-timer/)

在本文中，我们将使用 Python 制作一个简单的计时器来计算单圈时间间隔。

### 使用的模块

**时间:**该模块提供各种与时间相关的功能。它是 Python 标准库的一部分，不需要安装。

**进场:**
用户需要按回车键完成每一圈。计时器一直计时，直到按下 CTRL+C。对于每一圈，我们通过从上一圈结束时的总时间中减去当前时间来计算圈速。*时间*模块的*时间()*功能以毫秒为单位返回当前历元时间。

下面是实现:

```py
# importing libraries
import time

# Timer starts
starttime=time.time()
lasttime=starttime
lapnum=1

print("Press ENTER to count laps.\nPress CTRL+C to stop")

try:
     while True:

          # Input for the ENTER key press
          input()

          # The current lap-time
          laptime=round((time.time() - lasttime), 2)

          # Total time elapsed 
          # since the timer started
          totaltime=round((time.time() - starttime), 2)

          # Printing the lap number,
          # lap-time and total time
          print("Lap No. "+str(lapnum)) 
          print("Total Time: "+str(totaltime))
          print("Lap Time: "+str(laptime))

          print("*"*20)

          # Updating the previous total time
          # and lap number
          lasttime=time.time()
          lapnum+=1

# Stopping when CTRL+C is pressed
except KeyboardInterrupt:
     print("Done")
```

**输出:**

```py
ENTER to count laps.
Press CTRL+C to stop

Lap No. 1
Total Time: 1.09
Lap Time: 1.09
********************

Lap No. 2
Total Time: 2.66
Lap Time: 1.41
********************

Lap No. 3
Total Time: 5.06
Lap Time: 2.23
********************

Lap No. 4
Total Time: 5.63
Lap Time: 0.4
********************
Done

```