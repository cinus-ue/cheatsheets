# VIM CHEAT SHEET

## CONFIGURATIONS 
```
set number              " show line numbers
set nonumber
set showcmd             " show command in bottom bar
        +-------------------------------------------------+
        |text in the Vim window                           |
        |~                                                |
        |~                                                |
        |-- VISUAL --                   2f     43,8   17% |
        +-------------------------------------------------+
         ^^^^^^^^^^^                  ^^^^^^^^ ^^^^^^^^^^
          'showmode'                 'showcmd'  'ruler'

set textwidth=150
set showmatch           " highlight matching [{()}]
set wildmenu            " visual autocomplete for command menu
set incsearch           " search as characters are entered
set hlsearch            " highlight matches
set nocompatible
set backspace=indent,eol,start
set history=200         " keep 200 commands and 200 search patterns in the history
set ruler
set incsearch           " display the match for a search pattern when halfway typing it
set nrformats-=octal    " do not recognize numbers starting with a zero as octal
```
