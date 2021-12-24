# Python VLC 媒体列表–获取给定索引的媒体

> 原文:[https://www . geesforgeks . org/python-VLC-medialist-get-media-at-given-index/](https://www.geeksforgeeks.org/python-vlc-medialist-getting-media-at-given-index/)

在本文中，我们将看到如何在 python vlc 模块的 MediaList 对象中获取给定索引处的媒体。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。MediaList 对象包含多个媒体，换句话说，它有一个媒体列表，可以与 MediaListPlayer 对象一起使用来播放这些多个媒体对象。借助`add_media`方法，可以将多个媒体添加到媒体列表对象中，因此每个媒体都位于列表中各自的索引处。

> 为此，我们将对 MediaList 对象使用`item_at_index`方法
> 
> **语法:** media_list.item_at_index(n)
> 
> **自变量:**它以索引为自变量
> 
> **返回:**返回媒体对象

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

# creating a media list object
media_list = vlc.MediaList()

# creating a new media
media1 = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media1)

# creating a new media
media2 = player.media_new("1.mp4")

# adding another media
media_list.add_media(media2)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting media at the index 0 in media list
value = media_list.item_at_index(0)

# printing value
print(value)
```

**输出:**
![](img/57ccffa8c486070958f67ed1dd7ef62e.png)

```
vlc.Media object at 0x00000248E1B42981

```

另一个例子

```
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
media1 = player.media_new("1.mp4")

# adding media to media list
media_list.add_media(media1)

# creating a new media
media2 = player.media_new("death_note.mkv")

# adding media to media list
media_list.add_media(media2)

# setting media list to the media player
media_player.set_media_list(media_list)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting media at the index 1 in media list
value = media_list.item_at_index(1)

# printing value
print(value)
```

**输出:**
![](img/1182bf29ec1fe0d0a2c3ce2234f329d4.png)

```
vlc.Media object at 0x00000248E1B42988

```