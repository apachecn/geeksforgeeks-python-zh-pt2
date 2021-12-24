# Python VLC 媒体播放器–获取视频输出数量

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-视频输出数量/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-number-of-video-outputs/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的视频输出数量。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。视频输出是普通设备的输出源，只有一个视频输出，但也可以大于 1。

> 为此，我们将对 MediaPlayer 对象使用`has_vout`方法
> 
> **语法:** media_player.has_vout()
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

下面是实现

```
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

# getting number of video outputs
value = media_player.has_vout()

# printing value
print("Number of Video output(s) : ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```
Number of Video output(s) : 
1

```

下面是另一个例子
的实现

```
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

# getting number of video outputs
value = media_player.has_vout()

# printing value
print("Number of Video output(s) : ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```
Number of Video output(s) : 
1

```