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

### 插件配置II

```

"call plug#begin('~/.ks-vim-runtim/plugged')
call plug#begin()
" 启动时显示一个小牛+金句
Plug 'mhinz/vim-startify'

"Plug 'preservim/vim-markdown'
" 生成目录插件
"Plug 'mzlogin/vim-markdown-toc'
"Plug 'iamcco/markdown-preview.nvim'


"------------------
" Code Completions
"------------------
Plug 'Shougo/neocomplete'
Plug 'mattn/emmet-vim'
Plug 'jiangmiao/auto-pairs'
Plug 'ervandew/supertab'
" snippets
Plug 'SirVer/ultisnips' | Plug 'honza/vim-snippets'

"-----------------
" Fast navigation
"-----------------
Plug 'andymass/vim-matchup'
Plug 'easymotion/vim-easymotion'
Plug 'haya14busa/incsearch.vim'
Plug 'haya14busa/incsearch-fuzzy.vim'
Plug 'haya14busa/incsearch-easymotion.vim'

"--------------
" Fast editing
"--------------
Plug 'tpope/vim-surround'
Plug 'scrooloose/nerdcommenter'
Plug 'sjl/gundo.vim', {'on': 'GundoToggle'}
Plug 'godlygeek/tabular'
Plug 'nathanaelkane/vim-indent-guides'
Plug 'vim-scripts/argtextobj.vim'
Plug 'tpope/vim-repeat'
Plug 'gcmt/wildfire.vim'
"'bkad/CamelCaseMotion'
"'terryma/vim-multiple-cursors'


"--------------
" IDE features
"--------------
Plug 'scrooloose/nerdtree'  ", {'on': 'NERDTreeToggle'}
Plug 'Xuyuanp/nerdtree-git-plugin'
Plug 'majutsushi/tagbar'
Plug 'mileszs/ack.vim'
Plug 'ctrlpvim/ctrlp.vim'
Plug 'tpope/vim-fugitive'
" 底部状态栏
Plug 'vim-airline/vim-airline'
Plug 'vim-syntastic/syntastic'
Plug 'bronson/vim-trailing-whitespace'
Plug 'fholgado/minibufexpl.vim'
"Plug 'maksimr/vim-jsbeautify'
"'humiaozuzu/TabBar'

"-------------
" Other Utils
"-------------
Plug 'nvie/vim-togglemouse'
"'humiaozuzu/fcitx-status'

"----------------------------------------
" Syntax/Indent for language enhancement
"----------------------------------------
"------- web backend ---------
"'2072/PHP-Indenting-for-VIm'
"'tpope/vim-rails'
"'lepture/vim-jinja'
Plug 'digitaltoad/vim-jade'

"------- web frontend ----------
Plug 'othree/html5.vim', {'for': 'html'}
Plug 'pangloss/vim-javascript'
Plug 'kchmck/vim-coffee-script', {'for': 'coffee'}
Plug 'nono/jquery.vim'
Plug 'groenewege/vim-less', {'for': 'less'}
" 'wavded/vim-stylus'
" 'nono/vim-handlebars'
" 'tpope/vim-haml'

"------- markup language -------
"'tpope/vim-markdown'
"'timcharper/textile.vim'

"------- Ruby --------
"'tpope/vim-endwise'

"------- Go ----------
Plug 'fatih/vim-go', {'for': 'go'}

"------- FPs ------
Plug 'luochen1990/rainbow'
" 'wlangstroth/vim-racket'
" 'vim-scripts/VimClojure'
" 'rosstimson/scala-vim-support'

"------- Recat ------
Plug 'mxw/vim-jsx'

"--------------
" Appearance
"--------------
Plug 'yonchu/accelerated-smooth-scroll'

"--------------
" Color Schemes
"--------------
"Plug 'rickharris/vim-blackboard'
"Plug 'altercation/vim-colors-solarized'
Plug 'rickharris/vim-monokai'
"Plug 'tpope/vim-vividchalk'
"Plug 'Lokaltog/vim-distinguished'
"Plug 'chriskempson/vim-tomorrow-theme'
"Plug 'fisadev/fisa-vim-colorscheme'
Plug 'ajh17/Spacegray.vim'

"------ Airline ------
"Plug 'vim-airline/vim-airline-themes'

" You can specify revision/branch/tag.
" call dein#add('Shougo/vimshell', { 'rev': '3787e5'  })

call plug#end()

let g:vim_markdown_math = 1

" 在当前光标生成目录 :GenTocMarked
" 更新目录 :UpdateToc
" 取消储存时自动更新目录
let g:vim_auto_update_on_save = 0







"-----------------
" Plugin settings
"-----------------
" luochen1990/rainbow
let g:rainbow_active = 1
let g:rainbow_conf = {
    \   'guifgs': ['royalblue3', 'darkorange3', 'seagreen3', 'firebrick'],
    \   'ctermfgs': ['lightblue', 'lightyellow', 'lightcyan', 'lightmagenta'],
    \   'operators': '_,_',
    \   'parentheses': ['start=/(/ end=/)/ fold', 'start=/\[/ end=/\]/ fold', 'start=/{/ end=/}/ fold'],
    \   'separately': {
    \       '*': {},
    \       'tex': {
    \           'parentheses': ['start=/(/ end=/)/', 'start=/\[/ end=/\]/'],
    \       },
    \       'lisp': {
    \           'guifgs': ['royalblue3', 'darkorange3', 'seagreen3', 'firebrick', 'darkorchid3'],
    \       },
    \       'vim': {
    \           'parentheses': ['start=/(/ end=/)/', 'start=/\[/ end=/\]/', 'start=/{/ end=/}/ fold', 'start=/(/ end=/)/ containedin=vimFuncBody', 'start=/\[/ end=/\]/ containedin=vimFuncBody', 'start=/{/ end=/}/ fold containedin=vimFuncBody'],
    \       },
    \       'html': {
    \           'parentheses': ['start=/\v\<((area|base|br|col|embed|hr|img|input|keygen|link|menuitem|meta|param|source|track|wbr)[ >])@!\z([-_:a-zA-Z0-9]+)(\s+[-_:a-zA-Z0-9]+(\=("[^"]*"|'."'".'[^'."'".']*'."'".'|[^ '."'".'"><=`]*))?)*\>/ end=#</\z1># fold'],
    \       },
    \       'css': 0,
    \   }
    \}
