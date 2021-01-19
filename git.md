# Git

## Git 是个好东西~

* 问题：在弱网络情况下，有一个 repo 特别大， clone 的时候老失败怎么办？

![answer](./pics/git-20210119.png)

解释一下：

depth 用来指定克隆的深度，这个深度指的是 commit 次数，这里 ```--depth 1``` 意思是只克隆最后一次 commit 的内容，这样需要克隆的项目就会小很多

```git fetch --unshallow``` 表示拉取完整项目
这样操作就可以保证在弱网络条件下拉取大型项目

* 问题：克隆项目的时候如何设置代理？

1，全局代理

http 代理

```git config --global http.proxy http://127.0.0.1:1080```

```git config --global https.proxy http://127.0.0.1:1080```

socks 代理

```git config --global http.proxy socks5://127.0.0.1:1080```

```git config --global https.proxy socks5://127.0.0.1:1080```

2，对某一个域名设置代理

http 代理

```git config --global http.https://github.com.proxy http://127.0.0.1:1080```

```git config --global https.https://github.com.proxy http://127.0.0.1:1080```

socks 代理

```git config --global http.https://github.com.proxy socks5://127.0.0.1:1080```

```git config --global https.https://github.com.proxy socks5://127.0.0.1:1080```

假设本地代理的地址是 ```http://127.0.0.1:1080```

3，清除代理

```git config --global --unset http.proxy```

```git config --global --unset https.proxy```

其实也可以去 ```~/.gitconfig``` 文件里去看，删掉有关 proxy 的行就行了~