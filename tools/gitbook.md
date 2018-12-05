
GitBook 是一个基于 Node.js 的命令行工具，可使用 Github/Git 和 Markdown 来制作精美的电子书。

* Git 对电子书进行版本控制
* Markdown 提供编辑文件的格式
* GitBook 美化文本内容，并提供友好访问
    * GitBook 渲染 Markdown 文本格式
    * 众多的 [GitBook Plugins](https://plugins.gitbook.com/) 美化文本内容
    * 搭建文档网站友好访问文本
    * 合成一本电子书（pdf，epub，mobi）

# GitBook 安装

GitBook 是 Node.js 的一个模块，Node.js 模块可以被打包，并发布到 npm 官网上提供随时随地下载安装。在安装 Node.js 的时候，会集成 npm 包管理器的安装，即：

* Node.js 是 GitBook 的运行环境
* npm 是 Node.js 模块的管理工具

在安装 GitBook 之前首先需要安装 Node.js，可以从[官网](https://nodejs.org/en/)下载 LST 版本，然后通过 npm 工具安装 GitBook 。
    
    tar -xvf node-v10.14.0-linux-x64.tar.xz -C /opt/
    
    cat >> ~/.bashrc << \EOF

    NODE_BIN=/opt/node-v10.14.0-linux-x64/bin

    PATH=$NODE_BIN:$PATH
    EOF
    
    source ~/.bashrc
    npm install gitbook -g

# GitBook 创建书籍

GitBook 通过文件来管理书籍，即：书籍的每个章节对应一个文件。创建 mybook 文件夹管理所有文件，在开始写作之前执行以下命令：

    gitbook init
    
执行完后，在当前文件夹下会生成两个文件：README.md、SUMMARY.md。SUMMARY.md 文件配置书籍的目录结构，当前文件夹为起始地址，文件的路径对应目录的结构。例：README.md 对应目录 Introduction。

# GitBook 配置书籍

GitBook 使用 book.json 文件来配置书籍的信息：

* 书籍的名称
* 书籍的作者
* 使用的语言
* 自定义样式
* 使用的 plugins，及其配置信息

```json
{
    "title": "HELLO",
    "language": "zh-hans",
    "author": "xzdbing",
    "plugins": [
        "anchor-navigation-ex-toc",
        "code",
        "expandable-chapters-small",
        "github",
        "sectionx",
        "splitter"
    ],
    "pluginsConfig": {
        "anchor-navigation-ex-toc": {
            "showLevel": false
        },
        "code": {
            "copyButtons": true
        },
        "github": {
            "url": "https://github.com/xyz18"
        },
        "sectionx": {
            "tag": "b"
        }
    }
}
```

如果配置 plugins 字段，需要执行以下命令下载 GitBook Plugins：

    gitbook install

plugins 详细描述：

* anchor-navigation-ex-toc：页面内生成导航目录
* code: 代码块格式显示
* expandable-chapters-small：左侧章节目录折叠
* github：添加 GitHub 图标
* sectionx：页面分块显示
* splitter：左侧边栏宽度自由调节

# GitBook 浏览书籍

执行以下命令生成静态网页并运行服务器通过 `localhost:4000` 浏览当前书籍：

    gitbook serve

如果你有第二本书籍需要通过浏览器访问，执行以下命令通过 4001 端口访问 `localhost:4001`：

    gitbook serve --lrport 35288 --port 4001
    
