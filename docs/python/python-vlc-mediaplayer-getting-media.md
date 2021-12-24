# Python VLC 媒体播放器–获取媒体

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-media/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-media/)

在本文中，我们将看到如何在 python vlc 模块中获取 MediaPlayer 对象的媒体。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。媒体可以是 vlc 支持的视频甚至音频，可以借助`set_media`方法进行设置。

> 为此，我们将对 MediaPlayer 对象使用`get_media`方法
> 
> **语法:** media_player.get_media()
> 
> **论证:**不需要论证
> 
> **返回:**返回媒体对象

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

# getting media
value = media_player.get_media()

# printing media
print("Media : ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```py
Media : 
vlc.Media object at 0x00000254E3CE3408

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

# getting media
value = media_player.get_media()

# printing media
print("Media : ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```py
Media : 
vlc.Media object at 0x00000254E3CE3A06

```