# python tkinter–spinbox range validation

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-tkinter-spinbox 范围验证/

**先决条件:**[Python GUI–Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)、[Python Tkinter–验证入口小部件](https://www.geeksforgeeks.org/python-tkinter-validating-entry-widget/)
[Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 是一个 Python GUI(图形用户界面)模块，实现快捷方便，广泛用于创建桌面应用程序。它提供了各种基本的小部件来构建图形用户界面程序。在 Tkinter 中， [Spinbox](https://www.geeksforgeeks.org/python-tkinter-spinbox/) 是常用的小部件，用于从程序员提供的范围中选择固定数量的值，但默认情况下，Spinbox 接受用户给出的所有类型的输入。因此，我们需要验证输入，只接受范围内的值。
下面是实现:

**注意:**有关 Validatecommand 的更多信息，请参考[Python Tkinter–验证入口小部件](https://www.geeksforgeeks.org/python-tkinter-validating-entry-widget/)

## 蟒蛇 3

```py
from tkinter import *

# Validating function
def validate(user_input):
    # check if the input is numeric
    if  user_input.isdigit():
        # Fetching minimum and maximum value of the spinbox
        minval = int(root.nametowidget(spinbox).config('from')[4])
        maxval = int(root.nametowidget(spinbox).config('to')[4])

        # check if the number is within the range
        if int(user_input) not in range(minval, maxval):
            print ("Out of range")
            return False

        # Printing the user input to the console
        print(user_input)
        return True

    # if input is blank string
    elif user_input is "":
        print(user_input)
        return True

    # return false is input is not numeric
    else:
        print("Not numeric")
        return False

root = Tk()
root.geometry("300x300")
root.title("Spinbox Range Validation")

# Creating Spinbox
spinbox = Spinbox(root, from_ = 1, to = 1000)
spinbox.pack()
range_validation = root.register(validate)

spinbox.config(validate ="key",
         validatecommand =(range_validation, '% P'))

root.mainloop()
```