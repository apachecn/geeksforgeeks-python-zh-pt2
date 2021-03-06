# Python VLC 媒体列表–插入媒体

> 原文:[https://www . geesforgeks . org/python-VLC-medialist-insert-media/](https://www.geeksforgeeks.org/python-vlc-medialist-inserting-media/)

在本文中，我们将看到如何在 python vlc 模块的 MediaList 对象中插入媒体。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。MediaList 对象包含多个媒体，换句话说，它有一个媒体列表，可以与 MediaListPlayer 对象一起使用来播放这些多个媒体对象。插入意味着我们可以在给定的索引处添加媒体，我们可以借助`add_media`方法将媒体添加到媒体列表中。

> 为此，我们将对 MediaList 对象使用`insert_media`方法
> 
> **语法:** media_list.insert_media(媒体，索引)
> 
> **参数:**以 Media 对象和索引为参数
> 
> **返回:**成功时返回 0，如果媒体列表为只读，则返回-1

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

# creating a media list object
media_list = vlc.MediaList()

# creating a new media
media = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media)

# creating a new media
media = player.media_new("1.mp4")

# inserting  media to media list at index 0
media_list.insert_media(media, 0)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/1182bf29ec1fe0d0a2c3ce2234f329d4.png)

另一个例子

```py
# importing vlc module
import vlc

# importing time module
import time

# creating a media player object
media_player = vlc.MediaListPlayer()

# creating Instance class object
player = vlc.Instance()

# creating a media list object
media_list = vlc.MediaList()

# creating a new media
media = player.media_new("1.mp4")

# adding media to media list
media_list.add_media(media)

# creating a new media
media = player.media_new("death_note.mkv")

# inserting  media to media list at index 0
media_list.insert_media(media, 0)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)
```

**输出:**
![](img/57ccffa8c486070958f67ed1dd7ef62e.png)