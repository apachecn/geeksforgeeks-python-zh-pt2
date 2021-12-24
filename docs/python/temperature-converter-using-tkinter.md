# 使用 Tkit 的温度转换器

> 原文:[https://www . geesforgeks . org/temperature-converter-use-tkinter/](https://www.geeksforgeeks.org/temperature-converter-using-tkinter/)

**前提条件:**[python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

Python Tkinter 是一个 GUI 编程包或内置库。Tkinter 为 Tk GUI 工具包提供了一个强大的面向对象的界面。Python 搭配 Tkinter 是创建 GUI 应用程序最快最简单的方法。使用 Tkinter 创建图形用户界面是一项简单的任务。

**进场:**

*   从部分导入模块–tkinter、functools
*   创建主窗口
*   向主窗口添加一些小部件:按钮、条目、标签
*   显示消息
*   在小部件上应用事件触发器。

下面是实现。

```py
import tkinter as tk
from tkinter import messagebox
from functools import partial

# Declaration of global variable
temp_Val = "Celsius"

# getting drop down value
def store_temp(set_temp):
    global temp_Val
    temp_Val = set_temp

# Conversion of  temperature
def call_convert(rlabel1,  inputn):
    temp = inputn.get()

    if temp_Val == 'Celsius':

        # Conversion of celsius temperature to fahrenheit
        f = float((float(temp) * 9 / 5) + 32)
        rlabel1.config(text ="%.1f Fahrenheit" % f)
        messagebox.showinfo("Temperature Converter",
                            "Successfully converted to Fahrenheit ", )

    if temp_Val == 'Fahrenheit':

        # Conversion of fahrenheit temperature 
        # to celsius
        c = float((float(temp) - 32) * 5 / 9)
        rlabel1.config(text ="%.1f Celsius" % c)
        messagebox.showinfo("Temperature Converter", 
                            "Successfully converted to Celsius ")
    return

# creating Tk window
root = tk.Tk()

# setting geometry of tk window
root.geometry('300x150 + 600 + 200')

# Using title() to display a message in the
# dialogue box of the message in the title bar
root.title('Temperature Converter')

# Lay out widgets
root.grid_columnconfigure(1, weight = 1)
root.grid_rowconfigure(1, weight = 1)

inputNumber = tk.StringVar()
var = tk.StringVar()

# label and entry field
input_label = tk.Label(root, text ="Enter temperature")
input_entry = tk.Entry(root, textvariable = inputNumber)
input_label.grid(row = 1)
input_entry.grid(row = 1, column = 1)
result_label = tk.Label(root)
result_label.grid(row = 3, columnspan = 4)

# drop down setup
dropDownList = ["Celsius", "Fahrenheit"]
drop_down = tk.OptionMenu(root, var, *dropDownList,
                          command = store_temp)
var.set(dropDownList[0])
drop_down.grid(row = 1, column = 2)

# button widget
call_convert = partial(call_convert, result_label,
                       inputNumber)
result_button = tk.Button(root, text ="Convert",
                          command = call_convert)
result_button.grid(row = 2, columnspan = 2)

# infinite loop which is required to
# run tkinter program infinitely
# until an interrupt occurs
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-432228-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200615155214/temperature-converter.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200615155214/temperature-converter.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200615155214/temperature-converter.mp4)</video>