" fixed vim-javascript compatibility
autocmd FileType javascript syntax clear jsFuncBlock

" tabbar
let g:Tb_MaxSize = 2
let g:Tb_TabWrap = 1

hi Tb_Normal guifg=white ctermfg=white
hi Tb_Changed guifg=green ctermfg=green
hi Tb_VisibleNormal ctermbg=252 ctermfg=235
hi Tb_VisibleChanged guifg=green ctermbg=252 ctermfg=white


" easy-motion
let g:EasyMotion_leader_key = '<Leader>'
" <Leader>f{char} to move to {char}
map  <Leader>f <Plug>(easymotion-bd-f)
nmap <Leader>f <Plug>(easymotion-overwin-f)

" s{char}{char} to move to {char}{char}
nmap s <Plug>(easymotion-overwin-f2)

" Move to line
map <Leader>L <Plug>(easymotion-bd-jk)
nmap <Leader>L <Plug>(easymotion-overwin-line)

" Move to word
map  <Leader>w <Plug>(easymotion-bd-w)
nmap <Leader>w <Plug>(easymotion-overwin-w)
" replace vim default search
"map  / <Plug>(easymotion-sn)
"omap / <Plug>(easymotion-tn)
" These `n` & `N` mappings are options. You do not have to map `n` & `N` to
" EasyMotion.
" Without these mappings, `n` & `N` works fine. (These mappings just provide
" different highlight method and have some other features )
"map  n <Plug>(easymotion-next)
"map  N <Plug>(easymotion-prev)
"With this option set, v will match both v and V, but V will match V only.
let g:EasyMotion_smartcase = 1
"for symbols and numerals. 1 will match 1 and !; ! matches ! only.
"let g:EasyMotion_use_smartsign_us = 1 " US layout


