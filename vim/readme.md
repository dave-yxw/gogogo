## bundle配置
http://zuyunfei.com/2013/04/12/killer-plugin-of-vim-vundle/

* git clone https://github.com/gmarik/vundle.git ~/.vim/bundle/vundle
* 配置.vimrc。rtp对应vundle安装目录
<pre> 
set nocompatible                " be iMproved
filetype off                    " required!
set rtp+=~/.vim/bundle/vundle/
call vundle#rc()

" let Vundle manage Vundle
Bundle 'gmarik/vundle'

"my Bundle here:
"
" original repos on github
Bundle 'kien/ctrlp.vim'
Bundle 'sukima/xmledit'
Bundle 'sjl/gundo.vim'
Bundle 'jiangmiao/auto-pairs'
Bundle 'klen/python-mode'
Bundle 'Valloric/ListToggle'
Bundle 'SirVer/ultisnips'
Bundle 'Valloric/YouCompleteMe'
Bundle 'scrooloose/syntastic'
Bundle 't9md/vim-quickhl'
" Bundle 'Lokaltog/vim-powerline'
Bundle 'scrooloose/nerdcommenter'
"..................................
Bundle 'taglist.vim'
Bundle 'vimwiki'
Bundle 'winmanager'
Bundle 'Markdown'
Bundle 'c.vim'
Bundle 'snipMate'
Bundle 'SuperTab'
Bundle 'The-NERD-tree'
"..................................
filetype plugin indent on
</pre>
* 这里Bundle后面的语法：bundle分为三类：
	* 在Github vim-scripts 用户下的repos,只需要写出repos名称
	* 在Github其他用户下的repos, 需要写出”用户名/repos名”
	* 不在Github上的插件，需要写出git全路径

## YouCompleteMe的问题
* YouCompleteMe需要vim 7.4
* 需要源码安装 http://ftp2.tw.vim.org/pub/vim/unix/
* 安装需要配置python环境 ./configure --enable-pythoninterp --with-python-config-dir=/usr/lib/python2.7/config/
* 需要配置：
	* http://www.cnblogs.com/junnyfeng/p/3633697.html
	* 到 .vim/bundle/YouCompleteMe 下跑 ./install.sh --clang-completer
* 如果系统中有多个vim，需要alias vim到正确的vim

## 退格失效问题
* 修改 /etc/vim/vimrc.tiny
* set compatible 改成 set nocompatible
* 添加 set  backspace=2
* 如果不是insert状态，删除直接按X

网上有的方法里面，让修改/etc/vim/vimrc，其实这样也会修改vim(用vim命令)的配置，而当用 vim 命令启动时，只是读取vimrc，没有读取vim.tiny。所以只在vim.tiny做修改，只影响vi，不影响vim。
