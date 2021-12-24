# Python VLC MediaPlayer–获取光标

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-cursor/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-cursor/)

在本文中，我们将看到如何在 python vlc 模块中获取 MediaPlayer 对象中的光标位置。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。视频上的鼠标指针坐标表示为二元组(x，y)。坐标以解码视频分辨率表示，而不是以屏幕/视口上的像素表示。

> 为此，我们将对 MediaPlayer 对象使用`video_get_cursor`方法
> 
> **语法:**media _ player . video _ get _ cursor()
> 
> **论证:**不需要论证
> 
> **返回:**返回元组

下面是实现

```py
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media resource locator
mrl = "death_note.mkv"

# setting mrl to the media player
media_player.set_mrl(mrl)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting cursor co-ordinates
value = media_player.video_get_cursor()

# printing cursor co-ordinates
print("Cursor Co-ordinates : ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```py
Cursor Co-ordinates : 
(655, 436)

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

# media resource locator
mrl = "1.mp4"

# setting mrl to the media player
media_player.set_mrl(mrl)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting cursor co-ordinates
value = media_player.video_get_cursor()

# printing cursor co-ordinates
print("Cursor Co-ordinates : ")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```py
Cursor Co-ordinates : 
(607, 267)
```