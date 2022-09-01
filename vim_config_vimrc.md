#vim #config #vimrc

## vim config

~~~


filetype off " required

set rtp+=~/.vim/bundle/Vundle.vim

call vundle#begin()

Plugin 'VundleVim/Vundle.vim'

Plugin 'tpope/vim-fugitive'

Plugin 'git://git.wincent.com/command-t.git'

Plugin 'file:///home/gmarik/path/to/plugin'

Plugin 'rstacruz/sparkup', {'rtp': 'vim/'}

call vundle#end() " required

filetype plugin indent on " required

"filenames like *.xml, *.html, *.xhtml, ...

"These are the file extensions where this plugin is enabled.

"Plugin 'chiel92/vim-autoformat'

Plugin 'mattn/emmet-vim'

Plugin 'scrooloose/nerdtree'

"Plugin 'terryma/vim-multiple-cursors'

Plugin 'AutoComplPop'

Plugin 'ObserverOfTime/coloresque.vim'

"set notermguicolors

"set background=dark

Plugin 'alvan/vim-closetag'

"Plugin 'Yggdroot/indentLine'

Plugin 'sainnhe/sonokai'

Plugin 'jiangmiao/auto-pairs'

"Авто кавички

"Plugin 'eemed/sitruuna.vim"

"colorscheme sitruuna

"set background=light

"colorscheme PaperColor

"vim twig

"Plugin 'nelsyeung/twig.vim'

Plugin 'beautify-web/js-beautify'

Plugin 'maksimr/vim-jsbeautify'

map <c-j> :call HtmlBeautify()<cr>

"let g:closetag_filenames = '*.html,*.xhtml,*.phtml,*.php'

"let g:closetag_filetypes = 'html,xhtml,phtml,php'

"let g:closetag_emptyTags_caseSensitive = 1

"let g:closetag_shortcut = '>'

"let g:closetag_close_shortcut = '<leader>>'

call plug#begin('~/.vim/plugged')

"Plug 'junegunn/fzf', { 'do': { -> fzf#install() } }

"Plug 'junegunn/fzf.vim'

"autocomlete plug

"Plug 'ncm2/ncm2'

"Plug 'roxma/nvim-yarp'

"Plug 'ncm2/ncm2-bufword'

"Plug 'ncm2/ncm2-path'

"Plug 'phpactor/ncm2-phpactor

"Plug 'sbdchd/neoformat'

"Plug 'mhartington/formatter.nvim'

Plug 'NLKNguyen/papercolor-theme'

"Plug 'itchyny/lightline.vim'

" Snipets

Plug 'SirVer/ultisnips'

" Track the engine.

" Snippets are separated from the engine. Add this if you want them:

Plug 'honza/vim-snippets'

Plug 'sonph/onehalf'

" Trigger configuration. You need to change this to something other than <tab> if you use one of the following:

" - https://github.com/Valloric/YouCompleteMe

" - https://github.com/nvim-lua/completion-nvim

let g:UltiSnipsExpandTrigger="<tab>"

let g:UltiSnipsJumpForwardTrigger="<c-b>"

let g:UltiSnipsJumpBackwardTrigger="<c-z>"

" If you want :UltiSnipsEdit to split your window.

let g:UltiSnipsEditSplit="vertical"

" ---- потом розібратись "autocmd BufEnter * call ncm2#enable_for_buffer()

" IMPORTANT: :help Ncm2PopupOpen for more information

"enanle complete option

"set completeopt=noinsert,menuone,noselect

"autocmd BufEnter * call ncm2#enable_for_buffer()

"set completeopt=noinsert,menuone,noselect

call plug#end()

map <C-s> :UltiSnipsEdit<CR>

map <silent> <C-f> :Files<CR>

map <C-o> :NERDTreeToggle<CR>

let NERDTreeShowHidden=1

"map <C-j> :Neoformat<CR>

map <F2> :set nowrap<CR>

map <F3> :set wrap<CR>

map <F5> :set number<CR>

map <F6> :set nonumber<CR>

map <F4> :Autoformat<CR>

map <C-a> :Ag<CR>

nnoremap <silent> <PageUp> <PageUp>+<S-m>

nnoremap <silent> <PageDown> <PageDown>+<S-m>

"set number

syntax on

"set nowrap

set nocompatible " disable compatibility to old-time vi

set showmatch " show matching

set ignorecase " case insensitive

set mouse=v " middle-click paste with

set hlsearch " highlight search

set incsearch " incremental search

set tabstop=4 " number of columns occupied by a tab

set softtabstop=4 " see multiple spaces as tabstops so <BS> does the right thing

"set expandtab " converts tabs to white space

set shiftwidth=4 " width for autoindents

set autoindent " indent a new line the same amount as the line just typed

set wildmode=longest,list " get bash-like tab completions

"set cc=80 " set an 80 column border for good coding style

filetype plugin indent on "allow auto-indenting depending on file type

"set mouse=a " enable mouse click

set clipboard=unnamedplus " using system clipboard

filetype plugin on

set cursorline " highlight current cursorline

set ttyfast " Speed up scrolling in Vim

let g:indentLine_char_list = ['|', '¦', '┆', '┊']

map <C-u> :IndentLinesToggle<CR>

let g:indentLine_enabled = 0

"autocmd FileType javascript noremap <buffer> <c-f> :call JsBeautify()<cr>

"autocmd FileType json noremap <buffer> <c-f> :call JsonBeautify()<cr>

"autocmd FileType jsx noremap <buffer> <c-f> :call JsxBeautify()<cr>

"autocmd FileType html noremap <buffer> <c-f> :call HtmlBeautify()<cr>

"autocmd FileType css noremap <buffer> <c-f> :call CSSBeautify()<cr>

set t_Co=256

set background=dark

"colorscheme onehalflight

colorscheme PaperColor

"colorscheme sonokai

"set noignorecase

let g:user_emmet_leader_key=','

nnoremap <space> :nohlsearch<CR>

"keys для вводу на укр

"function SetUsLayout()

"!setxkbmap us,ua

"endfunction

"function SetUaLayout()

"!setxkbmap ua,us

"endfunction

"autocmd InsertLeave * call SetUsLayout()

"autocmd InsertEnter * call SetUaLayout()

"end of file

~~~