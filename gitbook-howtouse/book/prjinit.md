# 目录初始化

当```SUMMARY.md```创建完毕之后，我们可以使用Gitbook的命令行工具将这个目目录结构生成相应地目录及文件

```bash
$ gitbook init

$ ls
README.md    SUMMARY.md    book    end    howtouse    output    publish

$tree
.
├── LICENSE
├── README.md
├── SUMMARY.md
├── book
│   ├── README.md
│   ├── file.md
│   └── prjinit.md
├── howtouse
│   ├── Nodejsinstall.md
│   ├── README.md
│   ├── gitbookcli.md
│   └── gitbookinstall.md
├── output
│   ├── README.md
│   ├── outfile.md
│   └── pdfandebook.md
└── publish
    ├── README.md
    └── gitpages.md
```

我们可以看到，gitbook给我们生成了与```SUMMARY.md```所对应的目录及文件。

每个目录中，都有一个```README.md```文件，用于描述这一章的说明。
