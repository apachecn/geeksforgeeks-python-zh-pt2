# Python VLC MediaPlayer–设置播放速率

> 原文:[https://www . geesforgeks . org/python-VLC-media player-setting-play-rate/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-setting-play-rate/)

在本文中，我们将看到如何在 python vlc 模块中设置 MediaPlayer 对象的媒体播放速率。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。媒体播放速率基本上就是视频的速度，越多速率越快的视频得到播放，默认值为 1.0，为了减慢视频速度设置速率值小于 1。

> 为此，我们将对 MediaPlayer 对象使用`set_rate`方法
> 
> **语法:** media_player.set_rate(n)
> 
> **自变量:**以浮点值为自变量
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
media = vlc.Media("death_note.mkv")

# setting media to the media player
media_player.set_media(media)

# setting play rate
# doubles the speed of the video
media_player.set_rate(2)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)
该媒体以 2x 的速度播放

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

# setting play rate
# halves the speed of the video
media_player.set_rate(0.5)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)
本视频减速 50%