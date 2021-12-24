# Python VLC 媒体列表播放器–播放下一个项目

> 原文:[https://www . geesforgeks . org/python-VLC-medialistpayer-playing-next-item/](https://www.geeksforgeeks.org/python-vlc-medialistplayer-playing-next-item/)

在本文中，我们将看到如何在 python vlc 模块中播放 MediaListPlayer 对象中的下一个项目。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体列表播放器用于连续播放多个媒体，例如播放一个系列，而不是接受媒体列表中的单个媒体。它的工作方式几乎与 MediaPlayer 对象相似，但它能够播放媒体列表。我们可以借助`play`方法播放一个媒体，但是它从索引 0 开始播放媒体，给定索引的媒体可以借助`play_item_at_index`方法播放。

> 为了做到这一点，我们将使用媒体列表播放器对象的`next`方法
> 
> **语法:** media_list_player.next()
> 
> **论证:**不需要论证
> 
> **返回:**成功时返回 0，如果找不到项目则返回 1。

下面是实现

```
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

# creating a new media
media = player.media_new("1.mp4")

# adding media to media list
media_list.add_media(media)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play_item_at_index(0)

# playing next media in list
media_player.next()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**

![](img/1182bf29ec1fe0d0a2c3ce2234f329d4.png)

下面是另一个例子
的实现

```
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

# creating a new media
media = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play_item_at_index(0)

# playing next media in list
media_player.next()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/57ccffa8c486070958f67ed1dd7ef62e.png)