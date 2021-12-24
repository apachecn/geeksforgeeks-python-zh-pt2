# 用 Python 音译非 ASCII 字符

> 原文:[https://www . geesforgeks . org/音译-非 ascii-字符-带-python/](https://www.geeksforgeeks.org/transliterating-non-ascii-characters-with-python/)

音译是用其他语言中发音相似的字母书写一种语言单词的过程。它处理其他语言中单词的发音。同样，在计算机语言中，计算机可以处理 ASCII 字符，但对非 ASCII 字符有问题。有时我们无法跳过非 ASCII 字符，因为这可能会导致信息丢失。应该有一种方法来读取非 ASCII 字符，并用 ASCII 字符中的文本来表示它们。

**方法 1:**

这种方法与内置库*统一代码*有关。这个库有助于在 Python 中音译非 ASCII 字符。它提供了一个 u *nidecode()* 方法，该方法采用 Unicode 数据，并试图用 ASCII 表示它。此方法自动确定脚本语言并相应地音译它。它接受 unicode 字符串值，并返回字符串格式的音译。

**步骤:**

*   导入 *unidecode* 库
*   用输入文本调用 *unidecode()* 方法

**示例:**

## 蟒蛇 3

```py
# Import unidecode module from unidecode
from unidecode import unidecode

# Get transliteration for following
# non-ASCII text (Unicode string)
print(unidecode(u'ko\u017eu\u0161\u010dek'))

# Get transliteration for following
# non-ASCII text (Devanagari)
print(unidecode("आप नीचे अपनी भाषा और इनपुट उपकरण चुनें और लिखना आरंभ करें"))

# Get transliteration for following
# non-ASCII text (Chinese)
print(unidecode("谢谢你"))

# Get transliteration for following
# non-ASCII text (Japanese)
print(unidecode("ありがとう。"))

# Get transliteration for following
# non-ASCII text (Russian)
print(unidecode("улыбаться Владимир Путин"))
```

**输出:**

```py
kozuscek
aap niice apnii bhaassaa aur inputt upkrnn cuneN aur likhnaa aarNbh kreN
Xie Xie Ni
arigatou.
ulybat'sia Vladimir Putin
```

**方法 2:**

这种方法处理建立一个有助于音译的结构。在这种情况下，非 ASCII 字符的 Unicode 值用相关的 ASCII 值标记，从[开始，这里](https://www.unicode.org/charts/)提供了一个脚本列表。每个脚本中的字母的 Unicode 值是用可表示的 ASCII 字符提供的。维基百科还收集了 Unicode 值和相应的音译。

**步骤:**

*   创建以 Unicode 值作为关键字，以 ASCII 表示作为值的字典
*   用那本字典音译文中的每个字母。

例如，如果我们想要俄语的音译，我们将采用西里尔文字的所有字母，因为俄语使用西里尔字母。然后，对于每个字母，使用其 Unicode 值和 ASCII 表示来创建字典。然后，这个字典被用来音译给定的文本。

例如，取天成文书的一些字母，创建一个字典。此外，它用于小文本的音译。

**示例:**

## 计算机编程语言

```py
# Create devanagari transliteration dictionary
devanagari_translit_dict = {
    '\u0905': 'A', '\u0906': 'AA', '\u0907': 'I', '\u0908': 'II',
    '\u0909': 'U', '\u090A': 'UU', '\u090F': 'E', '\u0910': 'AI',
    '\u0913': 'O', '\u0914': 'AU', '\u0915': 'K', '\u0916': 'KH',
    '\u0917': 'G', '\u0918': 'GH', '\u0919': 'NG', '\u091A': 'C',
    '\u091B': 'CH', '\u091C': 'J', '\u091D': 'JH', '\u091E': 'NY',
    '\u091F': 'TT', '\u0920': 'TTH', '\u0921': 'DD', '\u0922': 'DDH',
    '\u0923': 'NN', '\u0924': 'T', '\u0925': 'TH', '\u0926': 'D',
    '\u0927': 'DH', '\u0928': 'N', '\u092A': 'P', '\u092B': 'PH',
    '\u092C': 'B', '\u092D': 'BH', '\u092E': 'M', '\u092F': 'Y',
    '\u0930': 'R', '\u0932': 'L', '\u0933': 'LL', '\u0935': 'V',
    '\u0936': 'SH', '\u0937': 'SS', '\u0938': 'S', '\u0939': 'H',
    '\u093E': 'AA', '\u093F': 'I', '\u0940': 'II', '\u0941': 'U',
    '\u0942': 'UU', '\u0947': 'E', '\u0948': 'AI', '\u094B': 'O',
    '\u094C': 'AU', '\u094D': '', '\u0902': 'n'}

# Define function transliterating text
def transliterate(text, translit_dict):
    new_word = ''
    for letter in text:
        new_letter = ''
        if letter in translit_dict:
            new_letter = translit_dict[letter]
        else:
            new_letter = letter
        new_word += new_letter
    return new_word

# Input text in devanagari
text = "आप नीचे अपनी भाषा और इनपुट उपकरण चुनें और लिखना आरंभ करें"

# Obtain Transliterated text for given input text
transliterated_text = transliterate(text, devanagari_translit_dict)
print(transliterated_text)
```

**输出:**

```py
AAP NIICE APNII BHAASSAA AUR INPUTT UPKRNN CUNEn AUR LIKHNAA AARnBH KREn
```