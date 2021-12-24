# Python VLC 媒体列表播放器–获取当前状态

> 原文:[https://www . geesforgeks . org/python-VLC-medialistpayer-get-current-state/](https://www.geeksforgeeks.org/python-vlc-medialistplayer-getting-current-state/)

在本文中，我们将看到如何在 python vlc 模块中显示 MediaListPlayer 对象的当前状态。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体列表播放器用于连续播放多个媒体，例如播放一个系列，而不是接受媒体列表中的单个媒体。它的工作方式几乎与 MediaPlayer 对象相似，但它能够播放媒体列表。状态可以是播放暂停或关闭，我们可以借助`set_pause`方法随时暂停和恢复媒体列表播放器，借助`play`方法可以开始播放。

> 为了做到这一点，我们将使用媒体列表播放器对象的`get_state`方法
> 
> **语法:** media_list_player.get_state()
> 
> **论证:**不需要论证
> 
> **返回:**返回状态对象

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

# creating a new media list object
media_list = player.media_list_new()

# creating a new media
media = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting media player current state
value = media_player.get_state()

# printing value
print(value)
```

**输出:**
![](img/57ccffa8c486070958f67ed1dd7ef62e.png)

```py
State.Playing

```

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

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting media player current state
value = media_player.get_state()

# printing value
print(value)
```

**输出:**
![](img/1182bf29ec1fe0d0a2c3ce2234f329d4.png)

```py
State.Playing

```