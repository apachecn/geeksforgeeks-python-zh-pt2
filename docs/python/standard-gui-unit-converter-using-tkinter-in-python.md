# Python 中使用 Tkinter 的标准 GUI 单元转换器

> 原文:[https://www . geesforgeks . org/standard-GUI-unit-converter-using-tkinter-in-python/](https://www.geeksforgeeks.org/standard-gui-unit-converter-using-tkinter-in-python/)

**先决条件:**[tkinter 简介](https://www.geeksforgeeks.org/introduction-to-tkinter/)[网络浏览器简介](https://www.geeksforgeeks.org/python-launch-a-web-browser-using-webbrowser-module/)

在本文中，我们将学习**如何使用 tkinter** 创建标准转换器。现在，我们将创建一个介绍窗口，显示加载栏、欢迎文本和用户的社交媒体配置文件链接，以便当他/她与其他人共享他的代码时，他们可以使用这些资源联系作者。这看起来有点长的代码，但是相信我，伙计们，如果你们开始理解它是如此容易，我把代码分成块，这有助于你们更好地理解。

#### 创建介绍窗口的步骤:

*   首先，“Tkinter”和“webbrowser”模块要导入。
*   创建一个启动介绍窗口的介绍类。
*   创建一个顶层 Tkinter 窗口，以便使用窗口的全部功能。
*   在窗口顶部贴上欢迎标签。
*   创建一个“ttk”。Progressbar”给了我们加载效果。
*   最后，创建四个按钮，并使用“网络浏览器”模块提供您的社交媒体链接。
*   你必须下载/创建四张图片来代表你的社交媒体链接。

下面是 Intro 类的实现:

## 蟒蛇 3

```py
# import required  modules
from tkinter import *
import tkinter as tk
from tkinter.ttk import Progressbar
from time import sleep
import webbrowser

# create intro class .
class intro():
    # constructor
    def __init__(self):

        # Used to open the hidden window.
        wind.deiconify()  

        wind.resizable(0,0)

        # Light blue background.
        wind.configure(bg="#008080")

        # Replace the title with your own name.
        wind.title("GeeksforGeeks Unit Converter")

        # window icon.
        icon=PhotoImage(file=r"convert.png")       
        wind.iconphoto(False,icon)

        # calling center function to center
        # the window to the screen.
        center(wind,500,230)

        # Welcome Label.
        # You can change the welcome text here too.
        entry = Label(wind,bg="#008080",fg="white",
                      text="Welcome to GeeksforGeeks Unit Converter!",
                      font=("Footlight MT Light",15,"bold"))

        entry.place(x=50,y=30,width=410,height=30)

        # Loading Bar Initialisation.
        self.load = Progressbar(wind,orient=HORIZONTAL,
                                length=250,
                                mode='indeterminate')

        # Start Button that opens
        # converter window.
        self.start=Button(wind,bg="#f5f5f5",fg="black",
                          text="START",command=self.loading)

        self.start.place(x=200,y=90,
                         width=80,height=30)           

        # Follow Me Label.
        follow = Label(wind,bg="#008080",fg="white",
                       text="Follow Me On",
                       font=("Helvetica",12,"bold"))

        follow.place(x=186,y=150,width=104,
                     height=20)

        # Author Social Media links and replace
        # the below 'xxxx' with your profile links.
        self.git=PhotoImage(file=r'gforg.png')
        github=Button(wind,image=self.git,bg="white",
                      relief=FLAT,
                      command=lambda:self.links("xxxx"),
                      cursor="hand2")

        github.place(x=110,y=190,width=30,
                     height=30)

        # Instagram Button.
        self.instag=PhotoImage(file=r'ins.png')

        insta=Button(wind,image=self.instag,
                     bg="#008080",relief=FLAT,
                     command=lambda:self.links("xxxx"),
                     cursor="hand2")

        insta.place(x=190,y=190,width=30,
                    height=30)

        # Facebook Button.
        self.fcb=PhotoImage(file=r'fb.png')

        fb=Button(wind,image=self.fcb,bg="white",
                  relief=FLAT,
                  command=lambda:self.links("xxxxx"),
                  cursor="hand2")

        fb.place(x=270,y=190,width=30,
                 height=30)

        # Twitter Button.
        self.tweet=PhotoImage(file=r'twitter.png')

        twitter=Button(wind,image=self.tweet,
                       bg="white",relief=FLAT,
                       command=lambda:self.links("xxxx"),
                       cursor="hand2")
        twitter.place(x=350,y=190,
                      width=30,height=30)

    # Opening author links in browser.
    def links(self,url):   
        webbrowser.get("C:/Program Files" +
                       " (x86)/Google/Chrome/Application/chrome.exe" +
                       " %s --incognito").open(url)

    # Loading ProgressBar.
    def loading(self):
        # Removing start button.
        self.start.place(x=0,y=0,width=0,
                         height=0) 
        self.load.place(x=120,y=100)
        # To remove self.start button when loading self.starts
        wind.update()       

        c=0

        while(c100):
            # Calling Shift function
            # to initialise converter window.
            shift("Length")
```

**创建转换器窗口的步骤:**

*   为转换器窗口创建一个单独的类。
*   我们将用合适的颜色组合将窗户水平分成两半。
*   现在我们需要创建两个 Tkinter 输入框、两个 Tkinter 标签、两个激活列表框的按钮、一个菜单的汉堡图标。
*   使用**将以上物品放置在各自的位置。放置 Tkit 小部件的**方法。
*   现在我们需要在单独的字典中输入每个单元的公式，以转换成其他单元。
*   在主函数中输入输入值，并在初始化或使用类的 setter 方法时传递它们
*   我们需要创建一个移位函数，用户可以使用它从一个参数移位到另一个参数。

下面是转换器类的实现:

## 蟒蛇 3

```py
# import required  modules
from tkinter import *
import tkinter as tk
from tkinter.ttk import Progressbar
from time import sleep
import webbrowser

# create converter class.
class converter():
    # constructor
    def __init__(self,unit):

        win.deiconify()

        # win.geometry("350x500")
        win.resizable(0,0)
        win.title("Converter")
        icon=PhotoImage(file=r'convert.png')
        win.iconphoto(False,icon)

        # Calling Center function to
        # center the window.
        center(win,350,500)

        # Assigning Current Unit,
        # to the converter,
        # selected by user.
        self.unit=unit

        # Input Part of the window(Top Half).
        upr=Label(win,bg="#add8e6",
                  width=400,height=250)
        upr.place(x=0,y=0)

        # Output Part of the
        # window(Bottom Half).
        lwr=Label(win,bg="#189AB4",
                  width=400,height=250
                  ,bd=0)
        lwr.place(x=0,y=250)

        # Hamburger Menu which contains
        # the available conversion options.
        self.menu_lb=Listbox(win,selectmode=SINGLE,
                             height=0,font=("Helvetica",10))
        # Binding event to select
        # the option from ListBox.
        self.menu_lb.bind('<>',self.option) 

        #Loading hamburger menu with options.
        options=["","","Length","Temperature",
                 "Speed","Time","Mass"]

        for i in range(len(options)):
            self.menu_lb.insert(i,options[i])

        # Hamburger menu icon
        self.pic=PhotoImage(file=r"menu.png")
        self.menu=Button(win,image=self.pic,width=35,
                         height=30,bg="#add8e6",bd=0,
                         command=lambda:self.select('m'))
        self.menu.place(x=0,y=0)

        # Input Entry to take the user input.
        self.inp_stg=StringVar()
        self.inp=Entry(win,bg="#add8e6",fg="white",
                       font=("Helvetica",14),
                       text=self.inp_stg,bd=1)
        self.inp.place(x=120,y=100,width=116,
                       height=40)
        self.inp.bind('',self.operation)
        self.inp.bind('',self.operation)

        # Loading the sub-menu box.
        self.lb_menu=unit["lb"]

        # Input Listbox(i.e., Meter etc)
        self.lb=Listbox(win,selectmode=SINGLE,
                        height=0)           
        self.lb.bind('<>',self.option)

        # Input Unit Display Label selected by customer.
        self.disp=Label(win,text=self.lb_menu[0],
                        bg="white",fg="black")
        self.disp.place(x=120,y=160,width=100,
                        height=20)

        # DownArrow Button to Activate Listbox sub-menu to selection conversion units.
        self.down=PhotoImage(file=r"down.png")
        scroll_upr=Button(win,image=self.down,
                          width=14,height=18,bd=0,
                          command=lambda:self.select(0))
        scroll_upr.place(x=220,y=160)

        # Output Entry to display the output.
        self.opt_stg=StringVar()   

        self.opt=Entry(win,bg="#189AB4",fg="black",
                       font=("Helvetica",14),
                       text=self.opt_stg,bd=1)

        self.opt.place(x=120,y=350,width=116,
                       height=40)
        self.opt.bind('',self.operation)

        self.lb1=Listbox(win,selectmode=SINGLE,
                         height=0)
        self.lb1.bind('<>',self.option)

        for i in range(len(self.lb_menu)):
            self.lb1.insert(i,self.lb_menu[i])
            self.lb.insert(i,self.lb_menu[i])       

        # Output unit display.
        self.disp1=Label(win,text=self.lb_menu[1],
                         bg="#ffffff",fg="black")
        self.disp1.place(x=120,y=410,width=100,
                         height=20)

        # Button to open sub-menu list.
        scroll_dwn=Button(win,image=self.down,
                          width=14,height=18,bd=0,
                          command=lambda:self.select(1),
                          bg="#f5f5f5")

        scroll_dwn.place(x=220,y=410)

        # To display the formulae used
        # to convert the current units.
        # StringVar() to update the input
        # and output entry fields after
        # every keystroke.
        self.form=StringVar()  
        self.formulae=Label(win,text="",bg="#189AB4",
                            fg="white",
                            font=("Helvetica",10))
        self.formulae.place(x=50,y=450,width=250,
                            height=25)

        # Current position of I/P and O/P
        # sub-menu is stored in a dictionary
        # and accessed through the dictionary.
        self.para=unit["para"] 
        self.para1=unit["para1"]

        #print(self.para,self.para1)

    # After shifting from parameter to
    # other paramter(i.e., From lenght
    # to Mass) we need reset and assign
    # the converter class with
    #respective inputs and outputs.    
    def set_unit(self,unit):
        global exp_in,exp_out

        # Input Expression.
        exp_in=""  

        # Output Expression.
        exp_out=""

        # Input StringVar()
        self.inp_stg.set("")

        # Output StringVar()
        self.opt_stg.set("") 

        # Current Parameter(i.e.,Length,Mass etc.)
        self.unit=unit

        # Accessing the position of unit display
        # label position through dictionary
        self.lb_menu=unit["lb"]

        # Deleting Input Listbox to assign
        # the current parameter values.
        self.lb.delete(0,END)  

        # Deleting Output Listbox
        # to assign the current
        # parameter values
        self.lb1.delete(0,END) 

        self.lb.place(y=0,height=0)
        self.lb1.place(y=250,height=0)

        # Initialising the unit display
        # label with initial unit
        # (i.e.,Tonne,Kilogram)
        self.disp['text']=self.lb_menu[0]
        self.disp1['text']=self.lb_menu[1]

        # Changing the length and
        # position of Listbox(Sub-Menu)
        # according to the length
        # of the list
        self.para=unit["para"]
        self.para1=unit["para1"]

        # Appending Options of the
        # list to Listbox.
        for i in range(len(self.lb_menu)):
            self.lb1.insert(END,self.lb_menu[i])
            self.lb.insert(i,self.lb_menu[i])

        # Clearing the formulae Label
        # after changing to another
        # parameter.
        self.formulae['text'] = "Formulae: "
                    + operator.replace("{}",
                           "Unit")

        # Centering the window.
        center(wind,500,230)
        win.update()

    # Performs Operation by taking
    # user input(Value and unit
    # to be converted).
    def operation(self,event):     

        global exp_in,operator,exp_out

        # Taking Input and Output
        # Units to convert from display.
        self.inp_unit = self.disp['text']
        self.opt_unit = self.disp1['text']

        try:
          # We can access the widget
          # by the checking the place /
          # position of event occurence.
            widget = event.widget

            if(widget == self.inp):
                win.update()

                # Retrieving the operator stored
                # in dictionary using unit
                # display label.
                index = self.unit[self.opt_unit][-1]
                operator = self.unit[self.inp_unit][index]
                # print("exp: ",operator,exp_in)

                # As this is a unit converter
                # we don't need characters so
                # we are checking for numbers itself.
                if(event.char >= '0' and event.char <= '9'):
                    exp_in = self.inp_stg.get()

                    #Taking the value after every
                    # keystroke and updating
                    # the output
                    exp_out = str(eval(operator.format(exp_in)))
                    self.opt_stg.set(exp_out)

                elif((event.char=='\b') or
                     (len(self.inp_stg.get())=='0'
                      and event.char<='9')):
                    exp_out = self.opt_stg.get()
                    exp_in = str(eval(operator.format(exp_out)))
                    self.inp_stg.set(exp_in)

                elif(event.char == '\b' or
                     (len(self.opt_stg.get())
```

现在创建一个主函数，并创建一组字典来输入单位公式值，并调用“intro()”类来启动转换器。在这里你可以看到你的联系链接，加载栏等。如果你想让你的窗口在屏幕中央被触发，你还需要创建一个“中心”功能。

下面是完整的代码实现:

## 蟒蛇 3

```py
# import required  modules
from tkinter import *
import tkinter as tk
from tkinter.ttk import Progressbar
from time import sleep
import webbrowser

# create intro class .
class intro():
    # constructor
    def __init__(self):

        # Used to open the hidden window.
        wind.deiconify()  

        wind.resizable(0,0)

        # Light blue background.
        wind.configure(bg="#008080")

        # Replace the title with your own name.
        wind.title("GeeksforGeeks Unit Converter")

        # window icon.
        icon=PhotoImage(file=r"convert.png")       
        wind.iconphoto(False,icon)

        # calling center function to center
        # the window to the screen.
        center(wind,500,230)

        # Welcome Label.
        # You can change the welcome text here too.
        entry = Label(wind,bg="#008080",fg="white",
                      text="Welcome to GeeksforGeeks Unit Converter!",
                      font=("Footlight MT Light",15,"bold"))

        entry.place(x=50,y=30,width=410,height=30)

        # Loading Bar Initialisation.
        self.load = Progressbar(wind,orient=HORIZONTAL,
                                length=250,
                                mode='indeterminate')

        # Start Button that opens
        # converter window.
        self.start=Button(wind,bg="#f5f5f5",fg="black",
                          text="START",command=self.loading)

        self.start.place(x=200,y=90,
                         width=80,height=30)           

        # Follow Me Label.
        follow = Label(wind,bg="#008080",fg="white",
                       text="Follow Me On",
                       font=("Helvetica",12,"bold"))

        follow.place(x=186,y=150,width=104,
                     height=20)

        # Author Social Media links and replace
        # the below 'xxxx' with your profile links.
        self.git=PhotoImage(file=r'gforg.png')
        github=Button(wind,image=self.git,bg="white",
                      relief=FLAT,
                      command=lambda:self.links("xxxx"),
                      cursor="hand2")

        github.place(x=110,y=190,width=30,
                     height=30)

        # Instagram Button.
        self.instag=PhotoImage(file=r'ins.png')

        insta=Button(wind,image=self.instag,
                     bg="#008080",relief=FLAT,
                     command=lambda:self.links("xxxx"),
                     cursor="hand2")

        insta.place(x=190,y=190,width=30,
                    height=30)

        # Facebook Button.
        self.fcb=PhotoImage(file=r'fb.png')

        fb=Button(wind,image=self.fcb,bg="white",
                  relief=FLAT,
                  command=lambda:self.links("xxxxx"),
                  cursor="hand2")

        fb.place(x=270,y=190,width=30,
                 height=30)

        # Twitter Button.
        self.tweet=PhotoImage(file=r'twitter.png')

        twitter=Button(wind,image=self.tweet,
                       bg="white",relief=FLAT,
                       command=lambda:self.links("xxxx"),
                       cursor="hand2")
        twitter.place(x=350,y=190,
                      width=30,height=30)

    # Opening author links in browser.
    def links(self,url):   
        webbrowser.get("C:/Program Files" +
                       " (x86)/Google/Chrome/Application/chrome.exe" +
                       " %s --incognito").open(url)

    # Loading ProgressBar.
    def loading(self):
        # Removing start button.
        self.start.place(x=0,y=0,width=0,
                         height=0) 
        self.load.place(x=120,y=100)
        # To remove self.start button when loading self.starts
        wind.update()       

        c=0

        while(c100):
            # Calling Shift function
            # to initialise converter window.
            shift("Length")

# create converter class.
class converter():
    # constructor
    def __init__(self,unit):

        win.deiconify()

        # win.geometry("350x500")
        win.resizable(0,0)
        win.title("Converter")
        icon=PhotoImage(file=r'convert.png')
        win.iconphoto(False,icon)

        # Calling Center function to
        # center the window.
        center(win,350,500)

        # Assigning Current Unit,
        # to the converter,
        # selected by user.
        self.unit=unit

        # Input Part of the window(Top Half).
        upr=Label(win,bg="#add8e6",
                  width=400,height=250)
        upr.place(x=0,y=0)

        # Output Part of the
        # window(Bottom Half).
        lwr=Label(win,bg="#189AB4",
                  width=400,height=250
                  ,bd=0)
        lwr.place(x=0,y=250)

        # Hamburger Menu which contains
        # the available conversion options.
        self.menu_lb=Listbox(win,selectmode=SINGLE,
                             height=0,font=("Helvetica",10))
        # Binding event to select
        # the option from ListBox.
        self.menu_lb.bind('<>',self.option) 

        #Loading hamburger menu with options.
        options=["","","Length","Temperature",
                 "Speed","Time","Mass"]

        for i in range(len(options)):
            self.menu_lb.insert(i,options[i])

        # Hamburger menu icon
        self.pic=PhotoImage(file=r"menu.png")
        self.menu=Button(win,image=self.pic,width=35,
                         height=30,bg="#add8e6",bd=0,
                         command=lambda:self.select('m'))
        self.menu.place(x=0,y=0)

        # Input Entry to take the user input.
        self.inp_stg=StringVar()
        self.inp=Entry(win,bg="#add8e6",fg="white",
                       font=("Helvetica",14),
                       text=self.inp_stg,bd=1)
        self.inp.place(x=120,y=100,width=116,
                       height=40)
        self.inp.bind('',self.operation)
        self.inp.bind('',self.operation)

        # Loading the sub-menu box.
        self.lb_menu=unit["lb"]

        # Input Listbox(i.e., Meter etc)
        self.lb=Listbox(win,selectmode=SINGLE,
                        height=0)           
        self.lb.bind('<>',self.option)

        # Input Unit Display Label selected by customer.
        self.disp=Label(win,text=self.lb_menu[0],
                        bg="white",fg="black")
        self.disp.place(x=120,y=160,width=100,
                        height=20)

        # DownArrow Button to Activate Listbox sub-menu to selection conversion units.
        self.down=PhotoImage(file=r"down.png")
        scroll_upr=Button(win,image=self.down,
                          width=14,height=18,bd=0,
                          command=lambda:self.select(0))
        scroll_upr.place(x=220,y=160)

        # Output Entry to display the output.
        self.opt_stg=StringVar()   

        self.opt=Entry(win,bg="#189AB4",fg="black",
                       font=("Helvetica",14),
                       text=self.opt_stg,bd=1)

        self.opt.place(x=120,y=350,width=116,
                       height=40)
        self.opt.bind('',self.operation)

        self.lb1=Listbox(win,selectmode=SINGLE,
                         height=0)
        self.lb1.bind('<>',self.option)

        for i in range(len(self.lb_menu)):
            self.lb1.insert(i,self.lb_menu[i])
            self.lb.insert(i,self.lb_menu[i])       

        # Output unit display.
        self.disp1=Label(win,text=self.lb_menu[1],
                         bg="#ffffff",fg="black")
        self.disp1.place(x=120,y=410,width=100,
                         height=20)

        # Button to open sub-menu list.
        scroll_dwn=Button(win,image=self.down,
                          width=14,height=18,bd=0,
                          command=lambda:self.select(1),
                          bg="#f5f5f5")

        scroll_dwn.place(x=220,y=410)

        # To display the formulae used
        # to convert the current units.
        # StringVar() to update the input
        # and output entry fields after
        # every keystroke.
        self.form=StringVar()  
        self.formulae=Label(win,text="",bg="#189AB4",
                            fg="white",
                            font=("Helvetica",10))
        self.formulae.place(x=50,y=450,width=250,
                            height=25)

        # Current position of I/P and O/P
        # sub-menu is stored in a dictionary
        # and accessed through the dictionary.
        self.para=unit["para"] 
        self.para1=unit["para1"]

        #print(self.para,self.para1)

    # After shifting from parameter to
    # other paramter(i.e., From lenght
    # to Mass) we need reset and assign
    # the converter class with
    #respective inputs and outputs.    
    def set_unit(self,unit):
        global exp_in,exp_out

        # Input Expression.
        exp_in=""  

        # Output Expression.
        exp_out=""

        # Input StringVar()
        self.inp_stg.set("")

        # Output StringVar()
        self.opt_stg.set("") 

        # Current Parameter(i.e.,Length,Mass etc.)
        self.unit=unit

        # Accessing the position of unit display
        # label position through dictionary
        self.lb_menu=unit["lb"]

        # Deleting Input Listbox to assign
        # the current parameter values.
        self.lb.delete(0,END)  

        # Deleting Output Listbox
        # to assign the current
        # parameter values
        self.lb1.delete(0,END) 

        self.lb.place(y=0,height=0)
        self.lb1.place(y=250,height=0)

        # Initialising the unit display
        # label with initial unit
        # (i.e.,Tonne,Kilogram)
        self.disp['text']=self.lb_menu[0]
        self.disp1['text']=self.lb_menu[1]

        # Changing the length and
        # position of Listbox(Sub-Menu)
        # according to the length
        # of the list
        self.para=unit["para"]
        self.para1=unit["para1"]

        # Appending Options of the
        # list to Listbox.
        for i in range(len(self.lb_menu)):
            self.lb1.insert(END,self.lb_menu[i])
            self.lb.insert(i,self.lb_menu[i])

        # Clearing the formulae Label
        # after changing to another
        # parameter.
        self.formulae['text'] = "Formulae: "
                    + operator.replace("{}",
                           "Unit")

        # Centering the window.
        center(wind,500,230)
        win.update()

    # Performs Operation by taking
    # user input(Value and unit
    # to be converted).
    def operation(self,event):     

        global exp_in,operator,exp_out

        # Taking Input and Output
        # Units to convert from display.
        self.inp_unit = self.disp['text']
        self.opt_unit = self.disp1['text']

        try:
          # We can access the widget
          # by the checking the place /
          # position of event occurence.
            widget = event.widget

            if(widget == self.inp):
                win.update()

                # Retrieving the operator stored
                # in dictionary using unit
                # display label.
                index = self.unit[self.opt_unit][-1]
                operator = self.unit[self.inp_unit][index]
                # print("exp: ",operator,exp_in)

                # As this is a unit converter
                # we don't need characters so
                # we are checking for numbers itself.
                if(event.char >= '0' and event.char <= '9'):
                    exp_in = self.inp_stg.get()

                    #Taking the value after every
                    # keystroke and updating
                    # the output
                    exp_out = str(eval(operator.format(exp_in)))
                    self.opt_stg.set(exp_out)

                elif((event.char=='\b') or
                     (len(self.inp_stg.get())=='0'
                      and event.char<='9')):
                    exp_out = self.opt_stg.get()
                    exp_in = str(eval(operator.format(exp_out)))
                    self.inp_stg.set(exp_in)

                elif(event.char == '\b' or
                     (len(self.opt_stg.get())
```

**输出:**

<video class="wp-video-shortcode" id="video-445622-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200705142403/2020-07-05-14-19-06.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200705142403/2020-07-05-14-19-06.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200705142403/2020-07-05-14-19-06.mp4)</video>

**要点:**

*   您需要安装“ **tkinter** ”和“**网络浏览器**”库。
*   创建一个介绍窗口是你的选择(这不是强制性的)。但是我建议你也创建一个。
*   你需要创建顶层窗口，因为我们不能破坏主窗口，因为它可能会破坏我们所有的项目。
*   您不需要安装各种集成开发环境，它在 python IDLE 上运行得非常好。