# (2021) European Combustion Meeting LaTeX Template

This repository contains the (unofficial) LaTeX template for the
European Sections of the Combustion Institute (ESCI).
This repository is a fork of the USSCI template developed by Bryan W. Weber and Kyle E. Niemeyer.
The source for the original template can be found online at https://github.com/pr-omethe-us/ussci-latex-template
This fork for the ECM/ESCI is hosted at https://github.com/mefuller/ecm-latex-template

## Instructions

1. Download a zip file of this repository and extract it
2. Open and try to build the `template.tex` file to make sure that everything works properly
3. If your references don't end up as numbers, make sure that your TeX environment/editor is set to use biber to compile the references. By default, most editors (such as TeXStudio) default to using BibTeX.
4. Copy the `template.tex` file and edit it to add your paper content

## Dependencies

The template uses the following
packages that must be installed with their dependencies:

* authblk
* biblatex
* biber
* calc
* fancyhdr
* fontenc
* geometry
* hyperref
* inputenc
* mathptmx
* multicol
* titlesec

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This <span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" rel="dct:type">work</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

## Tips and Tricks

### Figures and tables aren't displaying as intended?

Standard figure and table floats may not display as desired in the multicol environment.
Floats may either be made to span the page using the * variants, e.g.
```
\begin{figure*}
  % figure here (includegraphics or whatever)
  \caption{Figure description}
\end{figure*}
```

Alternatively, you may wish to define a new environment, e.g. the multicolumn figure (mcfigure):
```
\newenvironment{mcfigure}
	{\par\medskip\noindent\minipage{\linewidth}}
	{\endminipage\par\medskip}
```

To include captions in the new environment use the caption package:
```
\usepackage{caption}
...
\begin{mcfigure}
	% figure here (includegraphics or whatever)
	\captionof{figure}{Figure description}
\end{mcfigure}
```

### Column-width overruns

The interword spacing may be made increasingly elastic by adding ```\sloppy``` to the preamble.
This helps in cases where words are overrunning the column bounds.
