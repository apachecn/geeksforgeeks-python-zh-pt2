# Python VLC MediaPlayer–获得位置

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-position/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-position/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的位置。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。将媒体位置设置为 0.0 到 1.0 之间的百分比。如果未启用回放，这将不起作用。根据底层的输入格式和协议，这可能不起作用，可以借助`set_position`方法进行设置。

> 为此，我们将对 MediaPlayer 对象使用`get_position`方法
> 
> **语法:** media_player.get_position()
> 
> **论证:**它以否为论证
> 
> **返回:**返回浮点值

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

# setting position
media_player.set_position(0.5)

# getting position
value = media_player.get_position()

# printing value
print("Current media Position: ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```py
Current media Position: 
0.5

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

# setting position
media_player.set_position(0.3)

# getting position
value = media_player.get_position()

# printing value
print("Current media Position: ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```py
Current media Position: 
0.3

```