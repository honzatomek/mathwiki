# Contents

    - [Setup guide for note taking in Vim and LaTeX](#Setup guide for note taking in Vim and LaTeX)
    - [Requirements](#Requirements)
        - [VIM](#Requirements#VIM)
        - [pdf reader](#Requirements#pdf reader)
        - [LaTeX](#Requirements#LaTeX)
    - [python code](#python code)
        - [Pygments](#python code#Pygments)
        - [LaTeX setup](#python code#LaTeX setup)

# Setup guide for note taking in Vim and LaTeX
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

## LaTeX
```bash
sudo apt install texlive
sudo apt install latexmk
```

# python code
## minted package
```bash
sudo apt install texlive-latex-extra
sudo apt install python3-pygments
```

## Pygments
```bash
pip install Pygments
```

## vimtex setup
```vim
let g:vimtex_compiler_latexmk = {
    \ 'build_dir' : '',
    \ 'callback' : 1,
    \ 'continuous' : 1,
    \ 'executable' : 'latexmk',
    \ 'hooks' : [],
    \ 'options' : [
    \   '-verbose',
    \   '-shell-escape',
    \   '-file-line-error',
    \   '-synctex=1',
    \   '-interaction=nonstopmode',
    \ ],
    \}
```
the `-shell-escape` option is required for the `python minted` package to display
python


## LaTeX setup
document preamble
```tex
\usepackage{minted}
```

set up format:
```tex
\setminted[python]{breaklines, framesep=2mm, fontsize=\footnotesize, numbersep=5pt}
% creates \begin{python} ... \end{python} definition
\newminted[python]{python}{linenos=true,
                           frame=lines,
                           baselinestretch=1.2,
                           mathescape,
                           xleftmargin=1cm,
                           framesep=2mm,
                           fontsize=\footnotesize}
```

write code in blocks:
```tex
\begin{minted}{python}

\end{minted}
```

