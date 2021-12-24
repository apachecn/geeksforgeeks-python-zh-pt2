# Python VLC MediaPlayer–获取当前状态

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-current-state/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-current-state/)

在本文中，我们将看到如何在 python vlc 模块中获取 MediaPlayer 对象的当前状态。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。当前状态可以是播放暂停或没有什么特别的如果没有视频播放，这取决于媒体播放器对象。

> 为此，我们将对 MediaPlayer 对象使用`get_state`方法
> 
> **语法:** media_player.get_state()
> 
> **论证:**不需要论证
> 
> **返回:**返回状态对象

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

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting current state of the player
value = media_player.get_state()

# printing value
print("Current State : ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```py
Current State : 
State.Playing

```

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

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting current state of the player
value = media_player.get_state()

# printing value
print("Current State : ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```py
Current State : 
State.Playing

```