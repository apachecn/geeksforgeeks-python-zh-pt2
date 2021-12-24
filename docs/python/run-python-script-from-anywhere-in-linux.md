# 在 linux 的任何地方运行 python 脚本

> 原文:[https://www . geesforgeks . org/run-python-script-from-anywhere-in-Linux/](https://www.geeksforgeeks.org/run-python-script-from-anywhere-in-linux/)

在 Linux 中，有一种方法可以从任何地方执行 python 文件。这可以通过在终端中键入几个命令来完成。

### 先决条件:

*   [**Linux 中的基本 Shell 命令**](https://www.geeksforgeeks.org/essential-linuxunix-commands/)
*   **[蟒蛇基础知识](https://www.geeksforgeeks.org/python-programming-language/)**

### 步骤:

*   首先，打开终端，进入主目录。要转到主目录，请键入以下命令。

    ```py
    cd ~
    ```

*   创建一个文件夹和一个 python 脚本。让文件夹的名称为“check”，脚本的名称为“file1”。键入以下命令执行上述操作。

    ```py
    mkdir check
    cd check
    touch file1.py

    ```

*   Then type this script in the file1.py

    ```py
    import os
    i = 1

    # Write the path where to create the directories
    path ="/home / dev / test/"
    try:
        while i<5:
            os.mkdir(path+"file"+str(i))
            i+= 1
    except OSError:
        print("File creation failed !!")
    ```

    该脚本将在指定路径中创建 4 个目录。

*   Then to find where the python is installed in the system type the below commands.
    For python 2.7

    ```py
    which python
    ```

    对于 python 3

    ```py
    which python3
    ```

*   Copy the output and add this in the starting of the script e.g if output is `/usr/bin/python3` then write the below command in the starting of the script.

    ```py
    #!/usr/bin/python3
    ```

    所以 python 脚本看起来像

    ```py
    #! usr / bin / python3
    import os
    i = 1
    # Write the path where to create the directories
    path ="/home / dev / test/"
    try:
        while i<5:
            os.mkdir(path+"file"+str(i))
            i+= 1
    except OSError:
        print("File creation failed !!")
    ```

*   Type the following command to get the path of the working directory, starting from the root.

    ```py
    pwd
    ```

    也罢`/home/usr/check`

*   Add this path in `$PATH` variable. For this type in terminal

    ```py
    sudo nano .bashrc
    ```

    在执行此命令之前，请确保您在主目录中。
    然后在文件中添加这一行

    ```py
    export PATH=$PATH:/home/dev/check
    ```

    这将被添加到路径变量中。然后打字

    ```py
     source ~/.bashrc
    ```

*   关闭终端，然后再次打开。现在我们可以通过输入文件名

    ```py
    file1.py
    ```

    从终端的任何地方直接运行 python 文件

这将在 check 文件夹中创建四个目录。现在，任何放置在 check 目录中的 python 文件都可以通过输入文件名从终端的任何地方执行。