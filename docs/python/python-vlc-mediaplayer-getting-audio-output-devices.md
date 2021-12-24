# Python VLC 媒体播放器–获取音频输出设备

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-audio-output-devices/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-audio-output-devices/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的输出设备列表。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。音频输出设备可以内置扬声器或耳机以及外置扬声器。

> 为此，我们将对 MediaPlayer 对象使用`audio_output_device_enum`方法
> 
> **语法:**media _ player . audio _ output _ device _ enum()
> 
> **论证:**不需要论证
> 
> **返回:**返回一个潜在音频输出设备的无终止链表。它必须通过音频输出设备列表释放()

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

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting track
value = media_player.audio_output_device_enum()

# printing value
print("Audio Output Devices: ")
print(value)
```

**输出:**
![](img/19176fb5a1c679e002bbe99bd5b48532.png)

```py
Audio Output Devices: 

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

# setting video scale
media_player.video_set_scale(0.6)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting track
value = media_player.audio_output_device_enum()

# printing value
print("Audio Output Devices: ")
print(value)
```

**输出:**
![](img/5390004d24c75ca965ba2daf456c2851.png)

```py
Audio Output Devices: 
vlc.LP_AudioOutputDevice object at 0x0000021A9E961A86

```