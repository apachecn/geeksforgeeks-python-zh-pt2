# 生物节律模块中的序列

> 原文:[https://www.geeksforgeeks.org/sequence-in-biopython-module/](https://www.geeksforgeeks.org/sequence-in-biopython-module/)

**先决条件:** [生物机器人模块](https://www.geeksforgeeks.org/introduction-to-biopython/)

序列基本上是一系列特殊的字母，用来代表生物体的蛋白质、脱氧核糖核酸或核糖核酸。*生物节律*中的序列通常由*生物中描述的*序列*对象处理。Seq* 模块。 *Seq* 对象有补码、*反向补码*、*转录*、*反向转录*和*翻译*等内置功能。*序列* 对象有许多字符串方法，如*计数()、查找()、拆分()、剥离()*等。

以下是 Biopython 中的一些序列示例:

**例 1:**

## 蟒 3

```py
# Import libraries
from Bio.Seq import Seq

# Creating a sequence
seq = Seq("GACT")

# Printing Sequence
print(seq)
```

**输出:**

```py
GACT

```

在上面的例子中，序列 *GACT，*每个字母代表甘氨酸、丙氨酸、半胱氨酸和苏氨酸。每个 Seq 对象都有两个重要属性:

1.  Data, which is the actual sequence string ( *gact 【T5】 in this example).*
2.  Alphabet, used to indicate the type of sequence, i.e. DNA sequence, RNA sequence, etc. It is universal in nature and does not represent any sequence by default.

**例 2:**

## 蟒 3

```py
# Import libraries
from Bio.Seq import Seq

# Creating a sequence
seq = Seq("ACGT=TT")

# Updating sequence
updatedSeq = my_dna.ungap("=")

# Printing Sequence
print(updatedSeq)
```

**输出:**

```py
ACGTT

```

这里，序列 *ACGT，*每个字母代表腺嘌呤、胞嘧啶、鸟嘌呤和胸腺嘧啶。 *=TT* 指各种蛋白质命名惯例和功能。

### 字母表类别:

除了字符串属性之外， *Seq* 对象还拥有字母表属性，这些属性是来自*生物的*字母表*类的实例。字母表*模块，例如 IUPAC 脱氧核糖核酸或通用脱氧核糖核酸描述了分子的类型，即脱氧核糖核酸、核糖核酸、蛋白质，或者它也可以指示预期的符号。

Alphabet 模块提供以下类来表示各种序列:

<figure class="table">

| **级** | **属性** |
| --- | --- |
| 单字母字母表 | 大小为一个字母的通用字母表是从字母表中派生出来的，所有其他字母表类型都是由此派生出来的。 |
| 蛋白质字母表 | 通用单字母蛋白质字母表 |
| 核苷酸字母表 | 通用单字母核苷酸字母表 |
| 脱氧核糖核酸字母表 | 通用单字母 DNA 字母表。 |
| RNAAlphabet | 通用单字母 RNA alphabet。 |
| 二级结构 | 字母表用来描述二级结构。 |
| 三字母蛋白质 | 三字母蛋白质字母表。 |
| 【alphabet encoder】 | 类用于从现有字母表构建新的扩展字母表。 |
| 带间隙的 | 包含间隙字符的字母。含有停止符号的字母。 |

</figure>

*生物。Alphabet* 还提供了一个 *IUPAC* 模块，它给出了 IUPAC 社区定义的序列类型。IUPAC 模块中的一些类如下所示:

<figure class="table">

| **名称** | **级** | **性状** |
| --- | --- | --- |
| IUPAC 蛋白 | 蛋白 | IUPAC 蛋白 20 个标准氨基酸的字母表。 |
| ExtendedIUPACProtein | Extended _ protein | Extended 大写 IUPAC 蛋白单字母字母表。 |
| IUPACAmbiguousDNA | 歧义 _dna | 大写 IUPAC 歧义 DNA。 |
| IUPACUnambiguousDNA | 不含糊 _dna | 大写 IUPAC 不含糊 DNA (GATC)。 |
| ExtendedIUPACDNA | Extended _ DNA | Extended IUPAC DNA 字母表。 |
| IUPAC ambiguousrna | 暧昧 _rna | 大写 IUPAC 暧昧 RNA。 |
| IUPACUnambiguousRNA | 不含糊 _rna | 大写 IUPAC 不含糊 RNA (GAUC)。 |

</figure>

*生物。字母表*从*生物神话*中删除。字母表对象的预期功能从未被很好地建立，并且已经存在了 20 年的风格有缺点。特别是*字母编码器*类过于复杂，很难决定分子的类型。几个字母对象的一致性(例如在字符串添加过程中)通常是困难的。

没有一个具体的计划如何加强或取代目前的结构，决定完全废除 *Bio。Aplphabet* 模块。