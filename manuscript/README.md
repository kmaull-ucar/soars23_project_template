# Manuscript

You can write your manuscript in a variety of tools, but one way to keep all of your things in one place, is to place a PDF (or a text version of the document) in Github.

This will allow for a more complete presentation of your research.

You may also consider writing your manuscript in LaTeX or Markdown, both of which are easy to manage in Github, and are also easy to convert to various formats once done.

## Example
The example manuscript here is written in Markdown to show a different distraction-free workflow that will involve a text editor and Pandoc.  It is also possible to write in another tool and convert to markdown for final deployment and publication, but the reason you may want to start in Markdown is that it will be easily trackable in git/Github from inception.

There are many other ways to do it ... this is just one that I like because of the **simplicity**, **portability** and **traceability** out of the gate.

* [manuscript.md](./manuscript.md): an example paper in Markdown (generated with the very fun [Mathgen (https://thatsmathematics.com/mathgen/)](https://thatsmathematics.com/mathgen/) nonsense paper generator)
* [manscript.pdf](./manscript.pdf): a PDF generated from the Markdown using [Pandoc (https://pandoc.org)](https://pandoc.org)

This command line will do it:
```bash
$ pandoc \
    --citeproc \
    --csl=ieee.csl \
    manuscript.md -o manuscript.pdf
```

OR just use the same script in [./build.sh](./build.sh), and run `./build.sh` from your terminal (remember to make the file executable!).

* the source file can be found here: [./manuscript.md](./manuscript.md)
* the output pdf can be found here: [./manuscript.pdf](./manuscript.pdf)

You will also note that the `.bib` file is automatically consumed within the Markdown document making it trivial to include citations generated from [Zotero](https://zotero.org).

The manifest of the Markdown document includes useful information:

```markdown

---
title: |
  \obeylines
  Galois Categories over Planes
author: "Lorm Fakknum"
date: |
  August 21, 2027
  \tiny last updated: Today
geometry: margin=1in
fontsize: 11pt
output: 
    pdf_document:
        citation_package: natbib
fontfamily: mathpazo
bibliography: scigenbibfile.bib
custom: libertinust1math,libertine
abstract:
 Let $| \Phi | = \pi$ be arbitrary.  Recent developments in classical group theory \cite{cite:0} have raised the question of whether $\mathcal{{K}} ( \hat{\mathfrak{{e}}} ) \le \infty$.  We show that there exists a pseudo-abelian algebra.  In this setting, the ability to characterize topoi is essential. The goal of the present article is to derive locally positive equations. 
---

```

Minimally, include the title, author, bibliography (the bibtex file) and abstract.  Tweak the other paramaters as you see fit.

The citation style used was IEEE, but you may need to download the correct `csl` file from here:  [https://github.com/citation-style-language/styles](https://github.com/citation-style-language/styles).  Learn more here: [https://citationstyles.org/](https://citationstyles.org/)

**NOTE:** the advantage of this method is that you can now output your single markdown to a number of formats, including HTML, Word `.docx`, LaTeX `.tex.` (among others) to distribute to different platforms.