# Pytube | Python 库下载 youtube 视频

> 原文:[https://www . geesforgeks . org/pytube-python-library-download-YouTube-videos/](https://www.geeksforgeeks.org/pytube-python-library-download-youtube-videos/)

YouTube 是非常受欢迎的视频分享网站。从 YouTube 下载视频是一项艰巨的工作。下载下载器并使用它获取视频，或者去任何其他网站获取视频并保存在您的计算机上。使用 Python，这个任务非常容易。几行代码就能为你从 YouTube 上下载视频。为此，有一个名为“pytube”的 python 库。pytube 是一个轻量级、无依赖性的 Python 库，用于从 web 下载视频。
pytube 不是原生库。使用前需要安装。安装很容易，当你有 pip。在终端或命令提示符下，键入以下命令安装 pytube。

```
pip install pytube

```

如果您没有 pip，请将其安装为外部库。

**下载单个视频**

pytube 库使视频下载变得非常容易。通过将链接作为参数传递来创建 YouTube 模块的对象。然后，获得适当的视频扩展和分辨率。您可以将文件名设置为您方便的名称，在另一种情况下，原始名称将被保留。然后，使用下载功能下载文件，该功能有一个参数，即下载文件的位置。

## 蟒蛇 3

```
# importing the module 
from pytube import YouTube 

# where to save 
SAVE_PATH = "E:/" #to_do 

# link of the video to be downloaded 
link="https://www.youtube.com/watch?v=xWOoBJUqlbI"

try: 
    # object creation using YouTube
    # which was imported in the beginning 
    yt = YouTube(link) 
except: 
    print("Connection Error") #to handle exception 

# filters out all the files with "mp4" extension 
mp4files = yt.filter('mp4') 

#to set the name of the file
yt.set_filename('GeeksforGeeks Video')  

# get the video with the extension and
# resolution passed in the get() function 
d_video = yt.get(mp4files[-1].extension,mp4files[-1].resolution) 
try: 
    # downloading the video 
    d_video.download(SAVE_PATH) 
except: 
    print("Some Error!") 
print('Task Completed!') 
```

下载一个文件需要一些时间，因为从网络上下载了大量的数据。根据连接速度的不同，执行程序所需的时间也不同。如果您希望下载文件数量，请继续下一个案例。

**下载多个视频**

下载多个视频的基本任务与下载单个视频相同。我们可以使用 for 循环来下载视频。

## 蟒蛇 3

```
from pytube import YouTube 

#where to save 
SAVE_PATH = "E:/" #to_do 

#link of the video to be downloaded 
link=["https://www.youtube.com/watch?v=xWOoBJUqlbI", 
    "https://www.youtube.com/watch?v=xWOoBJUqlbI"
    ]

for i in link: 
    try: 

        # object creation using YouTube
        # which was imported in the beginning 
        yt = YouTube(i) 
    except: 

        #to handle exception 
        print("Connection Error") 

    #filters out all the files with "mp4" extension 
    mp4files = yt.filter('mp4') 

    # get the video with the extension and
    # resolution passed in the get() function 
    d_video = yt.get(mp4files[-1].extension,mp4files[-1].resolution) 
    try: 
        # downloading the video 
        d_video.download(SAVE_PATH) 
    except: 
        print("Some Error!") 
print('Task Completed!') 
```

在本文中，我们使用了一个 for 循环来下载多个文件，如图所示。可以使用文件处理来保存需要下载的文件中的所有链接。

**使用文件处理**下载多个视频

使用文件处理，我们可以打开包含链接组的文件。遍历文本文件的每一个链接，应用最基本的视频下载程序就是在这里完成的。这里，我们有一个名为“links_file.txt”的文本文件，其中包含了所有需要下载的链接。

## 蟒蛇 3

```
from pytube import YouTube 

# where to save 
SAVE_PATH = "E:/" #to_do 

# link of the video to be downloaded 
# opening the file 
link=open('links_file.txt','r') 

for i in link: 
    try: 

        # object creation using YouTube
        # which was imported in the beginning 
        yt = YouTube(i) 
    except: 

        #to handle exception
        print("Connection Error")  

    #filters out all the files with "mp4" extension 
    mp4files = yt.filter('mp4') 

    # get the video with the extension and
    # resolution passed in the get() function 
    d_video = yt.get(mp4files[-1].extension,mp4files[-1].resolution) 
    try: 

        # downloading the video 
        d_video.download(SAVE_PATH) 
    except: 
        print("Some Error!") 
print('Task Completed!') 
```

**要点:**

1.  请确保您已连接到互联网以下载视频。否则会引发错误。
2.  不要在任何循环中使用 set_filename()函数。在这种情况下，将只下载一个视频。
3.  您可以每次使用另一个名称数组来修改名称。
4.  两者之间的连接中断也会引发错误，在这种情况下，将不会下载视频。

本文由 [**里沙布·班萨尔**](https://www.linkedin.com/in/rishabh-bansal-9b4b71108/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。