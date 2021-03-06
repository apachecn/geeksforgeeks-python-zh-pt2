# Python VLC MediaPlayer–设置音量

> 原文:[https://www . geesforgeks . org/python-VLC-media player-setting-volume/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-setting-volume/)

在本文中，我们将看到如何在 python vlc 模块中设置 MediaPlayer 对象的音量。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。VLC 为我们提供了改变媒体音量的功能，它可以以百分比的形式设置，即 0 表示静音，100 表示最大声音。

> 为此，我们将对 MediaPlayer 对象使用`audio_set_volume`方法
> 
> **语法:**media _ player . audio _ set _ volume(n)
> 
> **自变量:**以整数为自变量
> 
> **返回:**如果设置了音量，则返回-1，如果音量超出范围，则返回-1

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

# setting video scale
media_player.video_set_scale(0.6)

# setting volume
media_player.audio_set_volume(50)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/19176fb5a1c679e002bbe99bd5b48532.png)

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

# setting volume
media_player.audio_set_volume(70)

# setting video scale
media_player.video_set_scale(0.6)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/5390004d24c75ca965ba2daf456c2851.png)