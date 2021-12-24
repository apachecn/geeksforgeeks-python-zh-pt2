# 使用 Python 下载 YouTube 媒体/音频–pafy

> 原文:[https://www . geesforgeks . org/YouTube-media audio-download-using-python-pafy/](https://www.geeksforgeeks.org/youtube-mediaaudio-download-using-python-pafy/)

本教程将帮助您使用 pafy 库使用 python 下载 youtube 视频或音频。Pafy 库用于检索 YouTube 内容和元数据。

**Pafy**
的特性(I)检索元数据，如浏览量、持续时间、评级、作者、缩略图、关键词。
(ii)以要求的分辨率/比特率/格式/文件大小下载视频或音频
(iii)命令行工具(ytdl)用于直接从命令行下载
(iv)仅下载 m4v 或 webm 格式的视频(无音频)
(v)仅下载 ogg 或 m4a 格式的音频(无视频)
(vi)与 Python 2.6+和 3.3+
一起工作(vii)可选依赖于 youtube-dl(推荐；更稳定)

**安装**

```
virtualenv venv
pip install pafy

```

**库导入**

```
 import pafy
```

**示例 1:**
检索诸如浏览量、持续时间、评级、作者、描述等元数据。

```
import pafy

# url of video
url = "https://www.youtube.com/watch?v=Ns4LCeeOFS4&t=320s"

# instant created
video = pafy.new(url)

# print title
print(video.title)

# print rating
print(video.rating)

# print viewcount
print(video.viewcount)

# print author & video length
print(video.author, video.length)

# print duration, likes, dislikes & description
print(video.duration, video.likes, video.dislikes, video.description)
```

输出:

```
Dynamic Programming | Set 3 (Longest Increasing Subsequence) | GeeksforGeeks
4.30275249481
57739
GeeksforGeeks 396
00:06:36 180 38 Explanation for the article: https://www.geeksforgeeks.org/dynamic-programming-set-3-longest-increasing-subsequence/

```

**示例 2:**
下载最佳分辨率视频，不考虑扩展名

```
import pafy

url = "https://www.youtube.com/watch?v=eACohWVwTOc"
video = pafy.new(url)

streams = video.streams
for i in streams:
    print(i)

# get best resolution regardless of format
best = video.getbest()

print(best.resolution, best.extension)

# Download the video
best.download()
```

输出:

```
normal:3gp@176x144
normal:3gp@320x180
normal:webm@640x360
normal:mp4@640x360
normal:mp4@1280x720
1280x720 mp4
  25, 707, 969 Bytes [100.00%] received. Rate: [ 506 KB/s].  ETA: [0 secs]  

```

**示例 3:**
下载指定特定格式的视频(比如. 3gp)

```
import pafy

url = "https://www.youtube.com/watch?v=eACohWVwTOc"
video = pafy.new(url)

streams = video.streams
for i in streams:
    print(i)

# get best resolution of a specific format
# set format out of(mp4, webm, flv or 3gp)
best = video.getbest(preftype ="3gp")

best.download()
```

输出:

```
normal:3gp@176x144
normal:3gp@320x180
normal:webm@640x360
normal:mp4@640x360
normal:mp4@1280x720
  6, 049, 643 Bytes [100.00%] received. Rate: [ 241 KB/s].  ETA: [0 secs]   

```

**示例 4:**
下载特定格式的音频。

```
import pafy 

url = "https://www.youtube.com/watch?v =eACohWVwTOc"
video = pafy.new(url)

audiostreams = video.audiostreams
for i in audiostreams:
    print(i.bitrate, i.extension, i.get_filesize())

audiostreams[3].download()
```

输出:

```
160k webm 1365668
160k webm 1811815
160k m4a 3470205
160k webm 3301003
160k webm 3588746

```

**示例 5:**
下载最佳音频

```
import pafy 

url = "https://www.youtube.com/watch?v=eACohWVwTOc"
video = pafy.new(url)

bestaudio = video.getbestaudio()
bestaudio.download()
```

输出:

参考资料:[https://pypi . python . org/pypi/pafy](https://pypi.python.org/pypi/pafy)