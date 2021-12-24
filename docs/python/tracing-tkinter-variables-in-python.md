# 在 Python 中跟踪 Tkinter 变量

> 原文:[https://www . geesforgeks . org/tracing-tkinter-variables-in-python/](https://www.geeksforgeeks.org/tracing-tkinter-variables-in-python/)

Python 中没有跟踪变量的内置方法。但是 tkinter 支持创建变量包装器，可以通过向变量附加一个“observer”回调来实现这一点。tkinter。变量类有像 BooleanVar、DoubleVar、IntVarand StringVar 这样的构造函数，分别用于布尔值、双精度浮点值、整数和字符串，所有这些都可以注册到每次访问变量值时都会被触发的观察器。观察器保持活动状态，直到被明确删除。还需要注意的是，与观察者相关联的回调函数默认采用三个参数，即 tkinter 变量的名称、Tkinter 变量的索引(如果它是一个数组，则为空字符串)和访问模式。
在 Python 3.5 和 2.7 以上版本中，trace_variable()、trace()、trace_vdelete()和 trace_vinfo()等较旧的方法被下面提到的方法替代。

1.  **trace _ add():**
    trace _ add()方法已经替换了 trace_variable()方法。trace_add()方法用于向变量添加一个观察器，并在每次访问该值时返回回调函数的名称。

> **语法:** trace_add(self，mode，callback_name)
> **参数:**
> **模式:**它是“数组”、“读取”、“写入”、“取消设置”中的一个，或者是这类字符串的列表或元组。
> **callback_name:** 是要在 tkinter 变量上注册的回调函数的名称。

2.  **trace _ remove():**
    trace _ remove()方法取代了 trace_vdelete()方法，用于注销观察器。它返回最初通过 trace_add()方法注册观察器时使用的回调的名称。

> **语法:** trace_remove(self，mode，callback_name)
> **参数:**
> **模式:**它是“数组”、“读取”、“写入”、“取消设置”中的一种，或者是这类字符串的列表或元组。
> **callback_name:** 是要在 tkinter 变量上注册的回调函数的名称。

2.  **trace _ info():**
    trace _ info()方法已经取代了 trace_vinfo()方法和 trace()方法。它返回回调的名称。这通常用于查找要删除的回调的名称。除了 tkinter 变量本身，此方法不接受任何参数。

```py
Syntax : trace_info(self) 
```

为了更好地理解上述方法的意义，让我们举个例子，构建一个简单的小部件。虽然使用 Tkinter 变量作为 textvariable 会在每次变量更改时自动更新小部件，但有时开发人员希望在读取或修改(或更改)变量时做一些额外的处理。这就是变量跟踪的作用。我们的回调函数将在每次小部件中的文本改变时触发，并将返回一个字符串“变量已改变”。

## 蟒蛇 3

```py
# Python program to trace
# variable in tkinter

from tkinter import *

root = Tk()

my_var = StringVar()

# defining the callback function (observer)
def my_callback(var, index, mode):
    print ("Traced variable {}".format(my_var.get())

# registering the observer
my_var.trace_add('write', my_callback)

Label(root, textvariable = my_var).pack(padx = 5, pady = 5)

Entry(root, textvariable = my_var).pack(padx = 5, pady = 5)

root.mainloop()
```

让我们看看 trace_add()方法注册一个观察器的代码，每当小部件中的 textvariable 改变时，就会触发这个观察器。
**输出:**

<video class="wp-video-shortcode" id="video-370387-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200102125511/media.io_Screen-Recording-11-13-2019-10-55-21-PM.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200102125511/media.io_Screen-Recording-11-13-2019-10-55-21-PM.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200102125511/media.io_Screen-Recording-11-13-2019-10-55-21-PM.mp4)</video>