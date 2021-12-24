# python 中的源码分发和内置分发

> 原文:[https://www . geesforgeks . org/source-distribution-and-build-distribution-in-python/](https://www.geeksforgeeks.org/source-distribution-and-built-distribution-in-python/)

Python 是关于分布的。它可以被定义为文件的集合，这些文件一起允许构建、打包和分发模块。一旦系统中存在发行版，就可以轻松安装。此外，它可以与 PyPI(Python 包索引)社区共享，以便其他人可以使用您的发行版。
为了更清楚，考虑 Anaconda，它是 python 和 R 编程语言的开源发行版。它包含 python、各种库(numpy、pandas、matplotlib tec)、IDE(如 Spyder、Jupyter Notebook)和包管理器 conda 以及其中的 pip，使用户能够将资源用于各种机器学习任务，而无需显式下载。

python 中有两种分发类型:

1.  **源码发布(`sdist`)**–包含`setup.py`(包含模块/元数据的信息)、模块/脚本的源文件(`.py`文件或`.c/.cpp`二进制模块)、数据文件等。结果是一个存档，然后可以用来重新编译任何平台上的一切，如 linux，windows 和 mac。
2.  **内置分发(`bdist`)**–它创建的分发包括`.pyc`文件(python 字节码)、`.so/.dll/.dylib`二进制模块、`.exe`如果在 windows 上使用 py2 exe(python 的扩展，可用于将脚本转换为 exe 形式，无需安装 python 即可使用)、数据文件……但没有`setup.py`。结果是一个特定于平台(例如 linux-x86_64)和 Python 版本的归档。它可以被安装，然后通过将其提取到文件系统的根目录中直接使用(可执行文件在/usr/bin(或等效文件)中，数据文件在/usr/share 中，模块在/usr/lib/PitOnx 中)。x/站点包/…)。

**setup.py**
`setup.py`是一个 python 文件，它通常会告诉系统，你要安装的模块/包已经使用 Distutils 打包分发了，Distutils 是 python 模块分发的标准。这是最重要的文件。它是配置项目各个方面的文件。setup.py 的主要特点是包含全局`setup()`功能。此函数的关键字参数是如何定义项目的具体细节。

**制作基本的 setup.py 文件。**

```py
# import setup function from 
# python distribution utilities
from distutils.core import setup 

# Calling the setup function
setup(
      name = 'nesters',
      version = '1.0.0',
      py_modules = ['addition'],
      author ='a geek',
      author_email = 'ageek@gmail.com',
      url = 'https;//ageek.com',
      description = 'a simple program to add two numbers',
      keywords='adds two numbers',
)
```

让我们看看 setup 函数的不同参数有什么作用:

*   **名称:**是项目名称。该包将在 PyPI 上以此名称列出。
*   **版本:**可以指定项目当前版本的字符串。如何设置系列版本的方案完全是你自己的选择(‘1.0’或‘0.1’甚至‘0 . 0 . 1’也可以)。如果项目已发布，该版本将在每个版本的 PyPI 上显示。每次上传新版本时，您也必须更改这个参数。
*   **描述:**关于包裹的简短描述。长描述参数可用于长描述。
*   **网址:**项目的主页网址。这使得人们更容易关注或参与项目。
*   **作者，作者 _ 邮箱:**关于作者的详细信息。
*   **许可证:**指定使用的许可证类型。
*   **分类器:**这是一个字符串列表，可以指定项目的更多细节，如项目的开发状态、主题、许可证和支持的 python 版本。
*   **install_requires:** 可以用来指定你的包需要运行哪些第三方库。当有人安装您的软件包时，这些依赖项将由 pip 安装。
*   **关键词:**列出描述项目的关键词。

让我们创建一个 addition.py 文件，其中包含两个数字相加的代码。在记事本中创建此文件，并将其保存为 addition.py。

```py
def addition():
    n = 5
    print("addition of two numbers")
    while(n>= 0):
        a, b = input("enter two numbers: ").split()
        try:
            value1 = int(a)
            value2 = int(b)
            break
        except e:
            print("re enter numbers" )
    sum = value1 + value2
    print("sum of two numbers is :", sum)
```

**制作源分布:**

*   要进行源代码分发，首先创建一个文件夹，并将 setup.py 和 addition.py 脚本复制到该文件夹中(让我们将其命名为 nester)。然后打开终端，将当前目录改为文件夹的目录，例如:如果在桌面–C:\ Users \ HP PC \ Desktop \ nester。
*   最后键入`setup.py sdist.`这将进行源分布。

执行以下命令后，一个 dist 文件夹将包含一个 nester1-1.1.0.tar 文件和一个包含 python 列表的 MANIFEST 文件(。py)由 sdist 命令构建的文件，将在同一个源文件夹(nester)中形成。

创建源代码分发时，可以使用`--format`选项指定许多格式。
例如:

```py
python setup.py sdist --formats=gztar,zip

```

不同的格式有:

| 格式 | 描述 |
| --- | --- |
| 活力 | zip 文件(。zip) |
| gstar | gzip 和 tar 文件(. tar.gz) |
| bztar | bzip2 '和 tar 文件(. tar.bz2) |
| xztar | xz 和 tar 文件(. tar.xz) |
| ztar | 压缩 tar 文件(. tar.Z) |
| 水手 | tar 文件 （.tar） |

**制作内置分布:**

*   从源分布中重复步骤 1。
*   最后输入`setup.py bdist`。这将创建一个构建的分布。

执行以下命令后，将创建两个文件夹:

1.  dist–包含 winRarZip 存档格式的“nester1-1.1.0.win-amd64”，在提取 Zip 文件时，会在 __pycache__ 文件夹中找到一个“addition.pyc”文件，这是您的“addition.py”文件的编译(字节代码)版本，特定于系统。
2.  build–其中包含库文件夹和“addition.py”文件。

创建构建的分发时，可以使用`--format`选项指定许多格式。
例如:

```py
python setup.py bdist --format=zip

```

不同的格式有:

| 格式 | 描述 |
| --- | --- |
| 活力 | zip 文件(。zip) |
| gstar | 压缩 tar 文件(. tar.Z) |
| ztar | bzip2 '和 tar 文件(. tar.bz2) |
| 水手 | tar 文件 （.tar） |
| 每分钟转数 | 每分钟转数 |
| pkgtool | Solaris pkgtool |
| sdux | Solaris pkgtool |
| wininet(wininet) | 用于 Windows 的自解压 ZIP 文件 |
| 中规模集成电路（medium-scale integration 的缩写） | Microsoft 安装程序 |