# Python VLC 实例–设置应用程序名称

> 原文:[https://www . geesforgeks . org/python-VLC-实例-设置-应用程序-名称/](https://www.geeksforgeeks.org/python-vlc-instance-setting-application-name/)

在本文中，我们将看到如何从 python vlc 模块中的 Instance 类设置应用程序名称。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。实例作为 VLC 图书馆的一个主要对象，通过实例对象，我们可以创建媒体播放器，列表播放器或任何其他在 VLC 可用的播放器。实例类在 VLC 用于创建各种对象的基类。当协议需要时，LibVLC 将名称作为用户代理字符串传递。

> 为此，我们将对实例对象使用`set_user_agent`方法
> 
> **语法:** instance.set_user_agent(名称，http)
> 
> **参数:**它以名称和 http 代理作为参数
> 
> **返回:**返回无

下面是实现

```py
# importing vlc module
import vlc

# importing time module
import time

# creating Instance class object
player = vlc.Instance()

# setting application name
player.set_user_agent("GFG", "GFG / Python / 3.6")

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

```py
# importing vlc module
import vlc

# importing time module
import time

# creating Instance class object
player = vlc.Instance()

# setting application name
player.set_user_agent("GFG-2", "GFG-2 / Python / 3.6")

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