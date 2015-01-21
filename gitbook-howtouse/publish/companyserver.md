# 发布到公司文档服务器

我写了一个简单地脚本，基本原理如下：

```bash
#!/bin/sh

git pull

# get real path
cd `echo ${0%/*}`
abspath=`pwd`

#清除之前生成的文件
rm -rf $abspath/build


PROJECT='gitbook-howtouse'

sync(){
    echo "sync $PROJECT document to gitbook server"
    SyncServer="rsync://doc.dq.in/rsync"
    Sync="rsync -avu --port=30873 --delete  --exclude '*.sh' --progress $abspath/build/$PROJECT $SyncServer/PATH/"
    echo $Sync
    eval $Sync
}

build(){
    echo "build $PROJECT document"

    OUTPUT="./build/$PROJECT"

    gitbook init

    rm  -rf $OUTPUT
    gitbook build . --output=$OUTPUT
    sync
}

build
```

这样就可以直接访问下面的地址来在公司的服务器上查看这本[Gitbook使用入门](http://doc.dq.in/gitbook-howtouse/index.html)了
