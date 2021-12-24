# Python VLC 媒体列表播放器–将媒体播放器设置为它

> 原文:[https://www . geesforgeks . org/python-VLC-medialistpayer-setting-media-player-to-it/](https://www.geeksforgeeks.org/python-vlc-medialistplayer-setting-media-player-to-it/)

在本文中，我们将看到如何在 python vlc 模块中将 media player 设置为 MediaListPlayer 对象。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体列表播放器用于连续播放多个媒体，例如播放一个系列，而不是接受媒体列表中的单个媒体。它的工作方式几乎与 MediaPlayer 对象相似，但它能够播放媒体列表。媒体播放器是 vlc 模块中所有可用播放器的基类。

> 为了做到这一点，我们将使用媒体列表播放器对象的`set_media_player`方法
> 
> **语法:**media _ list _ player . set _ media _ player(media _ player)
> 
> **参数:**以 MediaPlayer 实例为参数
> 
> **返回:**返回无

下面是实现

```py
# importing vlc module
import vlc

# importing time module
import time

# creating a media player object
media_player = vlc.MediaListPlayer()

# creating Instance class object
player = vlc.Instance()

# creating a new media list
media_list = player.media_list_new()

# creating a new media
media = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media)

# setting media list to the media player
media_player.set_media_list(media_list)

# new media player instance
new = player.media_player_new()

# setting media player to it
media_player.set_media_player(new)

# start playing video
media_player.play()
```

**输出:**
![](img/57ccffa8c486070958f67ed1dd7ef62e.png)

下面是另一个例子
的实现

```py
# importing vlc module
import vlc

# importing time module
import time

# creating a media player object
media_player = vlc.MediaListPlayer()

# creating Instance class object
player = vlc.Instance()

# creating a new media list
media_list = player.media_list_new()

# creating a new media
media = player.media_new("1.mp4")

# adding media to media list
media_list.add_media(media)

# setting media list to the media player
media_player.set_media_list(media_list)

# new media player instance
new = player.media_player_new()

# setting media player to it
media_player.set_media_player(new)

# start playing video
media_player.play()
```

**输出:**
![](img/1182bf29ec1fe0d0a2c3ce2234f329d4.png)