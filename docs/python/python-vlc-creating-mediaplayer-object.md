# Python VLC–创建媒体播放器对象

> 原文:[https://www . geesforgeks . org/python-VLC-creating-media player-object/](https://www.geeksforgeeks.org/python-vlc-creating-mediaplayer-object/)

在本文中，我们将看到如何在 python vlc 模块中创建一个 MediaPlayer 对象。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。MediaPlayer 类是基本类，它用于一次播放单个视频。

> 为了做到这一点，我们将使用`MediaPlayer`方法
> 
> **语法:**媒体播放器(video_uri)
> 
> **参数:**它以视频 uri 作为可选参数
> 
> **返回:**返回 MediaPlayer 对象

下面是实现

```py
# importing vlc module
import vlc
import time
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# printing type of media player variable
print(type(media_player))
```

**输出:**

```py
class 'vlc.MediaPlayer'

```

另一个例子

```py
# importing vlc module
import vlc
import time

# creating vlc media player object
media_player = vlc.MediaPlayer("1.mp4")

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)