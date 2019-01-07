
恭喜又一位同学入了程序员的坑 :)

# Python 起源简介

Python 的作者，Guido van Rossum，荷兰人。1991年，Python 发布了第一个公开发行版。

Guido 开始的设想是创造一种编程语言，能够像 C 语言那样，全面调用计算机的功能接口，又可以像 shell 那样，轻松的编程。之后 Python 的诞生，完全符合这个设想，介于 C 和 shell 之间，功能全面，易学易用，且可拓展。

发展至今，Python 已经越来越成熟。自从 2008 年，发布了 Python 3.0，Python2 每年会发布过渡版本，并仅支持到 2020 年。所以，学习 Python 可以直接入手 Python3。

# 推动 Python 的发展

第一是教育。Python 已经进入山东省小学教材，并且浙江、北京教育大省也将把 Python 编程基础纳入信息技术课程。随着国家机器的逐步推进，相信以后 Python 活的不会太差。

第二是人工智能和机器学习。随着人工智能逐步的走进人们的生活，人们对人工智能的关注度会越来越高，而人工智能和机器学习的首选语言就是 Python。

第三是创业公司。随着互联网的蓬勃发展，各式各样的公司都想做“互联网+”，而能够涉及如此广泛的领域，并且能快速搭建一套完整系统的。第一个想到的就是 Python。

第四是云计算。每一项技术的发展，能够被广泛的认可，都需要拥有一个成功的案例，而这个案例必须要有足够的说服性。OpenStack 仅次于 Linux 的开源项目，完全用 Python 开发，世界 100 强企业中近 50% 的企业采用了 OpenStack，开发者、用户遍及全球。  

# Python 如何做到能 “受到如此青睐”

首先，Python 是一种解释型语言。Python 虚拟机可以直接执行 Python 源码（其实执行前会把源码翻译成字节码），做到类似脚本的形式不需要编译直接执行程序，并且 Python 虚拟机能够提供与平台无关的运行环境。

再者，Python 是一门动态语言，不需要声明变量，在赋值语句的时候自动创建变量和对象。也不需要手动释放对象空间，采用自动垃圾回收机制，使 Python 可以直接编写逻辑代码，消除了大量繁琐的步骤。

第三，强制缩进的语法，使得 Python 代码工整、对齐，增加 Python 的可读性和简洁性。

第四，在 Python 中，一切皆对象，不仅变量、函数、类是对象, 就连 .py 的源码文件都是对象。是不是很神奇。

一句话：简洁是智慧的灵魂。

# Hello World

学习任何一门语言的第一步是看它的 Hello World 程序怎么写。下面是 Python 语言的 Hello World。

    print("hello world!")

编辑一个 .py 文件，命名为 test.py，文件中只有一行代码，调用内置方法 `print`，打印 “hello world!”，通过下面命令执行这个文件：
    
    $ python test.py
    hello world!

是不是有种运行脚本的感觉，Python 中没有编译程序的概念，而是直接翻译成字节码，不进行代码语法检查，所以可以直接执行源码。

# Python 安装

Python 安装包可以从[官网](https://www.python.org/downloads/)下载，Windows 版本下载的是可执行文件，和安装普通软件步骤相同：下一步，下一步 ... 完成。Linux 版本下载的是源码包，需要编译、安装，步骤如下：
    
    apt-get update
    apt-get install gcc make zlib1g-dev libreadline-dev libssl-dev libffi-dev  # ubuntu 环境下安装
    # yum install gcc zlib-devel readline-devel openssl-devel  sqlite-devel libffi-devel    # centos 环境下安装
    
    tar -zxvf Python-3.*.*.tgz -C /opt/
    cd /opt/Python-3.*.*
    ./configure prefix=/opt/python-3.*.*
    make
    make install

执行 Python 程序：

    $ /opt/python-3.*.*/bin/python3 test.py

也可以添加 Python 环境变量，路径是 `/opt/python-3.*.*/bin`，然后执行程序：

    $ python3 test.py
    