# Python VLC 媒体播放器–获得音频延迟

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-audio-delay/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-audio-delay/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的音频延迟。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。音频通道或音频轨道是存储设备或混音控制台中的音频信号通信通道，用于多轨道录制和声音增强等操作。音频延迟是指音频在延迟时间后会比正常时间播放。可以借助`audio_set_delay`方法进行设置。

> 为此，我们将对 MediaPlayer 对象使用`audio_get_delay`方法
> 
> **语法:**media _ player . audio _ get _ delay()
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

# setting video scale
media_player.video_set_scale(0.6)

# setting volume
media_player.audio_set_volume(80)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting audio delay
value = media_player.audio_get_delay()

# printing value
print("Audio delay : ")
print(value)
```

**输出:**
![](img/19176fb5a1c679e002bbe99bd5b48532.png)

```
Audio delay : 
0

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

# setting volume
media_player.audio_set_volume(70)

# setting video scale
media_player.video_set_scale(0.6)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting audio delay
value = media_player.audio_get_delay()

# printing value
print("Audio delay : ")
print(value)
```

**输出:**
![](img/5390004d24c75ca965ba2daf456c2851.png)

```
Audio delay : 
0

```