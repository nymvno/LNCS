# Simplified LNCS Template [![Build Status](https://circleci.com/gh/latextemplates/LNCS/tree/master.svg?style=shield)](https://circleci.com/gh/latextemplates/LNCS/)

> Quick start for modern LaTeXing with [LNCS](http://www.springer.com/computer/lncs).

## TOC

<!-- toc -->

- [Features](#features)
- [Background](#background)
- [Quick start](#quick-start)
- [Tool hints](#tool-hints)
- [Using the template with your git repository](#using-the-template-with-your-git-repository)
- [Warnings on ShareLaTeX](#warnings-on-sharelatex)
- [Development](#development)
- [Links](#links)

<!-- tocstop -->

## Features

 * Provides a skeletal [paper.tex](paper.tex) file.
 * Generated PDF allows for copy and paste of text without getting words with ligatures such as "workflow" destroyed.
   This is enabled by the [cmap] package, which encodes ligatures (such as fl) using unicode characters.
 * Automatic setting of "Fig." and "Section"/"Sect." according to the LNCS style.
   Just use `\Cref{sec:xy}` at the beginning of a sentence and `\cref{sec:xy}` in the middle of a sentence.
   Thanx to [cleveref].
 * Support of hyperlinked references without extra color thanx to [hyperref].
 * Better breaking of long URLs.
 * Sharper font (still compatible with Springer's requirements).
 * Support for `\powerset` command.
 * Support todos as pdf annotations. This is enabled by the [pdfcomment] package.
 * [microtypographic extensions](https://www.ctan.org/pkg/microtype) for a better look of the paper.
 * Adds modern packages such as [microtype], [cleveref], [csquotes], [paralist], [hyperref], [hypcap], [cfr-lm]
 * Optional: Support for [minted] package. Uncomment `\usepackage{minted}` to get started.

## Background

The official template is available at <http://www.springer.com/computer/lncs?SGWID=0-164-6-793341-0>.
Deep link: <ftp://ftp.springernature.com/cs-proceeding/llncs/llncs2e.zip>.
The files are also provided at Springer's FTP server at ftp://ftp.springer.de/pub/tex/latex/llncs/latex2e/.

> **Two files of Springer are needed to get the template working:**
> `llncs.cls` and `splncs03.bst`
>  You get them from ftp://ftp.springer.de/pub/tex/latex/llncs/latex2e/llncs.cls and ftp://ftp.springer.de/pub/tex/latex/llncs/latex2e/splncs03.bst or
> inside the ZIP of `llncs2e.zip` available at <ftp://ftp.springernature.com/cs-proceeding/llncs/llncs2e.zip>.

Reason: Licensing restrictions of Springer do not allow distribution outside of springer.
See [message #47 for debian bug 31897](https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=31897#47) for details.
Therefore, the required files `llncs.cls` and `splncs03.bst` have to be downloaded in some way.
Follow the quick start instructions.

## Quick start

 * Click on `Download ZIP` or [here](https://github.com/latextemplates/LNCS/archive/master.zip).
 * Extract `master.zip` in the folder where you want to write your paper.
 * Place `llncs.cls` and `splncs03.bst` into the directory
   - Download `llncs2e.zip` from <ftp://ftp.springernature.com/cs-proceeding/llncs/llncs2e.zip> and extract it in the directory.
     On Linux, just execute `download-llncs-files-from-springer.sh`.
   - In case ftp does not work at your side, you can try online ftp services such as http://www.net2ftp.com/ to download the files. Open the connection to `ftp.springer.de` and navigate to `pub`, `text`, `latex`, `llncs`, `latex2e`, and download the two files.
 * Edit [paper.tex](paper.tex).
 * `latexmk paper`.

## Tool hints

There is currently no official biblatex support.
A first step towards that is done at [biblatex-lncs](https://github.com/neapel/biblatex-lncs/).

MiKTeX installation hints are given at <https://github.com/latextemplates/scientific-thesis-template/blob/template/README.md#installation-hints-for-windows>.

Grammar and spell checking is available at [TeXstudio].
Please download [LanguageTool] and [configure TeXstudio to use it](http://wiki.languagetool.org/checking-la-tex-with-languagetool#toc4).
Note that it is enough to point to `languagetool.jar`.
Use [JabRef] to manage your bibliography.

If TeXstudio doesn't fit your need, check [the list of all available LaTeX Editors](http://tex.stackexchange.com/questions/339/latex-editors-ides).

In case you want to get started using minted, please install python and pygments.
Then, run pdflatex with the `-shell-escape` switch:
- `choco install python`
- `pip instal pygments`
- `pdflatex -shell-escape paper` (or just `latexmk paper`)

## Using the template with your git repository

1. Initialize your git repository as usual
2. Add this repository as upstream: `git remote add upstream https://github.com/latextemplates/LNCS.git`
3. Merge the branch `upstream/master` into your `master` branch: `git merge upstream/master`.

After that you can use and push the `master` branch as usual.
Notes on syncing with the upstream repository [are available from GitHub](https://help.github.com/articles/syncing-a-fork/).

## Warnings on ShareLaTeX

ShareLaTeX might output following warning:

> LaTeX Warning: You have requested, on input line 8, version
> 2015/06/24' of document class llncs, but only version 2004/08/17 v2.14
> LaTeX document class for Lecture Notes in Computer Science'
> is available.

The reason is that you did not download `llncs.cls` from <ftp://ftp.springer.de/pub/tex/latex/llncs/latex2e/>, but you did get if from somewhere else.
Please use the latest version offered by Springer.

## Development

- Reindent: `latexindent -y="indentPreamble:1,defaultIndent:'  '" -m -w paper.tex`

## Links

 * German: Hinweise zu Ausarbeitungen: http://wiki.flupp.de/studium/ausarbeitungen
 * Other templates: http://latextemplates.github.io/

  [cfr-lm]: https://www.ctan.org/pkg/cfr-lm
  [cleveref]: https://ctan.org/pkg/cleveref
  [cmap]: https://www.ctan.org/pkg/cmap
  [csquotes]: https://www.ctan.org/pkg/csquotes
  [hypcap]: https://www.ctan.org/pkg/hypcap
  [hyperref]: https://ctan.org/pkg/hyperref
  [microtype]: https://ctan.org/pkg/microtype
  [minted]: https://ctan.org/pkg/minted
  [paralist]: https://www.ctan.org/pkg/paralist
  [pdfcomment]: https://www.ctan.org/pkg/pdfcomment

  [JabRef]: https://www.jabref.org
  [LanguageTool]: https://languagetool.org/
  [TeXstudio]: http://texstudio.sourceforge.net/

  [llncs2e.zip]: ftp://ftp.springernature.com/cs-proceeding/llncs/llncs2e.zip
