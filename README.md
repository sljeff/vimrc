# vimrc
my own vimrc

## 内容
set nocompatible

set nu

set ts=4
set sts=4
set sw=4
set expandtab

"set smartindent
"set cindent
set autoindent

"set cursorline
"set cursorcolumn

set hlsearch
set incsearch

syntax enable
syntax on

set ignorecase smartcase

set encoding=utf-8
set termencoding=utf-8

inoremap ( ()<LEFT>
inoremap " ""<LEFT>
inoremap ' ''<LEFT>
inoremap [ []<LEFT>
inoremap { {}<LEFT><CR><CR><UP><TAB>

function! ClosePair(cchar)
    if getline('.')[col('.')-1] == a:cchar
        return "\<RIGHT>"
    else
        return a:cchar
    endif
endf

inoremap <expr> ) ClosePair(")")
inoremap <expr> ] ClosePair("]")
inoremap <expr> } ClosePair("}")

