# (2021 / 9th) Fuel Science Center International Conference LaTeX Template

This repository contains the (unofficial) LaTeX template for the
Fuel Science: From Production to Propulsion (9th) International Conference.
This repository is a fork of the the [ECM/ESCI template](https://github.com/mefuller/ecm-latex-template),
which is forked from the [USSCI template](https://github.com/pr-omethe-us/ussci-latex-template) developed by Bryan W. Weber and Kyle E. Niemeyer.

## Instructions

1. Download a zip file of this repository and extract it
2. Open and try to build the `template.tex` file to make sure that everything works properly
3. If your references don't end up as numbers, make sure that your TeX environment/editor is set to use biber to compile the references. By default, most editors (such as TeXStudio) default to using BibTeX.
4. Copy the `template.tex` file and edit it to add your paper content.
5. Fill out and submit `CallPapersPosters.pdf` along with the abstract.

## Dependencies

The template uses the following packages that must be installed with their dependencies:

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
* xcolor

Additionally, to compile the "Call for Papers and Posters", we require:
* etoolbox
* graphicx
* helvet

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This <span xmlns:dct="http://purl.org/dc/terms/" href="http://purl.org/dc/dcmitype/Text" rel="dct:type">work</span> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.

## Tips and Tricks

### Figures and tables aren't displaying as intended?

Standard figure and table floats may not display as desired in the multicol environment.
Floats may be made to span the page using the * variants, e.g.
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
