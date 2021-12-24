# Python VLC 媒体播放器–设置当前音轨

> 原文:[https://www . geesforgeks . org/python-VLC-media player-setting-current-audio-track/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-setting-current-audio-track/)

在本文中，我们将看到如何在 python vlc 模块中设置 MediaPlayer 对象的当前音轨。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。例如，一部电影可以有英语音轨和印地语音轨。当前音轨是媒体中当前播放的音轨。

> 为此，我们将对 MediaPlayer 对象使用`audio_set_track`方法
> 
> **语法:**media _ player . audio _ set _ track(n)
> 
> **自变量:**它以轨迹 id 为自变量
> 
> **返回:**成功返回 0，出错返回-1。

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

# setting audio track
media_player.audio_set_track(1)

# setting volume
media_player.audio_set_volume(80)

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

# setting audio track
media_player.audio_set_track(1)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/5390004d24c75ca965ba2daf456c2851.png)