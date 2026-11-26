# tkz-euclide — Euclidean Geometry with TikZ
Release 5.15c — 2026/11/26

## Description

`tkz-euclide` is a LaTeX package for drawing two-dimensional Euclidean
geometric figures. It uses a Cartesian orthonormal coordinate system
(unit = 1 cm) and provides tools to define points and manipulate them.
The goal is to reproduce, step by step, constructions as they would be
done by hand, in the most natural way possible.

Recent updates:
- **`lua` option**: most calculations can now be performed using Lua.
- **`mini` option**: when `tkz-euclide` is used together with
  [`tkz-elements`](https://ctan.org/pkg/tkz-elements), this option lets
  `tkz-euclide` focus only on the drawings. Some macros, such as those in the `tkz-draw-eu-show.tex` file, still require the use of the complete package.

## License

This package is released under the
[LaTeX Project Public License](https://www.latex-project.org/lppl/),
version 1.3c or later.

## Requirements

`tkz-euclide` requires LaTeX with UTF-8 input and works with both
**pdfLaTeX** and **LuaLaTeX**. It depends on up-to-date versions of:

- [xfp](https://ctan.org/pkg/xfp)
- [tikz](https://ctan.org/pkg/tikz)

## Installation

The package is available on **TeX Live** and **MiKTeX**. Use your package
manager to install it.

For local testing, place the distribution files in the same directory as
your `.tex` file. For permanent installation, move the files into your
local `TEXMFHOME` or system `TDS` tree.

## Usage

Add the following lines to your preamble:

```latex
\usepackage{tkz-euclide}

\begin{document}
\begin{tikzpicture}
  % your code here
\end{tikzpicture}
\end{document}


## Author

Alain Matthes, 5 rue de Valence, Paris 75005, al (dot) ma (at) mac (dot) com
