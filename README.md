# Contents

    - [Setup guide](#Setup guide)
    - [Requirements](#Requirements)
        - [VIM](#Requirements#VIM)
        - [pdf reader](#Requirements#pdf reader)
        - [latex](#Requirements#latex)

# Setup guide
[castel](https://castel.dev/post/lecture-notes-1/#vim-and-latex)

# Requirements
## VIM
plugins:
- [vimtex](https://github.com/lervag/vimtex.git)
- [tex-conceal](https://github.com/KeitaNakamura/tex-conceal.vim.git)
- [ultisnips](https://github.com/SirVer/ultisnips.git)

.vimrc:
```vim
let g:tex_flavor='latex'
let g:vimtex_view_method='zathura'
let g:vimtex_quickfix_mode=0
```

## pdf reader
```bash
sudo apt install zathura
```

## latex
```bash
sudo apt install texlive
sudo apt install latexmk
```