" incsearch & incsearch-fuzzy & incsearch-easymotion
" :h g:incsearch#auto_nohlsearch
" set hlsearch
let g:incsearch#auto_nohlsearch = 1
" map /  <Plug>(incsearch-forward)
" map ?  <Plug>(incsearch-backward)
" map g/ <Plug>(incsearch-stay)

map n  <Plug>(incsearch-nohl-n)
map N  <Plug>(incsearch-nohl-N)
map *  <Plug>(incsearch-nohl-*)
map #  <Plug>(incsearch-nohl-#)
map g* <Plug>(incsearch-nohl-g*)
map g# <Plug>(incsearch-nohl-g#)

" You can use other keymappings like <C-l> instead of <CR> if you want to
" use these mappings as default search and somtimes want to move cursor with
" EasyMotion.
function! s:incsearch_config(...) abort
  return incsearch#util#deepextend(deepcopy({
    \   'modules': [incsearch#config#easymotion#module({'overwin': 1})],
    \   'keymap': {
    \     "\<CR>": '<Over>(easymotion)'
    \   },
    \   'is_expr': 0
    \ }), get(a:, 1, {}))
endfunction

noremap <silent><expr> /  incsearch#go(<SID>incsearch_config())
noremap <silent><expr> ?  incsearch#go(<SID>incsearch_config({'command': '?'}))
noremap <silent><expr> g/ incsearch#go(<SID>incsearch_config({'is_stay': 1}))

