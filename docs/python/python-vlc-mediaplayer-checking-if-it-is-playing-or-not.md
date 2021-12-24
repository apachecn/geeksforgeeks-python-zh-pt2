# Python VLC MediaPlayer–检查它是否正在播放

> 原文:[https://www . geesforgeks . org/python-VLC-media player-checking-if-it-playing-or-not/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-checking-if-it-is-playing-or-not/)

在本文中，我们将看到如何在 python vlc 模块中检查视频是否在 MediaPlayer 对象中播放。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。我们用`play`的方法播放视频。

> 为此，我们将对 MediaPlayer 对象使用`is_playing`方法
> 
> **语法:** media_player.is_playing()
> 
> **论证:**不需要论证
> 
> **返回:**不玩则返回 0，玩则返回 1

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

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# checking if it is playing
value = media_player.is_playing()

# printing value
print("Is playing : ")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```py
Is playing : 
1

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

# start playing video + commenting it 
# media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# checking if it is playing
value = media_player.is_playing()

# printing value
print("Is playing : ")
print(value)
```

**输出:**

```py
Is playing : 
0

```