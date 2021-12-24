# Python VLC 实例–设置应用程序的元数据

> 原文:[https://www . geesforgeks . org/python-VLC-实例-设置-应用程序元数据/](https://www.geeksforgeeks.org/python-vlc-instance-setting-meta-data-of-application/)

在本文中，我们将看到如何从 python vlc 模块中的 Instance 类设置应用程序的元信息。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。实例作为 VLC 图书馆的一个主要对象，通过实例对象，我们可以创建媒体播放器，列表播放器或任何其他在 VLC 可用的播放器。实例类在 VLC 用于创建各种对象的基类。元数据包含关于应用程序的原始信息，可以借助`set_user_agent`方法为应用程序设置名称。

> 为此，我们将对实例对象使用`set_app_id`方法
> 
> **语法:** instance.set_app_id(id，版本，名称)
> 
> **参数:**以 id、版本、名称为参数，均为字符串格式
> 
> **返回:**返回无

下面是实现

```
# importing vlc module
import vlc

# importing time module
import time

# creating Instance class object
player = vlc.Instance()

# setting application meta data
player.set_app_id("vlc.GFG", "1.2", "GFG")

# creating a new media list
media_list = player.media_list_new()

# creating a media player object
media_player = player.media_list_player_new()

# creating a new media
media = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media)

# setting media list to the mediaplayer
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/57ccffa8c486070958f67ed1dd7ef62e.png)

下面是另一个例子
的实现

```
# importing vlc module
import vlc

# importing time module
import time

# creating Instance class object
player = vlc.Instance()

# setting application meta data
player.set_app_id("vlc.GFG-2", "1.01", "GFG-2")

# creating a new media list
media_list = player.media_list_new()

# creating a media player object
media_player = player.media_list_player_new()

# creating a new media
media = player.media_new("1.mp4")

# adding media to media list
media_list.add_media(media)

# setting media list to the mediaplayer
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/1182bf29ec1fe0d0a2c3ce2234f329d4.png)