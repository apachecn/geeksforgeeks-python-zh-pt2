# Python 脚本打开剪贴板上的谷歌地图位置

> 原文:[https://www . geesforgeks . org/python-script-open-Google-map-location-clipboard/](https://www.geeksforgeeks.org/python-script-open-google-map-location-clipboard/)

任务是创建一个 python 脚本，该脚本将打开默认的 web 浏览器，指向作为命令行参数给出的地址的谷歌地图。

**以下为分步流程:**

1.  **通过命令行输入创建 Address _ string:**命令行参数可以通过 sys 模块读取。sys.argv 数组的第一个元素作为文件名，其余元素作为命令行参数，这些参数被空格分割成不同的元素，与 raw_input()相同。拆分()。因此，如果 sys.argv 的长度大于 1，那么我们可以确定命令行参数已经被传递。
    由于 sys.argv 是一个字符串列表，因此可以将其传递给 join()方法，该方法返回一个字符串值。因为第一个元素是文件名，这是不需要的，我们可以从第二个元素开始切割列表并加入。

```py
#File name is Map.py
import sys
print ' '.join(sys.argv[1:])
```

```py
If we run >>> python Map.py New Delhi
The output of the program would be New Delhi.
```

*   **打开网络浏览器:**我们将使用**网络浏览器**模块打开浏览器。网页浏览器模块有一个 **open()** 的方法，可以将网页浏览器启动到指定的网址。例如，下面给出的脚本将打开网络浏览器，进入 GeeksforGeeks 的主页。

    ```py
    import webbrowser
    webbrowser.open('https://www.geeksforgeeks.org/')
    ```

    *   **Find the URL :** Now, when we go to Google Maps and search for google maps, the URL turns out to be gibberish and of no clear pattern, as shown below.
    [https://www.google.co.in/maps/place/GeeksforGeeks/@28.5011226,77.4077907,17z/data=!3m1!4b1!4m5!3m4!1s0x390ce626851f7009:0x621185133cfd1ad1!8m2!3d28.5011226!4d77.4099794?hl=en](https://www.google.co.in/maps/place/GeeksforGeeks/@28.5011226,77.4077907,17z/data=!3m1!4b1!4m5!3m4!1s0x390ce626851f7009:0x621185133cfd1ad1!8m2!3d28.5011226!4d77.4099794?hl=en)

    网站通常会在网址中添加额外的文本，用于定制和跟踪等附加任务。然而，可以观察到，网址的最初几个部分是**https://www.google.co.in/maps/place/GeeksforGeeks**，其中极客博客是我们搜索的关键词。
    同样，比如说在搜索新德里的时候，如果我们只写新德里，而不是新德里+的话，那么+会自动插入到需要的地方，这让我们的任务变得更加容易。
    因此最终网址可以取为**https://www.google.co.in/maps/place/*地址 _ 字符串* /** 。

    *   **Combining the two and Completing the script :** The python script to open the given command line address is given below. There will be two imported modules, **webbrowser** to open the browser to the designated URL and **sys** to work on the command line arguments.
    *   第一步是检查是否有任何命令行，这是使用 len(sys.argv)完成的。
    *   然后我们使用 join 方法来形成谷歌地图中要搜索的地方的地址字符串。
    *   最后，当我们得到地址时，我们使用 webbrowser 模块的 open()方法将浏览器打开到地址 URL。

    该程序通过 CMD(windows)或终端(Linux)以下列格式运行:

    ```py
    >>> python [File Name] [Address to be searched]
    For eg. >>> python Map.py GeeksforGeeks
    ```

    ```py
    # File Name -- Map.py
    import sys, webbrowser
    if len(sys.argv) > 1:       # Argument passed
        map_string = ' '.join(sys.argv[1:])
        webbrowser.open('https://www.google.com/maps/place/' + map_string)

    else:
        print "Pass the string as command line argument, Try Again"

    ```

    ```py
    >>> python Map.py SeeksforGeeks
    The above command will open map of GeeksforGeeks in the web browser.

    ```

    本文由 **Harshit Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。