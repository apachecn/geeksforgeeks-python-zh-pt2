# Python 字符串编码()方法

> 原文:[https://www.geeksforgeeks.org/python-strings-encode-method/](https://www.geeksforgeeks.org/python-strings-encode-method/)

在当今世界，安全性在许多应用程序中都至关重要。因此，需要在数据库中安全存储密码，因此需要保存字符串的编码版本。为了实现这一点，python 在其语言中定义了“ **encode()** ”，用指定的编码方案对字符串进行编码。语言中定义了几种编码方案。Python 字符串 **encode()** 方法使用指定的编码对字符串进行编码。如果没有指定编码，将使用 UTF-8。

> **语法:**
> 
> 编码(编码，错误)
> 
> **参数:**
> 
> *   **编码:**指定必须执行编码的编码。
> *   **错误:**决定发生错误时如何处理，例如“严格”在出现异常时引发 Unicode 错误，“忽略”忽略发生的错误。有六种类型的错误响应
>     *   严格–默认响应，失败时会引发 UnicodeDecodeError 异常
>     *   忽略–忽略结果中不可忽略的 unicode
>     *   replace–将不可编码的 unicode 替换为问号？
>     *   xmlcharfreplace–插入 XML 字符引用，而不是不可编码的 unicode
>     *   backlashread–插入\ uNNNN 转义序列，而不是不可编码的 unicode
>     *   name replace–插入一个\N{…}转义序列，而不是不可编码的 unicode
> 
> **返回:**
> 
> 返回编码形式的字符串

### **示例 1:** 打印可用编码方案的代码

## 蟒蛇 3

```
# Python3 code to print
# all encodings available

from encodings.aliases import aliases

# Printing list available
print("The available encodings are : ")
print(aliases.keys())
```

**输出:**

```
The available encodings are : 
dict_keys(['ibm039', 'iso_ir_226', '1140', 'iso_ir_110', '1252', 'iso_8859_8', 'iso_8859_3', 'iso_ir_166', 'cp367', 'uu', 'quotedprintable', 'ibm775', 'iso_8859_16_2001', 'ebcdic_cp_ch', 'gb2312_1980', 'ibm852', 'uhc', 'macgreek', '850', 'iso2022jp_2', 'hz_gb_2312', 'elot_928', 'iso8859_1', 'eucjp', 'iso_ir_199', 'ibm865', 'cspc862latinhebrew', '863', 'iso_8859_5', 'latin4', 'windows_1253', 'csisolatingreek', 'latin5', '855', 'windows_1256', 'rot13', 'ms1361', 'windows_1254', 'ibm863', 'iso_8859_14_1998', 'utf8_ucs2', '500', 'iso8859', '775', 'l7', 'l2', 'gb18030_2000', 'l9', 'utf_32be', 'iso_ir_100', 'iso_8859_4', 'iso_ir_157', 'csibm857', 'shiftjis2004', 'iso2022jp_1', 'iso_8859_2_1987', 'cyrillic', 'ibm861', 'ms950', 'ibm437', '866', 'csibm863', '932', 'iso_8859_14', 'cskoi8r', 'csptcp154', '852', 'maclatin2', 'sjis', 'korean', '865', 'u32', 'csshiftjis', 'dbcs', 'csibm037', 'csibm1026', 'bz2', 'quopri', '860', '1255', '861', 'iso_ir_127', 'iso_celtic', 'chinese', 'l8', '1258', 'u_jis', 'cspc850multilingual', 'iso_2022_jp_2', 'greek8', 'csibm861', '646', 'unicode_1_1_utf_7', 'ibm862', 'latin2', 'ecma_118', 'csisolatinarabic', 'zlib', 'iso2022jp_3', 'ksx1001', '858', 'hkscs', 'shiftjisx0213', 'base64', 'ibm857', 'maccentraleurope', 'latin7', 'ruscii', 'cp_is', 'iso_ir_101', 'us_ascii', 'hebrew', 'ansi_x3.4_1986', 'csiso2022jp', 'iso_8859_15', 'ibm860', 'ebcdic_cp_us', 'x_mac_simp_chinese', 'csibm855', '1250', 'maciceland', 'iso_ir_148', 'iso2022jp', 'u16', 'u7', 's_jisx0213', 'iso_8859_6_1987', 'csisolatinhebrew', 'csibm424', 'quoted_printable', 'utf_16le', 'tis260', 'utf', 'x_mac_trad_chinese', '1256', 'cp866u', 'jisx0213', 'csiso58gb231280', 'windows_1250', 'cp1361', 'kz_1048', 'asmo_708', 'utf_16be', 'ecma_114', 'eucjis2004', 'x_mac_japanese', 'utf8', 'iso_ir_6', 'cp_gr', '037', 'big5_tw', 'eucgb2312_cn', 'iso_2022_jp_3', 'euc_cn', 'iso_8859_13', 'iso_8859_5_1988', 'maccyrillic', 'ks_c_5601_1987', 'greek', 'ibm869', 'roman8', 'csibm500', 'ujis', 'arabic', 'strk1048_2002', '424', 'iso_8859_11_2001', 'l5', 'iso_646.irv_1991', '869', 'ibm855', 'eucjisx0213', 'latin1', 'csibm866', 'ibm864', 'big5_hkscs', 'sjis_2004', 'us', 'iso_8859_7', 'macturkish', 'iso_2022_jp_2004', '437', 'windows_1255', 's_jis_2004', 's_jis', '1257', 'ebcdic_cp_wt', 'iso2022jp_2004', 'ms949', 'utf32', 'shiftjis', 'latin', 'windows_1251', '1125', 'ks_x_1001', 'iso_8859_10_1992', 'mskanji', 'cyrillic_asian', 'ibm273', 'tis620', '1026', 'csiso2022kr', 'cspc775baltic', 'iso_ir_58', 'latin8', 'ibm424', 'iso_ir_126', 'ansi_x3.4_1968', 'windows_1257', 'windows_1252', '949', 'base_64', 'ms936', 'csisolatin2', 'utf7', 'iso646_us', 'macroman', '1253', '862', 'iso_8859_1_1987', 'csibm860', 'gb2312_80', 'latin10', 'ksc5601', 'iso_8859_10', 'utf8_ucs4', 'csisolatin4', 'ebcdic_cp_be', 'iso_8859_1', 'hzgb', 'ansi_x3_4_1968', 'ks_c_5601', 'l3', 'cspc8codepage437', 'iso_8859_7_1987', '8859', 'ibm500', 'ibm1026', 'iso_8859_6', 'csibm865', 'ibm866', 'windows_1258', 'iso_ir_138', 'l4', 'utf_32le', 'iso_8859_11', 'thai', '864', 'euc_jis2004', 'cp936', '1251', 'zip', 'unicodebigunmarked', 'csHPRoman8', 'csibm858', 'utf16', '936', 'ibm037', 'iso_8859_8_1988', '857', 'csibm869', 'ebcdic_cp_he', 'cp819', 'euccn', 'iso_8859_2', 'ms932', 'iso_2022_jp_1', 'iso_2022_kr', 'csisolatin6', 'iso_2022_jp', 'x_mac_korean', 'latin3', 'csbig5', 'hz_gb', 'csascii', 'u8', 'csisolatin5', 'csisolatincyrillic', 'ms_kanji', 'cspcp852', 'rk1048', 'iso2022jp_ext', 'csibm273', 'iso_2022_jp_ext', 'ibm858', 'ibm850', 'sjisx0213', 'tis_620_2529_1', 'l10', 'iso_ir_109', 'ibm1125', '1254', 'euckr', 'tis_620_0', 'l1', 'ibm819', 'iso2022kr', 'ibm367', '950', 'r8', 'hex', 'cp154', 'tis_620_2529_0', 'iso_8859_16', 'pt154', 'ebcdic_cp_ca', 'ibm1140', 'l6', 'csibm864', 'csisolatin1', 'csisolatin3', 'latin6', 'iso_8859_9_1989', 'iso_8859_3_1988', 'unicodelittleunmarked', 'macintosh', '273', 'latin9', 'iso_8859_4_1988', 'iso_8859_9', 'ebcdic_cp_nl', 'iso_ir_144'])
```

### **示例 2:** 编码字符串的代码

## 蟒蛇 3

```
# Python code to demonstrate
# encode()

# initializing string
str = "geeksforgeeks"

# printing the encoded string
print ("The encoded string in utf8 format is : ",)
print (str.encode('utf8', 'ignore'))
```

**输出:**

```
The encoded string in utf8 format is : 
b'geeksforgeeks'
```

### 示例 3:使用错误参数编码

## 蟒蛇 3

```
# unicode string
string = 'GeeksforGeeks'

# print string
print('The string is:', string)

# ignore error
print(string.encode("ascii", "ignore"))

# replace error
print(string.encode("ascii", "replace"))
```

**输出:**

```
The string is: GeeksforGeeks
b'GeeksforGeeks'
b'GeeksforGeeks'
```