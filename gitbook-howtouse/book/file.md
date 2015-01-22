# README.md 与 SUMMARY编写

## 使用语法

在Gitbook中所有文字的编写都使用```Markdown```语法。

## README.md

这个文件相对于是一本Gitbook的简介，比如我们这本书的```README.md``` :

```
# Gitbook 使用入门


> GitBook 是一个基于 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 来制作精美的电子书。

本书将简单介绍如何安装、编写、生成、发布一本在线图书。
```

## SUMMARY.md

这个文件相对于是一本书的目录结构。比如我们这本书的```SUMMARY.md``` :


```
# Summary

* [Introduction](README.md)
* [基本安装](howtouse/README.md)
   * [Node.js安装](howtouse/nodejsinstall.md)
   * [Gitbook安装](howtouse/gitbookinstall.md)
   * [Gitbook命令行速览](howtouse/gitbookcli.md)
* [图书项目结构](book/README.md)
   * [README.md 与 SUMMARY编写](book/file.md)
   * [目录初始化](book/prjinit.md)
* [图书输出](output/README.md)
   * [输出为静态网站](output/outfile.md)
   * [输出PDF](output/pdfandebook.md)
* [发布](publish/README.md)
   * [发布到Github Pages](publish/gitpages.md)
* [结束](end/README.md)
```

```SUMMARY.md```基本上是列表加链接的语法。链接中可以使用目录，也可以使用。
