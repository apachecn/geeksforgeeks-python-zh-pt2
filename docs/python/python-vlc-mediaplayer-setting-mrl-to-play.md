# Python VLC MediaPlayer–设置 MRL 玩

> 原文:[https://www . geesforgeks . org/python-VLC-media player-setting-MRL-to-play/](https://www.geeksforgeeks.org/python-vlc-mediaplayer-setting-mrl-to-play/)

在本文中，我们将看到如何在 python vlc 模块中设置 MRL media player 对象。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。MRL 是媒体资源定位器，换句话说，它是要播放的媒体的目的地。

> 为此，我们将对 MediaPlayer 对象使用`set_mrl`方法
> 
> **语法:** media_player.set_mrl(mrl)
> 
> **自变量:**以字符串为自变量
> 
> **返回:**返回媒体对象

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
```

**输出:**
![](img/33c5fe6e13ea1c939ea793883a04f9c7.png)

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
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)