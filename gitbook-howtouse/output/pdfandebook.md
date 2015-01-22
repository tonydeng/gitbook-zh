# 输出PDF

输出为PDF文件，需要先安装```gitbook pdf```

```bash
$ npm install gitbook-pdf -g
```

> 如果在安装gitbook-pdf时，觉得下载```phantomjs```包太慢的话，你可以到```phantomjs```的官方网站上去下载。

> http://phantomjs.org/

> 这个包的安装方式，参考其官网的说明文档。

然后，用下面的命令就可以生成PDF文件了。

```bash
$ gitbook pdf {book_name}
```

如果，你已经在编写的gitbook当前目录，也可以使用相对路径。

```bash
$ gitbook pdf .
```

然后，你就会发现，你的目录中多了一个名为```book.pdf```的文件。

