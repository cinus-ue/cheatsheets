# VIM CHEAT SHEET

## CONFIGURATIONS 
```
set number
set nonumber
set textwidth=150
set incsearch
set hlsearch
```
## NAVIGATING
```
h   Move left H Top line on screen
j   Move down M Middle line on screen
k   Move up L Bottom line on screen
l   Move right
10j Move down 10 lines

gg  First line of the file e The end of the current word
G   Last line of the file b Beginning of current word
:20 Line 20 of the file w Beginning of next word

0   Beginning of current line
^   First non-whitespace character of current line
$   End of current line
```
## SEARCH
```
*   Find the next instance of the current word
#   Find the previous instance of the current word
n   Find the next instance of the word being searched for, in the direction specified by
    the last use of {*,#}
N   Find the previous instance of the word being searched for, in the direction specified
    by the last use of {*,#}
/word     Find the next occurrence of ‘word’
/word\c   Find the next occurrence of ‘word’, ignoring case
/\<word\> Find the next occurrence of the word ‘word’, where ‘word’ is bounded by word
boundaries (ex. space, dash)
:noh      Un-highlight words
```