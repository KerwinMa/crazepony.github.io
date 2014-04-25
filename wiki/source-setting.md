---
layout: wiki
title: 源代码的基本配置
---

# {{ page.title }}

关于文件编码
=============
文件必须使用utf-8编码。如果使用其它的编码，例如中文中常见的gdb格式，会导致中文乱码，或者网页无法生成的问题。


关于行结束符问题
=============
在Linux/Windows/MacOs下，行结束符不一样。这样在多个平台之间进行协作开发时，在checkin和checkout之后，会导致很多行结束符不同意引起的问题。

添加.gitattribute文件，可以解决行结束符在多个平台下不一致的问题。

现在使用的.gitattribute配置为：

* 代码库中都为LF，也就是checkin的时候，会把所有文件的行结束符转化为LF；
* 工作路径下为所在OS的行结束符，也就是在checkout的时候，git回自动根据当前的OS将文件的行结束符做转化；
* 对于图片，jar库，和so文件等二进制文件，不进行上面的转化；