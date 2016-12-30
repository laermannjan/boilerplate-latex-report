# Report Biolerplate
by @laermannjan

## Quick start
* find your (sub)section and start typing
* in pml-paper root do `make all` and find pdf in _output/report.pdf_
  * this also keeps your cwd clean for your convencience
  * git won't track compilation files anyways, though
  * _Note: this nullifies the effect of includes compilation boost
  if necessary we should probably rather compile in separate directory to have booth speed of compilation and a clean $root._
* when errors occur, you can find them in _$root/error.txt_
  * you may also want to run `make cleanup` to remove any possibly corrupt files
* run `make clean` to delete output dir to ensure updates (usually not necessary)

## Structure - logical
- Intro
- Topic 1: Introduction and Overview
- Topic 2: Techniques, Applicability,...
- Experiments: ...
- Discussion: Conclusion, Review, Future stuff,...

## Structure - technical
* **Report.tex** serves as root file
  * Add latex magic in your .tex files: `% !TEX root = ../path/to/report.tex`
  * **sections** directory contains top level sections _section_.tex files
    * Subsections should reside in a directory section/_section_/**subsection.tex**
    * top level sections are **included** `\include{sections/section}` without filetype
    * subsections (and deeper) use **input** `\input{sections/section/subsection}`
    * `\include` functionally adds `\clearpage` before and after it and technically forces separate .aux files to be introduced for sections -> much quicker recompile!
    * `\include` can't be nested
    * `\input` inputs AS is WHERE is!
* **label** conventions
  * (sub)section: `sec:name`
  * paragraph: `para:name`
  * code: `foo:handle`
  * figures: `fig:name`

## Bibliography
* [JabRef](http://www.jabref.org) recommended to maintain .bib
  * can do built-in arXiv, google scholar, ... search
  * bibtexkey convention: `firstauthorYEARdescriptiveword`

## Check this out
* [Git commit messages convention](https://github.com/agis-/git-style-guide#messages)
* [Draw the LaTeX symbol you want, get the latex representation!](http://detexify.kirelabs.org/classify.html)


## TODO
* for experiments thumb rule 1 -  2 - 1 - 2: 1 p intro, 2 p methods, 1 p results, 2 p discussion
* introduction and discussion
* ...
