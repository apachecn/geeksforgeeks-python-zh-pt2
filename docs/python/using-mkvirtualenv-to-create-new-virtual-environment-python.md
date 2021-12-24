# 使用 mkvirtualenv 创建新的虚拟环境–Python

> 原文:[https://www . geesforgeks . org/using-mkvirtualenv-to-create-new-virtual-environment-python/](https://www.geeksforgeeks.org/using-mkvirtualenv-to-create-new-virtual-environment-python/)

使用虚拟环境如果您已经安装了 python 版本，并且希望在不打扰旧版本的情况下为项目使用不同的版本。为不同的项目使用新的虚拟环境是一个很好的实践。

有多种方法可以创建它，今天我们将使用 mkvirtualenv 命令创建一个。

虚拟包装

要使用 *mkvirtualenv* 命令，您需要安装 *virtualenvwrapper* ，这只是一组 python 扩展命令。

确保安装了 pip。

```py
$ sudo apt-get install python3-pip

```

安装虚拟包装器

```py
$ sudo pip3 install virtualenvwrapper

```

通过–

```py
$ sudo gedit ~/.bashrc

```

打开 bashrc

打开后，添加以下几行:

```py
export WORKON_HOME=$HOME/.virtualenvs
export PROJECT_HOME=$HOME/Devel
source /usr/local/bin/virtualenvwrapper.sh

```

保存 bashrc 文件。

**使用 mkvirtualenv 命令**

现在让我们使用它，

语法为:

```py
$ mkvirtualenv venv_name

```

如果你想在另一个版本的 python 上工作，试试这个:

```py
$ mkvirtualenv -p python3.x venv_name
$(venv_name) // You will see something like this

```

注意:你可以用任何版本来代替 x。

要在现有虚拟环境中工作，

```py
$ workon venv_name

```

走出虚拟环境–

```py
$(venv_name) deactivate

```

要查看您的虚拟环境列表，请转至-

```py
Home/.virtualenvs
```