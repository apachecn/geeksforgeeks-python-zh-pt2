# 用 Python 后台写文件

> 原文:[https://www . geesforgeks . org/writing-files-background-python/](https://www.geeksforgeeks.org/writing-files-background-python/)

Python 中如何在后台写文件？

想法是在 Python 中使用[多线程](https://www.geeksforgeeks.org/multi-threading-model/)。它允许我们在后台写文件，同时进行另一项操作。在本文中，我们将制作一个名为“Asyncwrite.py”的文件来演示它。这个程序增加了两个数字，同时还会在后台写一个文件。**请在你自己的系统上运行这个程序，这样你就可以看到制作的文件**

## 蟒蛇 3

```py
# Python3 program to write file in
# background

# Importing the threading and time
# modules
import threading
import time

# Inheriting the base class 'Thread'
class AsyncWrite(threading.Thread):

    def __init__(self, text, out):

        # calling superclass init
        threading.Thread.__init__(self)
        self.text = text
        self.out = out

    def run(self):

        f = open(self.out, "a")
        f.write(self.text + '\n')
        f.close()

        # waiting for 2 seconds after writing
        # the file
        time.sleep(2)
        print("Finished background file write to",
                                         self.out)

def Main():

    message = "Geeksforgeeks"
    background = AsyncWrite(message, 'out.txt')
    background.start()

    print("The program can continue while it writes")
    print("in another thread")
    print("100 + 400 = ", 100 + 400)

    # wait till the background thread is done
    background.join()
    print("Waited until thread was complete")

if __name__=='__main__':
    Main()
```

**输出:**

```py
Enter a string to store: HelloWorld
The program can continue while it writes in another thread
100 + 400 = 500
Finished background file write to out.txt
Waited until  thread was complete
```

该程序将要求输入一个字符串，并将计算两个数字的总和，在后台，它将“输入的字符串”写入名为“out.txt”的输出文件。检查您的“Asyncwrite.py”文件所在的目录，您还会发现一个名为“out.txt”的文件，其中存储了您的字符串。

**目的:**
在后台写文件的一般目的是，你可以在后台将你的数据添加到一个文件中，同时让程序在程序内做另一个任务。例如，您可以在为同一个用户执行另一个任务时，将接收到的用户输入写入文件。

**参考:**

*   [蟒蛇 3 基础知识](https://write.geeksforgeeks.org/python3-basics-and-important-topics-for-beginners/)
*   [Python3 中级话题](https://www.geeksforgeeks.org/python3-intermediate-level-topics/)