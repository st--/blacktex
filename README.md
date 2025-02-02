<p align="center">
  <a href="https://github.com/texworld/blacktex"><img alt="blacktex" src="https://texworld.github.io/blacktex/logo.svg" width="60%"></a>
  <p align="center">Clean up your LaTeX files.</p>
</p>

[![PyPi Version](https://img.shields.io/pypi/v/blacktex.svg?style=flat-square)](https://pypi.org/project/blacktex/)
[![PyPI pyversions](https://img.shields.io/pypi/pyversions/blacktex.svg?style=flat-square)](https://pypi.org/project/blacktex/)
[![GitHub stars](https://img.shields.io/github/stars/texworld/blacktex.svg?style=flat-square&logo=github&label=Stars&logoColor=white)](https://github.com/texworld/blacktex)
[![PyPi downloads](https://img.shields.io/pypi/dm/blacktex.svg?style=flat-square)](https://pypistats.org/packages/blacktex)

blacktex is a command-line tool that helps with article editing in LaTeX. It
removes all comments from a given file and corrects [some common
anti-patterns](http://mirrors.ctan.org/info/l2tabu/english/l2tabuen.pdf).

Install with one of

```
pip install -U blacktex
```

Then, with

```
blacktex in.tex > out.tex
```

the input file

```latex
Because   of $$a+b=c$$ ({\it Pythogoras}),
% @johnny remember to insert name
and $y=2^ng$ with $n=1,...,10$, we have ${\Gamma \over 2}=8.$
```

is converted to

```latex
Because of
\[
a+b = c
\]
(\textit{Pythogoras}),
and \(y = 2^n g\) with \(n = 1,\dots,10\), we have \(\frac{\Gamma}{2} = 8\).
```

You can use

```
blacktex -i in0.tex in1.tex ...
```

to modify files in-place. See `blacktex -h` for all options.
