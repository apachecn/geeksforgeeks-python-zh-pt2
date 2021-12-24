# Python VLC MediaPlayer–设置静音状态

> 原文:[https://www . geesforgeks . org/python-VLC-media player-setting-mute-status/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-setting-mute-status/)

在本文中，我们将看到如何在 python vlc 模块中设置 MediaPlayer 对象的静音状态。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。如果状态为真，则静音，否则取消静音@警告该功能并不总是有效。如果没有活动的音频回放流，静音状态可能不可用。如果使用数字直通(S/PDIF、HDMI…)，静音可能不太适用。还有一些音频输出插件根本不支持静音。@注意若要强制静音播放，请禁用所有音频轨道。这比静音更高效可靠。

> 为此，我们将对 MediaPlayer 对象使用`audio_set_mute`方法
> 
> **语法:** media_player.audio_set_mute(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回无

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

# making mute status True
media_player.audio_set_mute(True)

# setting video scale
media_player.video_set_scale(0.6)

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

# setting video scale
media_player.video_set_scale(0.6)

# making mute status True
media_player.audio_set_mute(True)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/5390004d24c75ca965ba2daf456c2851.png)