function! s:config_easyfuzzymotion(...) abort
  return extend(copy({
    \   'converters': [
    \     incsearch#config#fuzzy#converter(),
    \     incsearch#config#fuzzyspell#converter()
    \   ],
    \   'modules': [incsearch#config#easymotion#module({'overwin': 1})],
    \   'keymap': {"\<CR>": '<Over>(easymotion)'},
    \   'is_expr': 0,
    \   'is_stay': 1
    \ }), get(a:, 1, {}))
endfunction
noremap <silent><expr> z/ incsearch#go(<SID>config_easyfuzzymotion())
noremap <silent><expr> z? incsearch#go(<SID>config_easyfuzzymotion({'command': '?'}))
noremap <silent><expr> zg? incsearch#go(<SID>config_easyfuzzymotion({'is_stay': 1}))

" vim-indent-guides
if has("gui_running")
    let g:indent_guides_enable_on_vim_startup = 1
endif
" let g:indent_guides_auto_colors = 0
" autocmd VimEnter,Colorscheme * :hi IndentGuidesOdd  guibg=black ctermbg=3
" autocmd VimEnter,Colorscheme * :hi IndentGuidesEven guibg=darkgrey ctermbg=4
let g:indent_guides_start_level = 2
let g:indent_guides_guide_size = 2

" jsx
let g:jsx_ext_required = 0 " Allow JSX in normal JS files

" Tagbar
"let g:tagbar_ctags_bin='/usr/local/bin/ctags'
let g:tagbar_left=1
let g:tagbar_width=30
let g:tagbar_autofocus = 1
let g:tagbar_sort = 0
let g:tagbar_compact = 1
" tag for coffee
if executable('coffeetags')
  let g:tagbar_type_coffee = {
        \ 'ctagsbin' : 'coffeetags',
        \ 'ctagsargs' : '',
        \ 'kinds' : [
        \ 'f:functions',
        \ 'o:object',
        \ ],
        \ 'sro' : ".",
        \ 'kind2scope' : {
        \ 'f' : 'object',
        \ 'o' : 'object',
        \ }
        \ }

  let g:tagbar_type_markdown = {
    \ 'ctagstype' : 'markdown',
    \ 'sort' : 0,
    \ 'kinds' : [
        \ 'h:sections'
    \ ]
    \ }
endif

" Nerd Tree
let NERDChristmasTree=0
let NERDTreeWinSize=30
let NERDTreeChDirMode=2
let NERDTreeIgnore=['\~$', '\.pyc$', '\.swp$']
" let NERDTreeSortOrder=['^__\.py$', '\/$', '*', '\.swp$',  '\~$']
let NERDTreeShowBookmarks=1
let NERDTreeWinPos = "right"

" git nerd tree
let g:NERDTreeGitStatusIndicatorMapCustom= {
    \ "Modified"  : "✹",
    \ "Staged"    : "✚",
    \ "Untracked" : "✭",
    \ "Renamed"   : "➜",
    \ "Unmerged"  : "═",
    \ "Deleted"   : "✖",
    \ "Dirty"     : "✗",
    \ "Clean"     : "✔︎",
    \ "Unknown"   : "?"
    \ }

" nerdcommenter
let NERDSpaceDelims=1
" nmap <D-/> :NERDComToggleComment<cr>
let NERDCompactSexyComs=1

" ZenCoding
let g:user_emmet_expandabbr_key='<C-j>'

" airline
let g:airline_powerline_fonts=1
let g:airline#extension#tabline#enable=1


" neocomplete
" Disable AutoComplPop.
let g:acp_enableAtStartup = 0
" Use neocomplete.
let g:neocomplete#enable_at_startup = 1
" Use smartcase.
let g:neocomplete#enable_smart_case = 1
" Set minimum syntax keyword length.
let g:neocomplete#sources#syntax#min_keyword_length = 3
let g:neocomplete#lock_buffer_name_pattern = '\*ku\*'

" Define keyword.
if !exists('g:neocomplete#keyword_patterns')
    let g:neocomplete#keyword_patterns = {}
endif
let g:neocomplete#keyword_patterns['default'] = '\h\w*'

" Plugin key-mappings.
inoremap <expr><C-g>     neocomplete#undo_completion()
inoremap <expr><C-l>     neocomplete#complete_common_string()

" Recommended key-mappings.
" <CR>: close popup and save indent.
inoremap <silent> <CR> <C-r>=<SID>my_cr_function()<CR>
function! s:my_cr_function()
  return (pumvisible() ? "\<C-y>" : "" ) . "\<CR>"
  " For no inserting <CR> key.
  "return pumvisible() ? "\<C-y>" : "\<CR>"
endfunction
" <TAB>: completion.
inoremap <expr><TAB>  pumvisible() ? "\<C-n>" : "\<TAB>"
" <C-h>, <BS>: close popup and delete backword char.
inoremap <expr><C-h> neocomplete#smart_close_popup()."\<C-h>"
inoremap <expr><BS> neocomplete#smart_close_popup()."\<C-h>"
" Close popup by <Space>.
"inoremap <expr><Space> pumvisible() ? "\<C-y>" : "\<Space>"

" AutoComplPop like behavior.
"let g:neocomplete#enable_auto_select = 1

" Shell like behavior(not recommended).
"set completeopt+=longest
"let g:neocomplete#enable_auto_select = 1
"let g:neocomplete#disable_auto_complete = 1
"inoremap <expr><TAB>  pumvisible() ? "\<Down>" : "\<C-x>\<C-u>"

" Enable omni completion.
autocmd FileType css setlocal omnifunc=csscomplete#CompleteCSS
autocmd FileType html,markdown setlocal omnifunc=htmlcomplete#CompleteTags
autocmd FileType javascript setlocal omnifunc=javascriptcomplete#CompleteJS
autocmd FileType python setlocal omnifunc=pythoncomplete#Complete
autocmd FileType xml setlocal omnifunc=xmlcomplete#CompleteTags
autocmd FileType c setlocal omnifunc=ccomplete#Complete

" Enable heavy omni completion.
if !exists('g:neocomplete#sources#omni#input_patterns')
  let g:neocomplete#sources#omni#input_patterns = {}
endif
"let g:neocomplete#sources#omni#input_patterns.php = '[^. \t]->\h\w*\|\h\w*::'
"let g:neocomplete#sources#omni#input_patterns.c = '[^.[:digit:] *\t]\%(\.\|->\)'
"let g:neocomplete#sources#omni#input_patterns.cpp = '[^.[:digit:] *\t]\%(\.\|->\)\|\h\w*::'

" For perlomni.vim setting.
" https://github.com/c9s/perlomni.vim
"let g:neocomplete#sources#omni#input_patterns.perl = '\h\w*->\h\w*\|\h\w*::'

" Enable omni completion.
" autocmd FileType css setlocal omnifunc=csscomplete#CompleteCSS
" autocmd FileType html,markdown setlocal omnifunc=htmlcomplete#CompleteTags
" autocmd FileType javascript setlocal omnifunc=javascriptcomplete#CompleteJS
" autocmd FileType python setlocal omnifunc=pythoncomplete#Complete
" autocmd FileType c setlocal omnifunc=ccomplete#Complete
" if !exists('g:neocomplcache_omni_patterns')
  " let g:neocomplcache_omni_patterns = {}
" endif
" let g:neocomplcache_omni_patterns.erlang = '[a-zA-Z]\|:'

" SuperTab
" let g:SuperTabDefultCompletionType='context'
let g:SuperTabDefaultCompletionType = '<C-X><C-U>'
let g:SuperTabRetainCompletionType=2

" ctrlp
set wildignore+=*/tmp/*,*.so,*.o,*.a,*.obj,*.swp,*.zip,*.pyc,*.pyo,*.class,.DS_Store  " MacOSX/Linux
let g:ctrlp_custom_ignore = '\.git$\|\.hg$\|\.svn$'
:command Ctrlp CtrlPBuffer

" syntastic
set statusline+=%#warningmsg#
set statusline+=%{SyntasticStatuslineFlag()}
set statusline+=%*
let g:syntastic_always_populate_loc_list = 1
let g:syntastic_auto_loc_list = 1
let g:syntastic_check_on_open = 1
let g:syntastic_check_on_wq = 0
let g:syntastic_javascript_checkers = ['eslint']
"let g:syntastic_javascript_jsxhint_exec = 'jsx-jshint-wrapper'


" Tabularize
nmap <Leader>a= :Tabularize /=<CR>
vmap <Leader>a= :Tabularize /=<CR>
nmap <Leader>a: :Tabularize /:\zs<CR>
vmap <Leader>a: :Tabularize /:\zs<CR>
nmap <Leader>a= :Tabularize /=<CR>
vmap <Leader>a= :Tabularize /=<CR>
nmap <Leader>a<Space> :Tabularize / \zs<CR>
vmap <Leader>a<Space> :Tabularize / \zs<CR>

" MiniBufExpl
"let g:miniBufExplorerAutoStart=1
let g:miniBufExplBuffersNeeded = 1
let g:miniBufExplMapWindowNavVim = 1
let g:miniBufExplMapWindowNavArrows = 1
let g:miniBufExplMapCTabSwitchBufs = 1
let g:miniBufExplModSelTarget = 1
let g:miniBufExplCycleArround = 1
noremap <C-TAB>   :MBEbn<CR>
noremap <C-S-TAB> :MBEbp<CR>

" vim-jsbeautify
autocmd FileType javascript noremap <buffer>  <D-ƒ> :call JsBeautify()<cr>
" for json
autocmd FileType json noremap <buffer> <D-ƒ> :call JsonBeautify()<cr>
" for jsx
autocmd FileType jsx noremap <buffer> <D-ƒ> :call JsxBeautify()<cr>
" for html
autocmd FileType html noremap <buffer> <D-ƒ> :call HtmlBeautify()<cr>
" for css or scss
autocmd FileType css noremap <buffer> <D-ƒ> :call CSSBeautify()<cr>>
" beautify only selected lines
autocmd FileType javascript vnoremap <buffer>  <D-ƒ> :call RangeJsBeautify()<cr>
autocmd FileType json vnoremap <buffer> <D-ƒ> :call RangeJsonBeautify()<cr>
autocmd FileType jsx vnoremap <buffer> <D-ƒ> :call RangeJsxBeautify()<cr>
autocmd FileType html vnoremap <buffer> <D-ƒ> :call RangeHtmlBeautify()<cr>
autocmd FileType css vnoremap <buffer> <D-ƒ> :call RangeCSSBeautify()<cr>

" accelerated-smooth-scroll
" g:ac_smooth_scroll_fb_sleep_time_msec = 5
" g:ac_smooth_scroll_du_sleep_time_msec = 5


" Keybindings for plugin toggle
nnoremap <F2> :set invpaste paste?<CR>
set pastetoggle=<F2>
nmap <F5> :TagbarToggle<cr>
nmap <F6> :NERDTreeToggle<cr>
nmap <Leader>nn :NERDTreeToggle<cr>
nmap <F3> :GundoToggle<cr>
nmap <F4> :IndentGuidesToggle<cr>
nmap  <D-/> :
"nnoremap <leader>a :Ack
nnoremap <leader>v V`]

" switching to buffer 1 - 9 is mapped to ,[nOfBuffer]
for buffer_no in range(1, 9)
  execute "nmap <Leader>" . buffer_no . " :b" . buffer_no . "\<CR>"
endfor

" switching to buffer 10 - 100 is mapped to ,0[nOfBuffer]
for buffer_no in range(10, 100)
  execute "nmap <Leader>0" . buffer_no . " :b" . buffer_no . "\<CR>"
endfor


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


#### LSP介绍

过去的编辑器包揽了诸如代码高亮、语法分析、跳转等功能，这样就导致了所有编辑器都有自己专有的一套显示、跳转等方案。而第三方编辑器想要达到完全相同的效果几乎是不可能的。但是微软提出的LSP(language server protocol)却改变了这一格局。

LSP最重要的就是将语法分析、跳转、自动补全功能这些语言的核心功能和最终呈现效果分开。即server端主要提供了语法分析、补全、跳转的核心功能，而在客户端要做就是调用服务端提供的这些功能来展示以及通过快捷键或者其他用户接口以便用户使用。而且语言服务器是以进程的方式单独运行，并不会影响客户端的运行。它们之间通过本地网络的形式进行信息交换

![image](https://note.youdao.com/yws/api/personal/file/WEBd7dc1d9d4d7f28d156704bd749cd93b7?method=download&shareKey=4c838768a6702ba92945ecfc0f8a5326)

- 用户在工具中打开一个文件，该工具通知语言服务器文档打开('textDocument/didOpen')。从现在起，有关文档内容不再位于文件系统上，而是保存在编辑开辟的一块内容中

- 用户进行编辑：该工具通知服务器文档更改('textDocument/didChange'),程序语义信息由语言服务器更新。发生这种情况时，语言服务器会分析此信息，并通知工具('textDocument/publishDiagnostics')检测到的错误和警告，并且还可能返回一些可能的用于补全的内容

- 用户对编辑器中的符号执行“转到定义”：该工具发送具有两个参数的"textDocument/definition"请求：(1)文档URI, (2)从服务器启动Go to definition请求的文本位置。服务器使用文档URI和符号定义在文档中的位置进行响应。客户端接到返回后，根据服务器标记的位置进行跳转

- 用户关闭文档(文件): 工具发送"textDocument/didClose"通知，通知语言服务器文档现在不再处于内存中，并且将当前内容保存到文件系统中。


#### coc.nvim插件

github wiki文档：
https://github.com/neoclide/coc.nvim/wiki

##### 1. 安装

1. 安装nodejs

coc.nvim依赖node.js, 首先安装nodejs
```
brew install nodejs
```

2. 安装插件coc.nvim

在.vimrc中增加配置:
```
Plug 'neoclide/coc.nvim', {'branch': 'release'}

```

在vim安装与查看安装情况
```
:PlugInstall
:PlugStatus
:CocInfo 查看coc安装状态，显示版本信息，安装路径、日志等
```

3. 安装C/C++语言LSP

下载安装包 https://github.com/clangd/clangd/releases

clangd-mac-14.0.3.zip

解压到 /opt/下, ``` ln -s /opt/clangd-mac-14.0.3/bin/clangd /usr/local/bin ```

``` clangd -h ``` 时提示权限问题，在setting中打开security配置，允许anyway即可

在vim里安装coc-clangd扩展
```
:CocInstall coc-clangd   ## 安装C/C++/ObjectC扩展
```
其它语言扩展

https://github.com/neoclide/coc.nvim/wiki/Using-coc-extensions


4. coc-marketplace

https://github.com/fannheyward/coc-marketplace

coc本身并不提供具体语言的补全功能，更多的只是提供一个补全功能的平台，所以在安装完成后，我们需要安装具体的语言服务以支持对应的补全功能。需要在vim中使用```:CocInstall```来安装子插件及相关依赖。

如```:CocInstall coc-json``` 支持JSON的子插件。


要检索都有哪些子插件可以直接在[NPM上查找coc.vim](https://www.npmjs.com/search?q=keywords%3Acoc.miniBufExplMapWindowNavVim), 更好的是使用[coc-marketplace](https://github.com/fannheyward/coc-marketplace), 直接在VIM里面进行管理，安装命令如下：
```
:CocInstall coc-marketplace
```

安装后用```:CocList marketplace``` 打开面板，```Tab ```可对高亮的子插件进行安装卸载等操作。

```
# 打开面板
:CocList marketplace

# 搜索python相关子插件
:CocList marketplace python
```
用上下键选择，按Tab进行对应操作

常用的子插件列表 https://github.com/neoclide/coc.nvim/wiki/Using-coc-extensions#implemented-coc-extensions

补充：

查看当前安装的所有插件： ```:coclist extension ```
	- 浏览 Ctrl+j/k navigate all extensions 
	- 卸载，禁用插件等 Tab
	- 退出: ESC
	- 星号表示正在当前文件启用
	- 方号表示已经安装, 只不过当前文件没有使用中

5. coc常用配置

Tab, Shift+Tab切换自动补全生效
```
" Use tab for trigger completion with characters ahead and navigate.
" NOTE: Use commmand ':verbose imap <tab>' to make sure tab is not mapped by 
" other plugin before putting this into your config.
inoremap <silent><expr> <TAB>
	\ pumvisible() ? "\<C-n>" : 
	\ <SID>check_back_space() ? "\<TAB>" : 
	\ coc#refresh()
inoremap <expr><S-TAB> pumvisible() ? "\<C-p>" : "\<c-h>"

function! s:check_back_space() abort
  let col = col('.') - 1
  return !col || getline('.')[col -1] =~# '\s'
endfunction

```
使用回车确认补全，而不是换行。
```
" Make <CR> auto-select the first completion item and notify coc.nvim to
" format on enter, <cr> could be remapped by other vim plugin
inoremap <silent><expr> <cr> pumvisible() ? coc#_select_confirm()
	\ : "\<C-g>u\<CR>\<c-r>=coc#on_enter()\<CR>"
```

下一个报错，上一个报错
```
" Use `[g` and `]g` to navigate diagnostics
" Use `:CocDiagnostics` to get all diagnostics of current buffer in location list.
nmap <silent> [g <Plug>(coc-diagnostic-prev)
nmap <silent> ]g <Plug>(coc-diagnostic-next)
```

查看函数定义，调用
```
" GoTo code navigation.
nmap <silent> gd <Plug>(coc-definition)
nmap <silent> gy <Plug>(coc-type-definition)
nmap <silent> gi <Plug>(coc-implementation)
nmap <silent> gr <Plug>(coc-references)
```

 Shortcut | Action
---|---
``` Space y ``` | Get yank history list
``` gd ``` | Go to definition
``` gr ``` | List references 
``` gi ``` | List implementation 
``` gy ``` | Go to type definition 


显示文档
```
" Use Leader+h to show documentation in preview window.
nnoremap <silent> <LEADER>h :call <SID>show_documentation()<CR>

function! s:show_documentation()
  if (index(['vim','help'], &filetype) >= 0)
    execute 'h '.expand('<cword>')
  elseif (coc#rpc#ready())
    call CocActionAsync('doHover')
  else
    execute '!' . &keywordprg . " " . expand('<cword>')
  endif
endfunction
```

highlighting相同单词，可以使用vim - illuminate
```
" Highlight the symbol and its references when holding the cursor.
autocmd CursorHold * silent call CocActionAsync('highlight')
```

重命名
```
" Symbol renaming.
nmap <leader>rn <Plug>(coc-rename)
```



