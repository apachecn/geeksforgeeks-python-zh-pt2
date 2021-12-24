# Python VLC 媒体播放器–设置媒体角色

> 原文:[https://www . geesforgeks . org/python-VLC-media player-setting-media-role/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-setting-media-role/)

在本文中，我们将看到如何在 python vlc 模块中设置 MediaPlayer 对象的角色。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。角色可以是可用角色，也可以是自定义角色。

> 为此，我们将对 MediaPlayer 对象使用`set_role`方法
> 
> **语法:** media_player.set_role(角色)
> 
> **参数:**它将角色作为可用角色的参数，它可以是角色 id
> 
> **返回:**成功返回 0，错误返回-1

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

# setting media player role
media_player.set_role(2)

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

# setting media player role
media_player.set_role(2)

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