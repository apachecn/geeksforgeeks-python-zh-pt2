# Python VLC MediaPlayer–获取完整标题描述

> 原文:[https://www . geesforgeks . org/python-VLC-media player-get-full-title-description/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-getting-full-title-description/)

在本文中，我们将看到如何在 python vlc 模块中获得 MediaPlayer 对象的标题描述。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。标题描述给出视频标题的可用描述。

> 为此，我们将对 MediaPlayer 对象使用`get_full_title_descriptions`方法
> 
> **语法:**media _ player . get _ full _ title _ descriptions()
> 
> **论证:**不需要论证
> 
> **返回:**返回列表

下面是实现

```
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media resource locator
mrl = "death_note.mkv"

# setting mrl to the media player
media_player.set_mrl(mrl)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting title description
value = media_player.get_full_title_descriptions()

# printing title description
print("Title Description")
print(value)
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

```
Title Description
generator object MediaPlayer.get_full_title_descriptions.locals.genexpr at 0x000002D57AD935A1

```

下面是另一个例子
的实现

```
# importing vlc module
import vlc

# importing time module
import time

# creating vlc media player object
media_player = vlc.MediaPlayer()

# media resource locator
mrl = "1.mp4"

# setting mrl to the media player
media_player.set_mrl(mrl)

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(5)

# getting title description
value = media_player.get_full_title_descriptions()

# printing title description
print("Title Description")
print(value)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)

```
Title Description
generator object MediaPlayer.get_full_title_descriptions.locals.genexpr at 0x000002D57AD935C8

```