# Python-Tkinter Treeview 滚动

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-tkinter-tree view-scroll bar/

Python 有几个构建 GUI 的选项， [python tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 就是其中之一。它是 Python 的标准*图形用户界面*库，有助于轻松制作图形用户界面应用程序。它为 *tk* 图形用户界面工具包提供了一个高效的面向对象的界面。它也有多个控件，如文本框、滚动条、按钮等。此外，Tkinter 还有一些几何管理方法，即 *pack()，grid()，place()* ，有助于组织小部件。
**注:**更多信息请参考[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

## 滚动条树视图

当滚动条使用*树形视图*小部件时，这种类型的滚动条被称为*树形视图滚动条*。其中，树视图小部件有助于以列的形式在树的右侧显示树中列出的每个项目的多个特征。但是，它可以在 tkinter 支持的一些小部件和几何管理方法的帮助下，使用 python 中的 tkinter 来实现。
以下示例使用 Python-tkinter 说明了**树形视图滚动条**的用法:
**示例 1:**

## 计算机编程语言

```py
# Python program to illustrate the usage of
# treeview scrollbars using tkinter

from tkinter import ttk
import tkinter as tk

# Creating tkinter window
window = tk.Tk()
window.resizable(width = 1, height = 1)

# Using treeview widget
treev = ttk.Treeview(window, selectmode ='browse')

# Calling pack method w.r.to treeview
treev.pack(side ='right')

# Constructing vertical scrollbar
# with treeview
verscrlbar = ttk.Scrollbar(window,
                           orient ="vertical",
                           command = treev.yview)

# Calling pack method w.r.to vertical
# scrollbar
verscrlbar.pack(side ='right', fill ='x')

# Configuring treeview
treev.configure(xscrollcommand = verscrlbar.set)

# Defining number of columns
treev["columns"] = ("1", "2", "3")

# Defining heading
treev['show'] = 'headings'

# Assigning the width and anchor to  the
# respective columns
treev.column("1", width = 90, anchor ='c')
treev.column("2", width = 90, anchor ='se')
treev.column("3", width = 90, anchor ='se')

# Assigning the heading names to the
# respective columns
treev.heading("1", text ="Name")
treev.heading("2", text ="Sex")
treev.heading("3", text ="Age")

# Inserting the items and their features to the
# columns built
treev.insert("", 'end', text ="L1",
             values =("Nidhi", "F", "25"))
treev.insert("", 'end', text ="L2",
             values =("Nisha", "F", "23"))
treev.insert("", 'end', text ="L3",
             values =("Preeti", "F", "27"))
treev.insert("", 'end', text ="L4",
             values =("Rahul", "M", "20"))
treev.insert("", 'end', text ="L5",
             values =("Sonu", "F", "18"))
treev.insert("", 'end', text ="L6",
             values =("Rohit", "M", "19"))
treev.insert("", 'end', text ="L7",
             values =("Geeta", "F", "25"))
treev.insert("", 'end', text ="L8",
             values =("Ankit", "M", "22"))
treev.insert("", 'end', text ="L10",
             values =("Mukul", "F", "25"))
treev.insert("", 'end', text ="L11",
             values =("Mohit", "M", "16"))
treev.insert("", 'end', text ="L12",
             values =("Vivek", "M", "22"))
treev.insert("", 'end', text ="L13",
             values =("Suman", "F", "30"))

# Calling mainloop
window.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-386887-1" width="640" height="360" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200319194643/python-tkinter-treeview-scrollbar.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200319194643/python-tkinter-treeview-scrollbar.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200319194643/python-tkinter-treeview-scrollbar.webm)</video>

在上面的程序中，我们使用了 *pack()* 方法的几何管理方法。而且，我们只根据代码的要求构造了垂直滚动条，但是你可以根据你的要求构造两个滚动条。此外，这里使用锚点来定义文本的位置。但是，您也可以使用其他几何管理方法来构建 treeview 滚动条。