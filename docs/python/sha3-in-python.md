# Python 中的 SHA3

> 原文:[https://www.geeksforgeeks.org/sha3-in-python/](https://www.geeksforgeeks.org/sha3-in-python/)

一种**加密散列函数**是一类特殊的散列函数，它具有某些特性，使其适用于密码学。这是一种数字算法，它将自我主张大小的信息映射到固定大小的一条线(哈希函数)，该函数同样是单向输出函数，即不可恢复的函数。

## hashlib 模块

为了计算 Python 中的加密哈希值，使用了“hashlib”模块。 *hashlib* 给出以下加密散列函数来发现文本的散列输出，如下所示:

*   sha3 _ 224–28 位摘要大小
*   sha3 _ 256–32 位摘要大小
*   sha3 _ 384–48 位摘要大小
*   sha3 _ 512–64 位摘要大小

该模块实现了各种安全散列和消息摘要计算的典型接口。包括 FIPS 安全哈希计算 SHA1、SHA224、SHA256、SHA384 和 SHA512，就像 RSA 的 MD5 计算一样(在互联网 RFC 1321 中进行了描述)。早期的计算被称为消息摘要，但今天它是安全散列。

Python 通过库模块 *hashlib* 为哈希代码计算提供了丰富的帮助。您可以使用“hashlib.algorithms_available”来获得您的 Python 变体中所有可访问的散列计算的概要。

Hashlib 提供以下常量属性:

*   “hashlib . algorithms _ guaranteed”——一个包含所有哈希算法的集合，保证该模块在所有平台上都支持这些算法。
*   “hashlib . algorithms _ available”——包含解释器中当前可用的所有哈希算法名称的集合。

## 蟒蛇 3

```py
import hashlib

print(hashlib.algorithms_guaranteed)
print(hashlib.algorithms_available)
```

**输出:**

> {'blake2b '，' shake_256 '，' sha512 '，' sha3_224 '，' sha384 '，' sha3_512 '，' sha3_256 '，' sha3_384 '，' md5 '，' sha256 '，' sha224 '，' sha1 '，' blake2s '，' shake_128'}
> 
> {'sha512 '，' md5 '，' blake2s '，' SHA512 '，' DSA-SHA '，' whirlpool '，' sha224 '，' sha3_256 '，' blake2b '，' MD5 '，' SHA256 '，' ecdsa-with-SHA1 '，' dsaWithSHA '，' sha384 '，' sha3_384 '，' md4 '，' sha3_512 '，' sha256 '，' RIPEMD160 '，' shake_256 '，' SHA '，' SHA '，' sha3_224 '，'

### 常量属性

*   **hash.digest_size:** 后续哈希的大小，以字节为单位。
*   **hash.block_size:** 哈希计算的内部平方大小，以字节为单位。
*   **hash.name** :该 hash 的认可名称，始终为小写，始终适合作为 new()的边界，以生成另一个这种类型的 hash。

### hashlib 中的方法

*   **hash.update(数据):**用类似字节的对象更新 hash 对象。
*   **hash.digest():** 返回到现在为止的 update()方法的信息的浓缩。这是一个大小为 digest_size 的 bytes 对象，可以包含从 0 到 255 的字节数。
*   **hash.hexdigest():** 除了摘要之外的 Like digest()作为长度为两倍的字符串对象返回，仅包含十六进制数字。
*   **hash.copy():** 返回 hash 对象的副本(“克隆”)。这可以用来有效地描绘共享典型开始子串的信息的概观。

### SHAKE 可变长度摘要

*   **shake.digest(长度):**返回传递给 update()函数的信息的浓缩。这是一个字节大小的对象，可以包含 0 到 255 之间的所有字节。
*   **shake.hexdigest(长度):** Like overview()除了缩合之外，还作为长度为两倍的字符串对象返回，仅包含十六进制数字。

## SHA–简介

安全散列算法是由国家标准和技术研究所(NIST)提出的一组加密散列函数，包括:

*   **SHA-0:** 应用于 1993 年产生的名为“SHA”的 160 位散列函数的第一种形式的词。由于一个未披露的“值得注意的缺陷”，它在生产后不久就被召回，取而代之的是略微大修的 SHA-1 变种。
*   **SHA-1:** 一个 160 位的散列函数，看起来像以前的 MD5。这是由国家安全局(NSA)计划的，对于数字签名算法至关重要。在 SHA-1 发现了密码方面的缺陷，而该标准在 2010 年后的大多数密码使用中都没有得到认可。
*   **SHA-2:** 一组两个比较哈希函数，具有各种块大小，被称为 SHA-256 和 SHA-512，它们在字大小上形成对比；SHA-256 使用的是 32 字节的字，而 SHA-512 使用的是 64 字节的字。
*   **SHA-3:** 一个散列函数，在过去曾被称为 *Keccak* ，在 2012 年非 NSA 原创者公开竞争后被选中。它支持与 SHA-2 相似的散列长度，其内部结构与 SHA 家族的其余部分完全不同。

## SHA-3 的实施

安全散列算法-3 又称为 Keccak，是一种单向方法，用于根据 224、256、384 或 512 条来自任何大小的输入信息的标准，创建给定长度的计算机化打印，由 Yoan Dimen 在 2008 年推动的一群创作者创建，并在 2015 年被接受为新的 FIPS 标准。计算工作的方法是将混合容量与压缩到选定大小的“加密海绵”相结合。

**示例:**

> **输入:** HelloWorld
> 
> **输出[sha3 _ 224]:**c 4797897 c 58 a 0640 df 9 C4 e9 A8 f 30570364d 9 ed 8450 c 78 ed 155278 ac0
> 
> **输入:**hello world
> T3】输出【sha3 _ 256】:92 dad 9443 E4 DD 6d 70 a7 f 11872101 ebff 87 e 21798 E4 fbb 26 fa 4 BF 590 EB 440 e71b
> T6】输入: HelloWorld
> 
> 【T3 _ 384】输出【sha 3 _ 384】:dc6104 dc2 caff 3 ce 2 ccecbc 927463 fc 3241 c 85311449 f1 B1 f 4787394 c9b3aa 55 a9 e 201 d0s 0 B1 b7f 8892 BC 127216
> 
> **输入:** HelloWorld
> 
> **输出【sha 3 _ 512】:938315 EC 7 B0 e 0 bcac 648 AE 6 f 732 f 67 e00 f9c 6 CAA 3916279534 a 0769 b 0 BBB 15474 a 429177013 e 8a 7 e 489990887 D1 e 1933687 e 2183 FD 2 b 6054 c 2 e 8828 ca 1 c**

以下程序展示了使用不同方法在 Python-3.8 中实现 SHA-3 hash:使用**更新*方法实现 *sha3_224**

## *蟒蛇 3*

```py
*import sys
import hashlib

if sys.version_info < (3, 6):
    import sha3

# initiating the "s" object to use the
# sha3_224 algorithm from the hashlib module.
s = hashlib.sha3_224()

# will output the name of the hashing algorithm currently in use.
print(s.name)

# will output the Digest-Size of the hashing algorithm being used.
print(s.digest_size)

# providing the input to the hashing algorithm.
s.update(b"GeeksforGeeks")

print(s.hexdigest())*
```

***Output**

```py
sha3_224
28
11c044e8080ed87b3cf0643bc5880a38ae62dd4562390700000b1191
```* 

*使用*编码*方法实现 *sha3_256**

## *蟒蛇 3*

```py
*# import the library module
import sys
import hashlib

if sys.version_info < (3, 6):
    import sha3

# initialize a string
str = "GeeksforGeeks"

# encode the string
encoded_str = str.encode()

# create sha3-256 hash objects
obj_sha3_256 = hashlib.sha3_256(encoded_str)

# print in hexadecimal
print("\nSHA3-256 Hash: ", obj_sha3_256.hexdigest())*
```

***输出:***

> *SHA3-256 散列:b05 a 48 e 99 c 60983 b 96 b5 a 69 efad 8bb 44 e 5866702d 484d 43 e 592 ab 639 ef 64641 ff*

*执行 *sha3_384**

## *蟒蛇 3*

```py
*# import the library module
import sys
import hashlib

if sys.version_info < (3, 6):
    import sha3

# initialize a string
str = "GeeksforGeeks"

# encode the string
encoded_str = str.encode()

# create sha3-384 hash objects
obj_sha3_384 = hashlib.sha3_384(encoded_str)

# print in hexadecimal
print("\nSHA3-384 Hash: ", obj_sha3_384.hexdigest())*
```

***输出:***

> *sha 3-384 hash:b92 ecaaafd 00472 da 6d 619 b 6810 b5f 66 7c 090 e 32 BD 4 F5 a 6b 60899 e 8 E3 e 2c 859792 EC 07 a 33775 CFC 8d 05 c 64 f 222*

*使用**新*方法实施 *sha3_512***

## **蟒蛇 3**

```py
**import sys
import hashlib

if sys.version_info < (3, 6):
    import sha3

str = "GeeksforGeeks"

# create a sha3 hash object
hash_sha3_512 = hashlib.new("sha3_512", str.encode())

print("\nSHA3-512 Hash: ", hash_sha3_512.hexdigest())**
```

****输出:****

> **sha 3-512 hash:3706 a1 96a 8fa 96 B3 fc 5 ff 30 cbca 36 ce 666042 e 2d 07762022 a78 a2 EC 824439848 fc 3695 e 83336 ab 71 f17 DDD BC 24 b 96454 df 2a 437 e 34801 a4 e 13 faab 89 e 8d 0 FDA 61**

****哈希算法的应用:****

*   **消息摘要**
*   **密码验证**
*   **数据结构(编程语言)**
*   **编译器操作**
*   **拉宾-卡普算法**
*   **将文件名和路径链接在一起**