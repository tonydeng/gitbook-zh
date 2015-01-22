# 发布到Github Pages

## 将静态网站直接发布到Github Pages

可以将编写好的.md文件通过Gitbook处理成静态网站，然后发布到[Github Pages](https://pages.github.com/)上。

我的[Github Pages](http://tonydeng.github.io)是使用Octopress来进行构建的，于是就写了一个简单的脚本，将生成好的Gitbook直接同步到我的octopress项目中。

```bash
#!/bin/sh

Usage(){
    echo "welcome use front-end release script
    -----------------------------------------
    use it require input your deploy target
           gook luck!
    author:
        wolf.deng@gmail.com
    -----------------------------------------
    Usage:

    # 发布github.io
    ./deploy.sh github.io
    "
}

die( ){
    echo
    echo "$*"
    Usage
    echo
    exit 1
}

git pull

# get real path
cd `echo ${0%/*}`
abspath=`pwd`

#清除之前生成的文件
rm -rf $abspath/build

TARGET=$1
PROJECT='gitbook-howtouse'


sync( ){
    case $* in
        "github.io" )
            echo "sync $PROJECT gitbook website to $TARGET"
            GITHUB_PROJECT="~/workspace/github/tonydeng.github.io/source/gitbook-zh"
            Sync="rsync -avu --delete --exclude '*.sh' --exclude '.git*' --exclude '.DS_Store' $abspath/build/$PROJECT $GITHUB_PROJECT"
            echo $Sync
            eval $Sync

            cd $GITHUB_PROJECT
            rake generate
            rake deploy
        ;;

    esac
}

build(){
    echo "build $PROJECT document"

    OUTPUT="./build/$PROJECT"

    gitbook init

    rm  -rf $OUTPUT
    gitbook build . --output=$OUTPUT
}

blog(){
    echo "build & sync $PROJECT to github.io"
    build
    sync $TARGET
}

# 判断执行参数，调用指定方法
case $TARGET in
    github.io )
       blog
        ;;
    * )
        die "parameters is no reght!"
        ;;
esac
```

这样就可以直接调用脚本来将写好的Gitbook发布到我的[Github Pages](http://tonydeng.github.io)服务了。

这样其他人就可以通过下面的链接来查看这本[Gitbook使用入门](http://tonydeng.github.io/gitbook-zh/gitbook-howtouse/)了。

> http://tonydeng.github.io/gitbook-zh/gitbook-howtouse/

