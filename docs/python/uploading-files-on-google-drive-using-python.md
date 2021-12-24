# 使用 Python 上传谷歌硬盘上的文件

> 原文:[https://www . geesforgeks . org/uploading-file-on-Google-drive-use-python/](https://www.geeksforgeeks.org/uploading-files-on-google-drive-using-python/)

在现代互联网时代，大量平凡的或与工作相关的任务都是通过互联网完成的。存储在设备上的数据泄露可能会对个人/公司造成巨大伤害。考虑到恶意软件、病毒、蠕虫、特洛伊木马等数量的增加，静态数据的安全性已经成为许多人关注的问题。

保护数据最常见的方法之一是创建数据备份。虽然备份确实为关键数据提供了一些保护，但它应该远离原始数据。这样，即使包含原始数据的系统以某种方式遭到破坏，备份数据仍然是安全的。云存储是为实现这一目的而构建的技术。

任何拥有谷歌账户的人都可以使用 15gb 的免费云存储来存储他们的数据。这解决了异地备份的问题。但是每次上传文件数据可能会有点麻烦。因此，为了简化这个过程，我们将创建一个 python 程序，它可以查看目录，并将目录中的任何文件上传到我们的 Google Drive 帐户。

为此，我们将使用`pydrive`库。本模块未预装 python。要安装它，请在命令行中执行以下命令:

```
pip install pydrive

```

## 正在创建 OAuth 凭据

为了在每次我们想要上传一些数据到我们的 google 帐户时成功地验证它，我们需要创建一个 [OAuth](https://en.wikipedia.org/wiki/OAuth) 凭证。

完成上面的方法后，我们会得到一个类似于 *client_secret_(真的很长的 ID)的文件。json* 。将文件重命名为“ *client_secrets.json* ，并将其放在将创建主 python 程序的同一目录中。

**<font size="4">代号</font>**

```
from pydrive.drive import GoogleDrive
from pydrive.auth import GoogleAuth

# For using listdir()
import os

# Below code does the authentication
# part of the code
gauth = GoogleAuth()

# Creates local webserver and auto
# handles authentication.
gauth.LocalWebserverAuth()       
drive = GoogleDrive(gauth)

# replace the value of this variable
# with the absolute path of the directory
path = r"C:\Games\Battlefield"   

# iterating thought all the files/folder
# of the desired directory
for x in os.listdir(path):

    f = drive.CreateFile({'title': x})
    f.SetContentFile(os.path.join(path, x))
    f.Upload()

    # Due to a known bug in pydrive if we 
    # don't empty the variable used to
    # upload the files to Google Drive the
    # file stays open in memory and causes a
    # memory leak, therefore preventing its 
    # deletion
    f = None
```

上面的代码在执行时会执行操作系统默认浏览器的一个实例。然后，它会要求 pydrive 提供访问您的谷歌驱动帐户的权限。授予所有所需权限后，浏览器会显示一条消息

> 身份验证流程已经完成。

之后，上传文件到谷歌驱动器的过程开始。

使用上述程序时需要记住的某些事项

*   确保*“client _ secrets . JSON”*与 Python 程序在同一个目录中
*   目录(*路径*)不应包含任何子目录
*   你的谷歌驱动器应该有足够的空白空间，以便合并新文件
*   新文件将在谷歌硬盘的根目录下创建