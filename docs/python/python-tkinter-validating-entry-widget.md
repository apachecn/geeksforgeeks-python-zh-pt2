# Python Tkinter–验证条目小部件

> 原文:[https://www . geesforgeks . org/python-tkinter-validating-entry-widget/](https://www.geeksforgeeks.org/python-tkinter-validating-entry-widget/)

Python 提供了各种框架来处理图形用户界面应用程序。 [Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 或 Tk 接口是构建基于 GUI 的应用程序最广泛使用的 Python 接口之一。有些应用程序需要验证文本字段，以防止用户在提交表单之前输入无效内容。Python 允许通过使用回调函数进行变量跟踪来进行输入验证。每当在条目小部件中添加/删除输入时，都会调用该函数。有些应用程序会在提交表单时验证输入，但是下面这段代码会对键盘上的每一个按键进行验证。

1.  **导入 tkinter 模块**

    ```
    import tkinter
    ```

2.  **进口 tkinter 子模块**

    ```
    from tkinter import *
    ```

3.  **Define the “callback” function**

    ```
    def callback(input):
        if input.isdigit():
            print(input)
            return True

        elif input is "":
            print(input)
            return True

        else:
            print(input)
            return False
    ```

    **解释**
    回调函数检查条目小部件中的输入是否有效。如果条目有效，则返回真或假。在本例中，通过键盘输入的输入被检查为数字类型。如果输入是数字类型，那么回调函数返回真。对于删除操作，回调函数返回 true，因为输入是" "。然而，对于任何非数字输入，回调函数返回 false。

4.  **Creating the parent window**

    ```
    root=Tk()
    ```

    **语法:** Tk(screenName=None，baseName=None，className='Tk '，useTk=1)
    **参数:**在本例中，Tk 类是不带参数实例化的。
    **解释**
    这个方法创建一个父小部件，它通常是一个应用程序的主窗口。

5.  **Creating Entry widget**

    ```
    e=Entry(root)
    ```

    **语法:**入口(主，* *选项)
    **参数:**

    *   **主:**代表父窗口(此处为根)。
    *   **选项:**支持的选项有 bg、bd、command、光标、字体、exportselection、alignment、relief、highlightcolor、fg、selectbackground、selectforeground、selectborderwidth、show、xscrollcommand、state、textvariable 和 width。

    **返回值:**返回字符串(。！条目)。
    **解释**
    该方法用于在父微件(根)上创建 Entry 微件。

6.  **Specify the position of Entry widget within the parent window**

    ```
    e.place(x=50, y=50)
    ```

    **语法:**地点(x，y)
    **参数:**

    *   **x:** 入口小部件相对于父小部件沿 X 轴的位置。
    *   **y:** 条目小部件相对于父小部件沿 Y 轴的位置。

    **说明:**
    此方法指定 Entry 小部件在父窗口(根)中的位置。

7.  **Register the callback function**

    ```
    reg=root.register(callback)
    ```

    **语法:**寄存器(功能)
    **参数:**

    *   **函数:**将被调用以验证入口小部件中的输入的函数。

    **返回值:**这个方法返回一个可以用来调用函数的字符串。
    **解释**
    register()方法返回一个分配给变量‘reg’的字符串，该变量用于在后期调用回调函数。

8.  **Call the callback function to validate the input in Entry widget**

    ```
    e.config(validate="key", validatecommand=(reg, '%P'))
    ```

    **语法:**配置(validate =“key”，validatecommand=(reg，' % P ')
    **参数:**

    *   **验证:**该选项用于指定何时调用回调函数来验证输入。“键”值指定每当任何击键(从键盘输入)改变小部件的内容时进行验证。
    *   **validatecommand:** 此选项用于指定回调函数。该函数不直接调用，而是传递一个在前面步骤中注册的变量。传递“%P”是为了表示如果允许更改，文本将具有的值。

    **解释**
    验证选项支持其他值，如焦点、焦点输入、焦点输出、全部和无。默认值为“无”，这意味着没有验证。
    Validatecommand 选项支持其他值，如%d、%i、%s、%S、%v、%V 和%W。可以为要传递给 Python 函数的每个参数添加替换百分比
    Entry 小部件还支持 invalidcommand 选项，每当 Validatecommand 返回 False 时，该选项就会调用一个函数。
    可根据用户要求使用。

9.  **Run the application**

    ```
    root.mainloop()
    ```

    **语法:mainloop()**
    **解释**
    main loop()是一个无限循环，用于在窗口未关闭的情况下运行应用程序。

**入口小部件验证的完整代码**

```
import tkinter
from tkinter import *

def callback(input):

    if input.isdigit():
        print(input)
        return True

    elif input is "":
        print(input)
        return True

    else:
        print(input)
        return False

root = Tk()

e = Entry(root)
e.place(x = 50, y = 50)
reg = root.register(callback)

e.config(validate ="key", 
         validatecommand =(reg, '% P'))

root.mainloop()
```

**输出:**(推荐全屏查看)

<video class="wp-video-shortcode" id="video-386792-1" width="665" height="376" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200318144811/validationOutput.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200318144811/validationOutput.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200318144811/validationOutput.mp4)</video>

**解释**
当我们使用键盘输入数字时，回调函数返回 true，并且该值在输入小部件中是允许的。但是，从键盘输入字母时，回调函数返回 false，并且不允许在条目小部件中输入该值。为了更清楚地了解回调函数的工作原理，通过键盘发送的输入被打印在控制台上。可以看到，任何非数字输入都会打印在控制台上，但在条目小部件中是不允许的。此外，条目小部件中允许插入和删除数字。