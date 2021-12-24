# Python VLC MediaPlayer–设置字幕

> 原文:[https://www . geesforgeks . org/python-VLC-media player-setting-subtitle/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-setting-subtitle/)

在本文中，我们将看到如何在 python vlc 模块中为 MediaPlayer 对象的媒体设置当前字幕。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。字幕是从电影、电视节目、电子游戏等中的对话或评论的抄本或剧本中导出的文本，通常显示在屏幕底部，但是如果屏幕底部已经有文本，也可以在屏幕顶部。

> 为此，我们将对 MediaPlayer 对象使用`video_set_spu`方法
> 
> **语法:**media _ player . video _ set _ spu(id)
> 
> **自变量:**以字幕 id 为自变量
> 
> **返回:**成功返回 0，超出范围返回-1。

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

# setting subtitle
media_player.video_set_spu(2)

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

# setting subtitle
media_player.video_set_spu(2)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting subtitle count
value = media_player.video_get_spu_count()

# printing value
print("Subtitle Count: ")
print(value)
```

**输出:**
![](img/5390004d24c75ca965ba2daf456c2851.png)