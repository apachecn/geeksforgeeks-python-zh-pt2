# Python VLC MediaPlayer–获取曲目

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-track/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-track/)

在本文中，我们将看到如何在 python vlc 模块中跟踪 MediaPlayer 对象。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。一个视频可以有多个用户可以选择的轨道。可以借助`video_set_track`方法进行设置。

> 为此，我们将对 MediaPlayer 对象使用`video_get_track`方法
> 
> **语法:**media _ player . video _ get _ track()
> 
> **论证:**不需要论证
> 
> **返回:**如果没有活动输入，则返回视频轨道 ID (int)或-1

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

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting track 
value = media_player.video_get_track()

# printing value
print("Track : ")
print(value)
```

**输出:**
![](img/19176fb5a1c679e002bbe99bd5b48532.png)

```
Track : 
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

# setting video scale
media_player.video_set_scale(0.6)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting track 
value = media_player.video_get_track()

# printing value
print("Track : ")
print(value)
```

**输出:**
![](img/5390004d24c75ca965ba2daf456c2851.png)

```
Track : 
0

```