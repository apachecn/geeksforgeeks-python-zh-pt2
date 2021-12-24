# 在 Python 中使用 Tkinter 可视化气泡排序

> 原文:[https://www . geesforgeks . org/visiting-bubble-sort-using-tkinter-in-python/](https://www.geeksforgeeks.org/visualizing-bubble-sort-using-tkinter-in-python/)

在本文中，我们将使用 Python 图形用户界面库 Tkinter 来可视化冒泡排序算法。

*   Tkinter 是一个非常容易使用和初学者友好的图形用户界面库，可以用来可视化排序算法。
*   在这里，气泡排序算法是可视化的，它通过重复交换相邻的元素/值来工作，如果它们的顺序是错误的，直到整个数组被排序。
*   想法是:**如果 arr[i] > arr[i+1]，那么交换**它们。
*   在第一次迭代中，必须扫描 N-1 个项目，最大的元素移动到它的右边位置。在第二次迭代中，第二大的项目将移动到它的正确位置，并且在第三次迭代(在项目 N-3 处停止)之后，第三大的项目将就位。因此，为了以正确的顺序放置所有元素，上述操作被执行 N-1 次。该算法的时间复杂度= **O(N <sup>2</sup> )。**

**程序:**

1.  指定范围内的随机值列表将生成为条形。
2.  不同的颜色(红色和绿色)用于显示排序过程。
3.  为了便于用户可视化，创建了合适的“速度”范围栏。
4.  “生成”和“开始”按钮分别用于创建数据条和启动排序过程。

**冒泡排序扩展码:**

这是冒泡排序算法的扩展代码，它被导入到主 Tkinter 可视化器代码中，以实现冒泡排序算法并返回排序结果。

## 蟒蛇 3

```py
# Extension Bubble Sort Code
# importing time module
import time

# function to implement bubble sort by passing
# the following parameters:
# data is passed for the set of unsorted data values
# drawdata is used to generate the data bars
# timer iis for the speed range
def bubble(data, drawData, timer):
    n = len(data)

    for i in range(n):
        for j in range(0, n-i-1):

            if data[j] > data[j+1]:
                data[j], data[j+1] = data[j+1], data[j]

                # if swapped then color becomes Green else stays Red
                drawData(data, ['Green' if x == j +
                                1 else 'Red' for x in range(len(data))])
                time.sleep(timer)

    # sorted elements generated with Green color
    drawData(data, ['Green' for x in range(len(data))])
```

**Tkit 的代码:**

在这段代码中，我们将数据值生成为不同长度和特定颜色的条。基本布局设计在一个 Tkinter 'Frame '中，当条生成和算法可视化的部分设计在一个 Tkinter 'Canvas '中。

该代码主要包含以下组件:

1.  **主机**:一个 Tkinter 框架，用于排列所有必要的组件(标签、按钮、速度条等)。)以有组织的方式
2.  **画布**:一个 Tkinter 画布，用作绘制生成的数据条并可视化排序过程的空间
3.  **生成()**:通过接受一个范围，然后将其作为参数传递给 drawData()函数来生成数据值的方法
4.  **drawData()** :生成画布上特定颜色的归一化数据值(在给定范围内)的条的方法
5.  **start_algorithm()** :按下“start”按钮时调用该功能。它通过从冒泡排序扩展代码中调用冒泡()函数来启动排序过程。

## 蟒蛇 3

```py
# code for Bubble Sort Visualizer using Python and Tkinter
from tkinter import *
from tkinter import ttk
import random
from bub_srt import bubble

# initialising root class for Tkinter
root = Tk()
root.title("Bubble Sort Visualizer")

# maximum window size
root.maxsize(900, 600)
root.config(bg="Black")
select_alg = StringVar()
data = []

# function to generate the data values by accepting a given range
def generate():
    global data

    # minval : minimum value of the range
    minval = int(minEntry.get())

    # maxval : maximum value of the range
    maxval = int(maxEntry.get())

    # sizeval : number of data values/bars to be generated
    sizeval = int(sizeEntry.get())

    # creating a blank data list which will be further
    # filled with random data values
    # within the entered range
    data = []
    for _ in range(sizeval):
        data.append(random.randrange(minval, maxval+1))

    drawData(data, ['Red' for x in range(len(data))])

# function to create the data bars by creating a canvas in Tkinter
def drawData(data, colorlist):
    canvas.delete("all")
    can_height = 380
    can_width = 550
    x_width = can_width/(len(data) + 1)
    offset = 30
    spacing = 10

    # normalizing data for rescaling real-valued numeric data within the
    # given range
    normalized_data = [i / max(data) for i in data]

    for i, height in enumerate(normalized_data):
        # top left corner
        x0 = i*x_width + offset + spacing
        y0 = can_height - height*340

        # bottom right corner
        x1 = ((i+1)*x_width) + offset
        y1 = can_height

        # data bars are generated as Red colored vertical rectangles
        canvas.create_rectangle(x0, y0, x1, y1, fill=colorlist[i])
        canvas.create_text(x0+2, y0, anchor=SE, text=str(data[i]))
    root.update_idletasks()

# function to initiate the sorting process by
# calling the extension code
def start_algorithm():
    global data
    bubble(data, drawData, speedbar.get())

# creating main user interface frame and
# basic layout by creating a frame
Mainframe = Frame(root, width=600, height=200, bg="Grey")
Mainframe.grid(row=0, column=0, padx=10, pady=5)

canvas = Canvas(root, width=600, height=380, bg="Grey")
canvas.grid(row=1, column=0, padx=10, pady=5)

# creating user interface area in grid manner
# first row components
Label(Mainframe, text="ALGORITHM", bg='Grey').grid(
    row=0, column=0, padx=5, pady=5, sticky=W)

# algorithm menu for showing the name of the sorting algorithm
algmenu = ttk.Combobox(
    Mainframe, textvariable=select_alg, values=["Bubble Sort"])
algmenu.grid(row=0, column=1, padx=5, pady=5)
algmenu.current(0)

# creating Start Button to start the sorting visualization process
Button(Mainframe, text="START", bg="Blue", command=start_algorithm).grid(
    row=1, column=3, padx=5, pady=5)

# creating Speed Bar using scale in Tkinter
speedbar = Scale(Mainframe, from_=0.10, to=2.0, length=100, digits=2,
                 resolution=0.2, orient=HORIZONTAL, label="Select Speed")
speedbar.grid(row=0, column=2, padx=5, pady=5)

# second row components
# sizeEntry : scale to select the size/number of data bars
sizeEntry = Scale(Mainframe, from_=3, to=60, resolution=1,
                  orient=HORIZONTAL, label="Size")
sizeEntry.grid(row=1, column=0, padx=5, pady=5)

# minEntry : scale to select the minimum value of data bars
minEntry = Scale(Mainframe, from_=0, to=10, resolution=1,
                 orient=HORIZONTAL, label="Minimum Value")
minEntry.grid(row=1, column=1, padx=5, pady=5)

# maxEntry : scale to select the maximum value of data bars
maxEntry = Scale(Mainframe, from_=10, to=100, resolution=1,
                 orient=HORIZONTAL, label="Maximum Value")
maxEntry.grid(row=1, column=2, padx=5, pady=5)

# creating generate button
Button(Mainframe, text="Generate", bg="Red", command=generate).grid(
    row=0, column=3, padx=5, pady=5)

# to stop automatic window termination
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-547196-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210110184510/zoom_0.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210110184510/zoom_0.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210110184510/zoom_0.mp4)</video>