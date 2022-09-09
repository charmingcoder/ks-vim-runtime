# ks-vim-runtime
vim/mvim配置

## VIM配置
由于vim与neovim配置不兼容，vim不支持lua配置，neovim现在流行lua配置。目前先专注vim配置

### 插件管理器
```
vim-plug

https://github.com/junegunn/vim-plug
```

### 基础配置
```
" Sets how many lines of history VIM has to remember
set history=500

" Enable filetype plugins
filetype plugin on
filetype indent on

set nocompatible "使用vim自己的键盘模式，避免vi键盘模式的以前版本的一些bug和局限

set encoding=utf-8 "编码格式

set fencs=utf-8,ucs-bom,shift-jis,gb18030,gbk,gb2312,cp936 "打开文件格式

syntax on "语法高亮

filetype on "侦测文件类型

filetype plugin on "载入文件类型插件



set cindent "c缩进
set autoindent "回车后下一行自动缩进
set smartindent "智能缩进，这种缩进模式中，每一行都和前一行有相同的缩进量，同时这种缩进形式能正确的识别出花括号，当遇到右花括号（}），则取消缩进形式。此外还增加了识别C语言关键字的功能。如果一行是以#开头的，那么这种格式将会被特殊对待而不采用缩进格式。


set tabstop=4 " 一个tab键所占的列数
set shiftwidth=4 " 缩进的列数
set softtabstop=4 "敲入tab键时实际占有的列数
set expandtab "自动将tab键输入转化为相应的空格数


set mouse=a "可使用鼠标

set nu "设置行号

set hlsearch "高亮搜索
set incsearch "搜索逐字符高亮
set ignorecase "搜索时忽略大小写

set cursorline "高亮当前行


set background=dark "背景为黑

set showcmd "显示输入命令


set magic "设置魔术

"简单地说， magic就是设置哪些元字符要加反斜杠哪些不用加的。 简单来说：
"magic (\m)：除了 $ . * ^ 之外其他元字符都要加反斜杠。
"nomagic (\M)：除了 $ ^ 之外其他元字符都要加反斜杠。


set laststatus=2 "显示状态栏 (默认值为 1, 无法显示状态栏)
set statusline=%F%m%r%h%w%=\ %y\ %0(%{&fileformat}\ %{&encoding}\ Column:\%c\ Line:\%l\ %p%%\ Total:\%L%) "设置状态栏显示内容


set foldenable "设置允许折叠
set fdm=syntax "设置语法折叠
set fdm=manual "手动折叠

```

### 其它

#### 字体
NerdFont

#### vim Tab标签管理
vim默认最多只能打开10个标签页。使用```set tabpagemax=15```改变这个限制
- tabs切换
	- :tabnext/tabn  下一个tab, 快捷键gt
	- :tabprevious/tabp  上一个tab, 快捷键gT
	- :tablast  最后tabs
	- :tabfirst  最初tab
	- :tabclose/tabc
	- :tabonly/tabo  只保留当前的tab
	- :tabe <文件名>  在新建的标签页中打开指定的文件
	- :tabnew <文件名>  在新标签页中编辑新的文件
	- :tabs  查看所有打开的tab列表，并有>标识当前页面，用+表示出已更改的页面
	- :tab split  在新建标签页中，打开当前缓冲区中的文件
	- :tabf  允许在当前目录搜索文件，并在新标签页中打开。比如tabf img.* 此命令只能打开一个文件
	- :tabm [次序]  移动当前文件的标签页次序。比如:tabm 1将把当前标签页移动到第2的位置；不指定次序将被移动到最后

- 配置标签页
	- :set showtabline=[1,2,3]  标签页在窗口上方显示标签栏。=0完全不显示标签栏，=1只有新建时才显示, =2总是显示

- 多标签页命令
	- :tabdo <命令>  同时在多个标签页中执行命令。如:tabdo %s/food/drink/g命令把当前多个标签页文件中的food都换成drink

- 帮助
	- :help tab-page-intro

#### vim 移动命令
- 显示区滚动
	- ^U ：文本向下滚动半屏
	- ^D：文本向上滚动半屏
	- ^E:向上滚动一行
	- ^Y:向下滚动一行(windows 下可能被映射为重做键)
	- ^F:向前滚动一整屏front
	- ^B: 向后滚动一整屏back
	- zz：将当前行置为屏幕中心行
	- zb：将当前行置为屏幕最后行bottom
	- zt：将当前行置为平没有第一行top

- 整行移动
	- :m +1 向下移动1行
	- :m -2 向上移动1行
	- :m 3 移动到第3行后的一行

- 其它
	- ddp  交换两行，与:m +1效果相同

