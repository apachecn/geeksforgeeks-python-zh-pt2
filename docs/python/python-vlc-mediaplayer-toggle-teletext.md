# Python VLC 媒体播放器–切换 Teletext

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-VLC-media player-toggle-teletext/

在本文中，我们将看到如何在 python vlc 模块的 MediaPlayer 对象中切换图文电视。VLC 媒体播放器是 VideoLAN 项目开发的一款免费开源的便携式跨平台媒体播放器软件和流媒体服务器。媒体播放器对象是 vlc 模块中播放视频的基本对象。我们可以借助`MediaPlayer`方法创建一个 MediaPlayer 对象。切换图文电视，即视频输出的透明状态。

> 为此，我们将对 MediaPlayer 对象使用`toggle_teletext`方法
> 
> **语法:**media _ player . toggle _ 图文电视()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

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

# toggle teletext
media_player.toggle_teletext()

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(1)
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

# toggle teletext
media_player.toggle_teletext()

# start playing video
media_player.play()

# wait so the video can be played for 5 seconds
# irrespective for length of video
time.sleep(1)
```

**输出:**
![](img/adad80dcd4fb054e2f8093e65d2cb30f.png)