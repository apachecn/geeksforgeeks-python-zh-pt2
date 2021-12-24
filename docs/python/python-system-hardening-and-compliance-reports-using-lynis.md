# Python |使用 Lynis 的系统强化和合规性报告

> 原文:[https://www . geeksforgeeks . org/python-系统-强化和合规-报告-使用-lynis/](https://www.geeksforgeeks.org/python-system-hardening-and-compliance-reports-using-lynis/)

Lynis 是一款久经考验的安全工具，适用于运行 Linux、macOS 或基于 Unix 的操作系统的系统。它对您的系统执行广泛的运行状况扫描，以支持系统强化和合规性测试。该项目是开放源代码软件，拥有 GPL 许可证，自 2007 年开始提供。

由于 Lynis 是灵活的，它被用于几个不同的目的。Lynis 的典型用例包括:

*   安全审计
*   合规性测试(如 PCI、HIPAA、SOx)
*   渗透测试
*   漏洞检测
*   系统硬化

系统加固是指保护您的系统免受潜在威胁和漏洞的侵害。Lynis 可用于生成系统中各种威胁和漏洞的详细报告。然后，用户或系统管理员可以采取必要的措施来保护系统。
Lynis 的报告很难阅读，通常有很多信息。因此，我们使用 Bash 和 Python 脚本来解析报告，从报告中提取相关信息，如警告、建议，并将其作为报告存储在 excel 文件中。

【Lynis 的先决条件–

*   通过克隆 github 存储库在您的系统上安装 Lynis:[https://github.com/CISOfy/lynis](https://github.com/CISOfy/lynis)
*   使用命令 sudo pip3 安装熊猫来安装熊猫库。
*   一旦您在系统上安装了 Lynis，导航到 Lynis 目录，您会发现一堆文件以及一个名为 Lynis 的可执行文件。
*   使用 bash 脚本(代码如下)提取相关信息，如 lynis 报告中给出的警告和建议。创建一个名为 run.sh 的文件，并将 bash 代码复制粘贴到该文件中，并键入:sudo。/run.sh 运行 bash 脚本。
*   运行 Python 脚本(代码如下)对提取的数据进行清理和解析，并将相关信息输出为 excel 文件。

下面是 Bash 和 Python 脚本–

**重击脚本:**

## 尝试

```py
#!/bin/bash

# script to scrape/parse the report file and
# extract the relevant details and run the
# python script to display the details in a server.

echo "running......"
echo ""

sudo ./lynis audit system --quick

# execute warnings. sudo ./warnings.sh
echo "Generating warnings"
echo ""
echo "warnings are: "
echo ""

sudo cat /var/log/lynis-report.dat | grep warning | sed -e "s/warning\[\]\=//g"
sudo cat /var/log/lynis-report.dat | grep warning | sed -e "s/warning\[\]\=//g" | cat > warnings.txt

echo ""
echo "warnings generated"
echo "output file: warnings.txt"

sudo chmod 755 warnings.txt

#execute suggestions.  sudo ./suggestions.sh
echo "Generating suggestions"
echo ""
echo "suggestions are: "
echo ""

sudo cat /var/log/lynis-report.dat | grep suggestion | sed -e "s/suggestion\[\]\=//g"

sudo cat /var/log/lynis-report.dat | grep suggestion | sed -e "s/suggestion\[\]\=//g" | cat > suggestions.txt

echo ""
echo "suggestions generated"
echo "output file: suggestions.txt"

sudo chmod 755 suggestions.txt

# execute packages. sudo ./packages.sh
echo "Generating packages"
echo ""
echo "packages are: "
echo ""

sudo cat /var/log/lynis-report.dat | grep installed_package | sed -e "s/installed_package\[\]\=//g"
sudo cat /var/log/lynis-report.dat | grep installed_package | sed -e "s/installed_package\[\]\=//g" | cat > packages.txt

echo ""
echo "packages generated"
sudo chmod 755 packages.txt

# execute shells.  sudo ./shells.sh
echo "Generating available shells"
echo ""
echo "shells are: "
echo ""

sudo cat /var/log/lynis-report.dat | grep available_shell | sed -e "s/available_shell\[\]\=//g"
sudo cat /var/log/lynis-report.dat | grep available_shell | sed -e "s/available_shell\[\]\=//g" | cat > shells.txt

echo ""
echo "shells generated"

echo "output file: shells.txt"

sudo chmod 755 shells.txt
```

**Python 脚本:**

## 蟒蛇 3

```py
# importing libraries
import pandas as pd
from pandas import ExcelWriter
import os

# function to get the data.
def get_data():

    warnings = open('warnings.txt', 'r')
    suggestions = open('suggestions.txt', 'r')
    packages = open('packages.txt', 'r')
    shells = open('shells.txt', 'r')

    warn_data = warnings.readlines()
    sugg_data = suggestions.readlines()
    pack_data = packages.read()
    shell_data = shells.readlines()

    return warn_data, sugg_data, pack_data, shell_data

def clean_data():

    warn, sugg, pack, shell = get_data()

    warn_clean = []
    for line in warn:
        warn_clean.append(line.split('|'))

    for i in range(len(warn_clean)):
        warn_clean[i] = warn_clean[i][:2]
        # print(warn_clean[i])

    sugg_clean = []   
    for line in sugg:
        sugg_clean.append(line.split('|'))

    for i in range(len(sugg_clean)):
        sugg_clean[i] = sugg_clean[i][:2]
        # print(sugg_clean[i])

    pack_clean = []
    pack = pack.split('|')
    pack_clean = pack
    del pack_clean[0]

    shell_clean = []

    for i in range(len(shell)):
        shell_clean.append(shell[i].rstrip('\n'))
        # print(shell_clean[i])

    return warn_clean, sugg_clean, pack_clean, shell_clean

def convert_to_excel():

    warnings, suggestions, packages, shells = clean_data()

    try:
        os.mkdir('outputs')
    except(Exception):
        pass

    os.chdir('outputs')

    warn_packages = []
    warn_text = []
    for i in range(len(warnings)):
        warn_packages.append(warnings[i][0])

    for i in range(len(warnings)):
        warn_text.append(warnings[i][1])

    print(warn_packages, warn_text)

    warn = pd.DataFrame()

    warn['Packages'] = warn_packages
    warn['warnings'] = warn_text

    # warn.to_excel('warnings.xlsx', index = False)

    writer = ExcelWriter('warnings.xlsx')

    warn.to_excel(writer, 'report1', index = False)

    workbook = writer.book
    worksheet = writer.sheets['report1']

    # Account info columns
    worksheet.set_column('A:A', 15)
    # State column
    worksheet.set_column('B:B', 45)
    # Post code
    # worksheet.set_column('F:F', 10)

    writer.save()

    sugg_packages = []
    sugg_text = []
    for i in range(len(suggestions)):
        sugg_packages.append(suggestions[i][0])

    for i in range(len(suggestions)):
        sugg_text.append(suggestions[i][1])

    # print(sugg_packages, sugg_text)

    sugg = pd.DataFrame()

    sugg['Packages'] = sugg_packages
    sugg['suggestions'] = sugg_text

    writer1 = ExcelWriter('suggestions.xlsx')

    sugg.to_excel(writer1, 'report2', index = False)

    workbook = writer1.book
    worksheet = writer1.sheets['report2']

    # Account info columns
    worksheet.set_column('A:A', 25)
    # State column
    worksheet.set_column('B:B', 120)
    # Post code
    # worksheet.set_column('F:F', 10)
    writer1.save()

    pack_data = pd.DataFrame()
    pack_data['Packages'] = packages
    writer1 = ExcelWriter('packages.xlsx')

    pack_data.to_excel(writer1, 'report3', index = False)

    workbook = writer1.book
    worksheet = writer1.sheets['report3']

    # Account info columns
    worksheet.set_column('A:A', 75)
    # State column
    # Post code
    # worksheet.set_column('F:F', 10)
    writer1.save()

    os.chdir('..')

if __name__ == '__main__':

    warnings, suggestions, packages, shells = clean_data()

    convert_to_excel()
```

运行上述脚本后，您将在当前目录中找到一个名为 outputs 的文件夹。导航到 outputs 文件夹，您将在其中找到包含警告、建议和已安装软件包的 excel 工作表。