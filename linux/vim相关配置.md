### Vim与配置

#### 1、安装vim

```shell
sudo apt-get install vim
```

#### 2.配置vim

```shell
#编辑vimrc文件(全局配置文件,针对所有用户)
sudo vim /etc/vim/vimrc
```

#### 3.配置内容

````shell
#1.显示左侧行号
set number/nu

#2.自动语法高亮
syntax on 

#3.设置缩进的宽度
set tabstop=4

#4.突出显示当前行
set cursorline

#5.在右下角显示光标位置的状态行
set ruler    

#6.自动缩进
set autoindent
````

#### 4.vimrc

```shell
"This line should not be removed as it ensures that various options are
" properly set to work with the Vim-related packages available in Debian.
debian.vim

" Uncomment the next line to make Vim more Vi-compatible
" NOTE: debian.vim sets 'nocompatible'. Setting 'compatible' changes numerous
" options, so any other options should be set AFTER setting 'compatible'.
set nocompatible

" Vim5 and later versions support syntax highlighting. Uncommenting the
" following enables syntax highlighting by default.
if has("syntax")
syntax on " 语法高亮
endif
colorscheme ron " elflord ron peachpuff default 设置配色方案，vim自带的配色方案保存在/usr/share/vim/vim72/colors目录下

" detect file type
filetype on
filetype plugin on

" If using a dark background within the editing area and syntax highlighting
" turn on this option as well
set background=dark

" Uncomment the following to have Vim jump to the last position when
" reopening a file
if has("autocmd")
au BufReadPost * if line("'\"") > 1 && line("'\"") <= line("$") | exe "normal! g'\"" | endif
"have Vim load indentation rules and plugins according to the detected filetype
filetype plugin indent on
endif

" The following are commented out as they cause vim to behave a lot
" differently from regular Vi. They are highly recommended though.

" 搜索模式里忽略大小写
"set ignorecase 

" 如果搜索模式包含大写字符，不使用 'ignorecase' 选项。只有在输入搜索模式并且打开 'ignorecase' 选项时才会使用。
"set smartcase 

" 自动把内容写回文件: 如果文件被修改过，在每个 :next、:rewind、:last、:first、:previous、:stop、:suspend、:tag、:!、:make、CTRL-] 和 CTRL-^命令时进行；用 :buffer、CTRL-O、CTRL-I、'{A-Z0-9} 或 `{A-Z0-9} 命令转到别的文件时亦然。
set autowrite 

" 设置自动对齐(缩进)：即每行的缩进值与上一行相等；使用 noautoindent 取消设置
set autoindent 

" 智能对齐方式
"set smartindent 

 " 设置制表符(tab键)的宽度
set tabstop=4

" 设置软制表符的宽度
set softtabstop=4 

" (自动) 缩进使用的4个空格
set shiftwidth=4 

 " 使用 C/C++ 语言的自动缩进方式
set cindent

"设置C/C++语言的具体缩进方式
set cinoptions={0,1s,t0,n-2,p2s,(03s,=.5s,>1s,=1s,:1s 

" 设置退格键可用
"set backspace=2

 " 设置匹配模式，显示匹配的括号 
set showmatch

 " 整词换行 
set linebreak

" 光标从行首和行末时可以跳到另一行去 "
set whichwrap=b,s,<,>,[,] 

set hidden

"使用鼠标 
set mouse=a 

"显示行号 
set number

"标识预览窗口 
"set previewwindow 

"历史记录50条
"set command history to 50
set history=50 

"状态行设置(总显示最后一个窗口的状态行；设为1则窗口数多于一个的时候显示最后一个窗口的状态行；0不显示最后一个窗口的状态行 )
set laststatus=2 

" 标尺，用于显示光标位置的行号和列号，逗号分隔。每个窗口都有自己的标尺。如果窗口有状态行，标尺在那里显示。否则，它显示在屏幕的最后一行上。 
set ruler 

" 命令行显示输入的命令 
set showcmd 

" 命令行显示vim当前模式
set showmode  

"--find setting-- 
set incsearch 

" 输入字符串就显示匹配点 
set hlsearch 

"自动语法高亮
syntax on 

"突出显示当前行
set cursorline
```







### Vim基本操作

```shell
#保存
:w

#退出
:q

#强制
:!

#进入模式
点击esc  

#强制保存
:wq!

#强制退出不保存
:q!
```

