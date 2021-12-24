# Python VLC MediaPlayer–切换全屏

> 原文:[https://www . geesforgeks . org/python-VLC-media player-toggling-全屏/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-toggling-full-screen/)

在本文中，我们将看到如何在 python vlc 模块中切换 MediaPlayer 对象的全屏。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。切换非嵌入式视频输出的全屏状态。默认情况下，媒体不处于全屏模式。

> 为此，我们将对 MediaPlayer 对象使用`toggle_fullscreen`方法
> 
> **语法:**media _ player . toggle _ full screen()
> 
> **论证:**不需要论证
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

# toggling full screen
media_player.toggle_fullscreen()

# media object
media = vlc.Media("death_note.mkv")

# setting media to the media player
media_player.set_media(media)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/b9eb6c3bd27106a39edd9d3c440ac2fd.png)

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

# toggling full screen
media_player.toggle_fullscreen()

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

![](img/c0f8b2d777a1a069801b56edaaa0ebe7.png)