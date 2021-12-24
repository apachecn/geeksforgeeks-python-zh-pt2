# Python VLC 媒体播放器–获取当前媒体的长度

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-length-of-current-media/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-length-of-current-media/)

在本文中，我们将看到如何在 python vlc 模块中获取 MediaPlayer 对象的当前媒体长度。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。长度基本上就是当前媒体有多长。

> 为此，我们将对 MediaPlayer 对象使用`get_length`方法
> 
> **语法:** media_player.get_length()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数(毫秒)

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

# getting length of the current media
value = media_player.get_length()

# printing value
print("Length of the media : ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```py
Length of the media : 
1377385

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

# getting length of the current media
value = media_player.get_length()

# printing value
print("Length of the media : ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```py
Length of the media : 
5009

```