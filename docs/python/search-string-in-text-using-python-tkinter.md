# 使用 Python-Tkinter 在文本中搜索字符串

> 原文:[https://www . geesforgeks . org/search-string-in-text-use-python-tkinter/](https://www.geeksforgeeks.org/search-string-in-text-using-python-tkinter/)

**Tkinter** 是 Python 的标准 GUI 库。它为 Tk GUI 工具包提供了一个强大的面向对象的界面。在本文中，我们将看到如何使用 Tkinter 在给定的文本窗口中搜索特定的字符串。
**注:**关于 **Tkinter** 的更多详细信息，请参考[Python GUI–Ttkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)
**方法创建用户自定义函数来搜索(def find)**
一个内部循环将在文本小部件中搜索每个单词的所有实例，并标记它们以突出显示。循环的终止条件是在小部件中找不到当前单词。然后，毕竟单词已经被标记，设置它们的颜色。

*   声明一个变量 s，并在文本中获取要搜索的用户的字符串输入(在这种情况下，字符串在‘编辑’文本框窗口中键入)

*   将索引值初始化为 1。

*   初始化内部循环。

*   使用。search()在给定文本中搜索所需的字符串(在本例中为 s ),并更新当前索引值，直到文本结束。

*   最后一个索引值是当前索引和字符串长度的总和。

*   每当在索引 1 和最后一个索引之间找到所需的字符串时，就将“find”标记添加到这两个索引中。

*   改变焦点找到按钮

*   一旦按下查找按钮。带有“find”标签的字符串，该字符串以红色突出显示。

*   使用。主循环()终止，因为任何用户都将终止程序

**例 1:**

## 蟒蛇 3

```
#Python Program to search string in text using Tkinter

from tkinter import *

#to create a window
root = Tk()

#root window is the parent window
fram = Frame(root)

#adding label to search box
Label(fram,text='Text to find:').pack(side=LEFT)

#adding of single line text box
edit = Entry(fram)

#positioning of text box
edit.pack(side=LEFT, fill=BOTH, expand=1)

#setting focus
edit.focus_set()

#adding of search button
butt = Button(fram, text='Find') 
butt.pack(side=RIGHT)
fram.pack(side=TOP)

#text box in root window
text = Text(root)

#text input area at index 1 in text window
text.insert('1.0','''Type your text here''')
text.pack(side=BOTTOM)

#function to search string in text
def find():

    #remove tag 'found' from index 1 to END
    text.tag_remove('found', '1.0', END)

    #returns to widget currently in focus
    s = edit.get()
    if s:
        idx = '1.0'
        while 1:
            #searches for desired string from index 1
            idx = text.search(s, idx, nocase=1,
                              stopindex=END)
            if not idx: break

            #last index sum of current index and
            #length of text
            lastidx = '%s+%dc' % (idx, len(s))

            #overwrite 'Found' at idx
            text.tag_add('found', idx, lastidx)
            idx = lastidx

        #mark located string as red
        text.tag_config('found', foreground='red')
    edit.focus_set()
butt.config(command=find)

#mainloop function calls the endless loop of the window,
#so the window will wait for any
#user interaction till we close it
root.mainloop()
```

**输出:**

<figure class="image"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200327124102/tkinter2.png" alt="Search String in Text using Python-Tkinter
“></figure>

较大的文本框用于文本输入，较小的文本框用于需要在给定文本中找到的字符串输入，一旦找到，就用红色标记。
**例 2:**

## 蟒蛇 3

```
#Python Program to search string in text using Tkinter

from tkinter import *

root = Tk()
fram = Frame(root)
Label(fram,text='Text to find:').pack(side=LEFT)
edit = Entry(fram)
edit.pack(side=LEFT, fill=BOTH, expand=1)
edit.focus_set()
butt = Button(fram, text='Find') 
butt.pack(side=RIGHT)
fram.pack(side=TOP)

text = Text(root)
text.insert('1.0','''Type your text here''')
text.pack(side=BOTTOM)

def find():

    text.tag_remove('found', '1.0', END)
    s = edit.get()
    if s:
        idx = '1.0'
        while 1:
            idx = text.search(s, idx, nocase=1,
                              stopindex=END)
            if not idx: break
            lastidx = '%s+%dc' % (idx, len(s))
            text.tag_add('found', idx, lastidx)
            idx = lastidx
       text.tag_config('found', foreground='red')
    edit.focus_set()
butt.config(command=find)
root.mainloop()
```

**输出:**

<figure class="image"><img src="https://media.geeksforgeeks.org/wp-content/uploads/20200327124532/tkinter21.png" alt="Search String in Text using Python-Tkinter
“></figure>