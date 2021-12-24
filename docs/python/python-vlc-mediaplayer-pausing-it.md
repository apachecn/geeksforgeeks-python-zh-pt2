# Python VLC MediaPlayer–暂停它

> 原文:[https://www . geesforgeks . org/python-VLC-media player-暂停-it/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-pausing-it/)

在本文中，我们将看到如何在 python vlc 模块的 MediaPlayer 对象中暂停媒体。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。我们可以借助`play`方法播放视频。

> 为此，我们将对 MediaPlayer 对象使用`set_pause`方法
> 
> **语法:** media_player.event_manager()
> 
> **自变量:**以整数为自变量，零则播放/恢复，非零则暂停。
> 
> **返回:**返回无

下面是实现

```py
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media object
media = vlc.Media("D:\\pych\\bhuvan\\death_note.mkv")

# setting media to the media player
media_player.set_media(media)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# pausing the video
media_player.set_pause(1)
```

**输出:**
此视频将播放 5 秒钟，然后暂停
![](img/8a97fafb4e82545c3892a5d6b0f3bb5f.png)

下面是另一个例子
的实现

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

# wait so the video can be played for 3 seconds
# irrespective for length of video
time.sleep(3)

# pausing the video
media_player.set_pause(1)
```

**输出:**
同样这个视频会播放 3 秒然后暂停
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)