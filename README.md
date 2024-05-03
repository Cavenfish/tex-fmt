# tex-fmt

[![CI](
https://github.com/wgunderwood/tex-fmt/actions/workflows/flake.yml/badge.svg)](
https://github.com/wgunderwood/tex-fmt/actions/workflows/flake.yml)
[![crates.io](
https://img.shields.io/crates/v/tex-fmt?logo=rust)](
https://crates.io/crates/tex-fmt)
[![license: MIT](
https://shields.io/badge/license-MIT-blue.svg)](
https://mit-license.org/)

A LaTeX formatter written in Rust.

<table width="100%">
<tr>
<td>
<b>Input</b>
</td>
<td>
<b>Output</b>
</td>
</tr>
<tr>
<td>

``` tex
\begin{document}

\begin{itemize}
\item Lists with items
over multiple lines
\end{itemize}

\begin{align}
E = m c^2
\end{align}

\end{document}
```
</td>
<td>

``` tex
\begin{document}

\begin{itemize}
  \item Lists with items
    over multiple lines
\end{itemize}

\begin{align}
  E = m c^2
\end{align}

\end{document}
```
</td>
</tr>
</table>

- ⚡ Very good run-time performance
- 🔧 No configuration necessary
- 📟 Command-line interface
- 📜 Handles LaTeX file types `.tex`, `.bib`, `.cls`, and `.sty`
- 🦀 Written entirely in safe Rust

## Installation

### Nix

``` shell
nix build "github:wgunderwood/tex-fmt"
```

### Cargo

``` shell
cargo install --git "https://github.com/wgunderwood/tex-fmt"
```
## Performance

Run `perf.sh` to format all test cases.
For large files, tex-fmt is hundreds of times faster than latexindent.

| **Files** | **Lines** | **Size** | **tex-fmt** | **latexindent** | **latexindent -m** |
| --- | --- | --- | --- | --- | --- |
| 14 | 33k | 948kb | **0.0392s** | 14.5s [x369] | 18.7s [x478] |

## Limitations

- Semantic parsing of LaTeX code not conducted
- No linting or correction of syntax errors
- Customization via configuration files not supported
- Compliance with existing formatting guidelines not guaranteed
- Editor integration not currently provided
- No spell checking

## Existing tools

- [latexindent](https://github.com/cmhughes/latexindent.pl).
Perl script, many configuration options, slow on large files.

- [LaTeXTidy](http://bfc.sfsu.edu/cgi-bin/hsu.pl?LaTeX_Tidy).
Perl script, download links seem to be broken.

- [latex-pretty](https://c.albert-thompson.com/latex-pretty/).
Browser-based, uses latexindent as the backend.

- [latexformat.com](https://latexformat.com/).
Browser-based.

- [texpretty](http://ftp.math.utah.edu/pub/texpretty/).
C program which works sometimes and appears to be fast.
Fails with certain keywords inside brackets.

- [latex-editor](https://latex-editor.pages.dev/formatter/).
Browser-based.

- [LaTeXFmt](https://github.com/engeljh/vim-latexfmt).
Vim plugin, does not apply indentation.

- [latex-formatter](https://github.com/nfode/latex-formatter).
Visual Studio plugin, uses latexindent as the backend.
