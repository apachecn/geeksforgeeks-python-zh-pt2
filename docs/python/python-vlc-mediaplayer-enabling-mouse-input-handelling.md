# Python VLC 媒体播放器–启用鼠标输入处理

> 原文:[https://www . geesforgeks . org/python-VLC-media player-enabled-鼠标-输入-handelling/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-enabling-mouse-input-handelling/)

在本文中，我们将看到如何在 python vlc 模块中启用鼠标输入来处理 MediaPlayer 对象。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。通过输入处理，可以创建事件处理程序，并可以通过鼠标输入来执行操作。

> 为此，我们将对 MediaPlayer 对象
> **使用 video_set_mouse_input 方法语法:**media _ player . video _ set _ mouse _ input(True)
> **参数:**它以 bool 为参数
> **返回:**它返回 None

下面是实现

## 蟒蛇 3

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

# making mouse input enable
media_player.video_set_mouse_input(True)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**

![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

下面再举一个例子
就是实现

## 蟒蛇 3

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

# making mouse input enable
media_player.video_set_mouse_input(True)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**

![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)