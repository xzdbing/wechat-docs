
工欲善其事，必先利其器。

Sublime Text 3 是一款文本编辑器，不过能很好的支持代码、标记文本、文档等复杂文本的编写。如果安装使用 Sublime Text 3，完全可以抛弃使用常用文本编辑器、Markdown编辑器、HTML编辑器、OneNote、Notepad++，以及一半的 PyCharm、一半的 VS。

以下对 Sublime Text 3 中 Windows 版本的介绍，在 Linux 下支持并不好，如果是 Linux 系统，推荐使用 Atom。

# Sublime Text 3 的介绍

Sublime Text 3 中 99% 的代码是用 C++ 开发的，插件部分是用 Python 写的。

在性能上，Sublime Text 3 和 Windows 的文本编辑器体验差不多。一方面，在软件自身的打开速度和打开文本文件的速度，用时差不多；另一方面，在内存的占用方面大概是文本编辑器的两倍。但在使用过程中，基本感受不到 Sublime Text 3 和文本编辑器的差异。

重点是在实用性上面，主要的特殊功能有：

* 文字拼写检查
* 代码提示
* 书签
* 文件搜索、项目切换
* 多窗口、多鼠标点编辑
* 大量的插件工具，等待你去挖掘

# Sublime Text 3 的安装

## 下载

1. 浏览[官网](http://www.sublimetext.com/)，下载最新 64 位 Windows 版的安装包。

2. 在安装过程中：选中 Add to explorer context menu，添加到右键菜单，方便启动。

3. 安装完成之后：在 Sublime Text 3 安装路径下创建文件夹：Sublime Text 3/Data，方便配置软件和管理以后安装的插件。

## 激活

适合 3176 版本，亲测可用，点击菜单栏 `<Help> -> <Enter License>`， 复制粘贴下面的内容：

    ----- BEGIN LICENSE -----
    sgbteam
    Single User License
    EA7E-1153259
    8891CBB9 F1513E4F 1A3405C1 A865D53F
    115F202E 7B91AB2D 0D2A40ED 352B269B
    76E84F0B CD69BFC7 59F2DFEF E267328F
    215652A3 E88F9D8F 4C38E3BA 5B2DAAE4
    969624E7 DC9CD4D5 717FB40C 1B9738CF
    20B3C4F1 E917B5B3 87C38D9C ACCE7DD8
    5F7EF854 86B9743C FADC04AA FB0DA5C0
    F913BE58 42FEA319 F954EFDD AE881E0B
    ------ END LICENSE ------

# 安装扩展插件，配置高可用性

## 插件管理：Package Control

Package Control 是管理 Sublime Text 的插件的插件。

1. ctrl + shift + p，打开命令面板
2. 输入：Install Package Control，安装 Package Control 插件

## 主题插件：Theme - SoDaReloaded

1. ctrl + shift + p，打开命令面板
2. 输入: Package Control: Install Package，通过 Package Control 安装插件
3. 输入：Theme - SoDaReloaded，安装主题

## 配置渲染颜色：One Half Light

1. 打开[颜色编辑器](http://tmtheme-editor.herokuapp.com)
2. 在 Gallery 中选择一个你喜欢的颜色配置，个人比较喜欢 One Half Light。
3. 修改好配置方案，保存下载
4. 用 WinRAR（或其他压缩软件）打开压缩文件：Sublime Text 3/Packages/Color Scheme - Default.sublime-package，将 One Half Light 配色文件添加到 Color Scheme - Default.sublime-package 文件中

## 主题、颜色配置

点击菜单栏 `<Preferences> -> <Package Settings> -> <Package Control> -> <Settings - User>`，添加下列内容：

    {
        "color_scheme": "Packages/Color Scheme - Default/OneHalfLight.tmTheme",
        "font_size": 11,
        "font_options": "gdi",
        "line_padding_top": 1,
        "line_padding_bottom": 1,
        "ignored_packages":
        [
           "Vintage"
        ],
        "theme": "SoDaReloaded Light.sublime-theme",
        "translate_tabs_to_spaces": true,               // 空格替代tab
        "highlight_line": true,                         // 高亮显示当前行
        "show_encoding": true,                          // 显示文件当前编码
        "bold_folder_labels": true,                     // 加粗文件夹名称
        "word_wrap": true                               // 自动换行
        // "trim_trailing_white_space_on_save": true,  // 保存时去掉行尾无用空格
        // "save_on_focus_lost": true,                 // 焦点丢失后自动保存
    }
    
## 快捷键设置

1. Ctr + P:  快速切换打开文件，并且快速跳转文件中的symbols、line、word：
    * [file]            匹配文件
    * [file]@[fun]      匹配函数 / 标题
    * [file]#[word]     匹配内容
    * [file]:lineNum    跳转到行

2. hjkl 上下左右模拟 vim 快捷键，还有其他快捷键可以自行测试，点击菜单栏 `<Preferences> -> <Key Bindings>`，添加下列内容：

```
[
    { "keys": ["shift+enter"], "command": "run_macro_file", "args": {"file": "res://Packages/Default/Add Line.sublime-macro"} },
    { "keys": ["ctrl+h"], "command": "move", "args": {"by": "characters", "forward": false} },
    { "keys": ["ctrl+l"], "command": "move", "args": {"by": "characters", "forward": true} },
    { "keys": ["ctrl+k"], "command": "move", "args": {"by": "lines", "forward": false} },
    { "keys": ["ctrl+j"], "command": "move", "args": {"by": "lines", "forward": true} },
    { "keys": ["ctrl+1"], "command": "fold_by_level", "args": {"level": 1} },
    { "keys": ["ctrl+2"], "command": "fold_by_level", "args": {"level": 2} },
    { "keys": ["ctrl+3"], "command": "fold_by_level", "args": {"level": 3} },
    { "keys": ["ctrl+4"], "command": "fold_by_level", "args": {"level": 4} },
    { "keys": ["ctrl+5"], "command": "fold_by_level", "args": {"level": 5} },
    { "keys": ["ctrl+6"], "command": "fold_by_level", "args": {"level": 6} },
    { "keys": ["ctrl+7"], "command": "fold_by_level", "args": {"level": 7} },
    { "keys": ["ctrl+8"], "command": "fold_by_level", "args": {"level": 8} },
    { "keys": ["ctrl+9"], "command": "fold_by_level", "args": {"level": 9} },
    { "keys": ["ctrl+0"], "command": "unfold_all" },
]
```

## 支持 Python 插件安装：Anaconda

Anaconda 是一款支持 Python 开发的插件，安装完成之后，打开 .py 文件，Ctrl + B 可以直接执行 Python 程序。

Anaconda 默认提示文档帮助和 PEP8 检查，嫌麻烦可以取消。点击菜单栏 `<Preferences> -> <Package Settings> -> <Anaconda> -> <Settings - User>`，添加下列内容：

    {
        "enable_signatures_tooltip": false,
        "enable_docstrings_tooltip": false,
        "merge_signatures_and_doc": false,
        "pep8": false
    }

### Linux 支持中文

    git clone https://github.com/lyfeyaj/sublime-text-imfix.git
    cd sublime-text-imfix
    cp ./lib/libsublime-imfix.so /opt/sublime_text_3/
    cp ./src/subl /usr/bin/


