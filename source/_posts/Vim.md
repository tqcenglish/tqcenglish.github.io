title: Vim
date: 2016-03-4 22:34:44
tags: vi
---

Vim
===

vim快捷键
---------

不要想一次记忆全部.

跳转
----

~~~~

    %   ;跳转到相匹配的括号
    gd      ;跳转到局部变量定义位置
    gf  ;打开光标处所指的文件
    "   ;跳转到光标上次停靠的位置
    mx  ;设置书签,x的取值范围位a-z的26个字母
    `x  ;跳转到对应书签位置
    {   ;跳转上一段开头
    }   ;跳转到下一段的开头
    (   ;跳转到句子的开头
    )   ;跳转到下一句子开头
    [[  ;跳转到上一个函数
    ]]  ;跳转到下一个函数
~~~~

### 光标和补全

~~~~ {.sh}

    Ctrl + I     向前追赶你的光标移动
    Ctrl + O     向后回退你的光标移动
    Ctrl + X 和 Ctrl + D  宏定义补齐
    Ctrl + X 和 Ctrl + ]  是Tag 补齐
    Ctrl + X 和 Ctrl + F  是文件名补齐
    Ctrl + X 和 Ctrl + I  关键词补齐，指明关键词所在文件名
    Ctrl + X 和 Ctrl + V  是表达式补齐
    Ctrl + X 和 Ctrl + L  这可以对整个行补齐
~~~~

缩进相关
--------

~~~~ {.sh}

    >>  -向右给它进当前行
    <<  -向左缩进当前行
    =   - 缩进当前行 （和上面不一样的是，它会对齐缩进）
    =%  -把光标位置移到语句块的括号上，然后按=%，缩进整个语句块（%是括号匹配）
    G=gg 或是 gg=G        -缩进整个文件（G是到文件结尾，gg是到文件开头）
    :r!date         插入日期, :r 是:read的缩写，!是表明要运行一个shell命令
    * 或 # 在当前文件中搜索当前光标的单词
~~~~

vimrc设置
---------

-   set guifont=Monaco:h15 "设置字体
-   colorscheme desert "设置配色方案
-   set encoding=utf-8 "设置编码
-   set is "搜索时在未完全输入完毕要检索的文本时就开始检索
-   set nocompatible "关闭vi兼容模式
-   filetype plugin on "载入文件类型插件
-   filetype indent on "为特定文件类型载入相关缩进文件
-   set confirm "在处理未保存或只读文件的时候，弹出确认
-   set nu "显示行号
-   set showcmd "显示命令
-   set lz "当运行宏时，在命令执行完成之前，不重绘屏幕
-   set hid "可以在没有保存的情况下切换buffer
-   set backspace=eol,start,indent
-   set whichwrap+=\<,\>,h,l,b,s,[,] "退格键和方向键可以换行
-   set incsearch "增量式搜索
-   set hlsearch "高亮搜索
-   set ignorecase "搜索时忽略大小写
-   set showmatch "显示匹配的括号
-   set nobackup "关闭备份
-   set noswapfile "不使用swp文件，注意，错误退出后无法恢复
-   set lbr "在breakat字符处而不是最后一个字符处断行
-   set ai "自动缩进
-   set si "智能缩进
-   set cindent "C/C++风格缩进
-   set foldmethod=indent "用缩进表示折叠
-   set spell "打开拼写检查
-   set mouse=a "设置鼠标模式

vim插件
-------

### vim-pathogen

vim插件管理, pathogen.vim makes it super easy to install plugins and
runtime files in their own private directories. [pathogen][]

### nerdtree

vim中显示树形结构的文件列表, The NERD tree allows you to explore your
filesystem and to open files and directories.

[nerdtree][]

### vim-pandoc

Vim Plugin for pandoc

[pandoc][]

### taglist

把文件在~/.vim/目录中解压缩,在~/.vim/plugin和~/.vim/doc目录中各放入一个文件：

    plugin/taglist.vim – taglist插件
    doc/taglist.txt    - taglist帮助文件
生成帮助标签

     :helptags ~/.vim/doc

查看帮助
    :help taglist.txt

配置
    if MySys() == "windows"                "设定windows系统中ctags程序的位置
        let Tlist_Ctags_Cmd = 'ctags'
    elseif MySys() == "linux"              "设定linux系统中ctags程序的位置
        let Tlist_Ctags_Cmd = '/usr/bin/ctags'
    endif
    let Tlist_Show_One_File = 1            "不同时显示多个文件的tag，只显示当前文件的
    let Tlist_Exit_OnlyWindow = 1          "如果taglist窗口是最后一个窗口，则退出vim
    let Tlist_Use_Right_Window = 1         "在右侧窗口中显示taglist窗口
    map <silent> <F9> :TlistToggle<cr>

[taglist](http://www.vim.org/scripts/script.php?script_id=273)

  [pathogen]: https://github.com/tpope/vim-pathogen
  [nerdtree]: https://github.com/scrooloose/nerdtree
  [pandoc]: https://github.com/vim-pandoc/vim-pandoc
