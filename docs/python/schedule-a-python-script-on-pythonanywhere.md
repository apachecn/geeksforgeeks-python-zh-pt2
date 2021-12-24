# 在 Python 上安排 Python 脚本

> 原文:[https://www . geesforgeks . org/schedule-a-python-script-on-python annywhere/](https://www.geeksforgeeks.org/schedule-a-python-script-on-pythonanywhere/)

让计算机 24/7 开着是不切实际的，所以如果你想每天在特定的时间执行 Python 脚本，你可能需要一台一直开着的计算机。为了实现这一点，一个网站[让你可以全天候访问这样一台电脑。您可以上传一个 Python 脚本，并将其安排在每天的特定时间运行。例如，当您想要从网站提取一些值(例如，天气数据)并每天用该值生成文本文件或其他报告时，这种可用性可能会很有用。](https://www.pythonanywhere.com/)

**要安排 Python 脚本在 Python 上执行，请执行以下简单步骤:**

*   在[这里](https://www.pythonanywhere.com)注册，初学者账户是免费的，有一些 T & C
*   转到您的仪表板，文件，上传一个文件，并上传您想要计划执行的 Python 文件。
*   转到任务，设置一天中您希望脚本执行的时间，并键入您上传的 Python 文件的名称(例如，myfirstpyscript.py)。
    **注**:输入的时间应以 UTC 为单位。

*   Click “create” and you are done.

    Python 文件现在将每天在您指定的时间执行。

    **示例:**下面是一个非常简单的 Python 脚本，可以用来调度执行。

    ```py
    from datetime import datetime

    # Saves a .txt file with file name
    # as 2020-01-11-10-20-23.txt
    with open(datetime.now().strftime("%Y-%m-%d-%H-%M-%S"), "w")as myfile:

        # Content of the file
        myfile.write("Hello World !")
    ```

    上面的代码创建了一个文本文件，并编写了字符串“Hello World！”在文本文件中。文本文件的名称将是当前日期和时间。例如，一个文件名示例是 2020-01-11-10-20-23.txt。

    该名称由`datetime.now()`生成，表示脚本执行的日期和时间。每次执行脚本时，脚本都会生成一个具有不同名称的新文本文件。每天都会创建一个新的文本文件。