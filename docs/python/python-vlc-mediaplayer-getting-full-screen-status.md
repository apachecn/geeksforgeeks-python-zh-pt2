# Python VLC MediaPlayer–获得全屏状态

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-全屏-status/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-full-screen-status/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的全屏状态。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。启用全屏状态使其全屏这类似于切换全屏，但在这种状态下，我们可以撤销全屏。这个状态可以借助`set_fullscreen`方法设置。

> 为此，我们将对 MediaPlayer 对象使用`get_fullscreen`方法
> 
> **语法:** media_player.get_fullscreen()
> 
> **论证:**不需要论证
> 
> **返回:**如果为真则返回 1，否则返回 0

下面是实现

```py
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# setting full screen status
media_player.media_player.set_fullscreen(True)

# media object
media = vlc.Media("death_note.mkv")

# setting media to the media player
media_player.set_media(media)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting full screen status
value = media_player.get_fullscreen()

# printing value
print("Full Screen : ")
print(value)
```

**输出:**
![](img/b9eb6c3bd27106a39edd9d3c440ac2fd.png)

```py
Full Screen : 
1

```

另一个例子

```py
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media object
media = vlc.Media("1mp4.mkv")

# setting media to the media player
media_player.set_media(media)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting full screen status
value = media_player.get_fullscreen()

# printing value
print("Full Screen : ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```py
Full Screen : 
0

```