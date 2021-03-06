# Python VLC 媒体播放器–获取音轨描述

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-audio-traces-description/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-audio-tracks-description/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的音轨描述。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。在一些视频中，有不同的音轨可供使用，因此用户可以在它们之间切换，例如，一个视频可以有不同的语言，因此它可能有一个以上的音轨。

> 为此，我们将对 MediaPlayer 对象使用`audio_get_track_description`方法
> 
> **语法:**media _ player . audio _ get _ track _ description()
> 
> **论证:**不需要论证
> 
> **返回:**返回列表

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

# getting audio Tracks description
value = media_player.audio_get_track_description()

# printing subtitle description
print("Audio Tracks Description")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```py
Audio Tracks Description
[(-1, b'Disable'), (1, b'English - [English]'), (2, b'English Commentary - [English]')]

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

# getting audio Tracks description
value = media_player.audio_get_track_description()

# printing subtitle description
print("Audio Tracks Description")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```py
Audio Tracks Description
[]
```