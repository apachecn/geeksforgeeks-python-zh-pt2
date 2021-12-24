# Python VLC 实例–创建媒体播放器实例

> 原文:[https://www . geesforgeks . org/python-VLC-instance-creating-media player-instance/](https://www.geeksforgeeks.org/python-vlc-instance-creating-mediaplayer-instance/)

在本文中，我们将看到如何从 python vlc 模块中的 instance 类创建一个 MediaPlayer 实例。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。实例作为 VLC 图书馆的一个主要对象，通过实例对象，我们可以创建媒体播放器，列表播放器或任何其他在 VLC 可用的播放器。实例类在 VLC 用于创建各种对象的基类。媒体播放器对象用于播放单个或多个媒体。

> 为此，我们将对实例对象使用`media_player_new`方法
> 
> **语法:** instance.media_player_new()
> 
> **参数:**不需要参数，但可以将 uri 作为可选参数
> 
> **返回:**返回 MediaPlayer 对象

下面是实现

```
# importing vlc module
import vlc

# importing time module
import time

# creating Instance class object
player = vlc.Instance()

# creating a new media
media = player.media_new("death_note.mkv")

# creating a media player object
media_player = player.media_player_new()

media_player.set_media(media)

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

# creating Instance class object
player = vlc.Instance()

# creating a new media
media = player.media_new("1.mp4")

# creating a media player object
media_player = player.media_player_new()

media_player.set_media(media)

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