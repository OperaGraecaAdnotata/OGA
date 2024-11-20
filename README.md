# Opera Graeca Adnotata v0.2.0

This repository contains the documentation for
**Opera Graeca Adnotata** (OGA), a multilayer corpus
of Ancient Greek texts with automatically generated annotations
(the largest one of its kind) 🏋️❤️😃:

* number of base texts: **1,999**, each corresponding to an ancient work
* number of tokens: **40,105,221**

The Ancient Greek works comprised in OGA come from the GitHub repositories:

* [Canonical Greek (release 0.0.11376425141)](https://github.com/PerseusDL/canonical-greekLit/releases/tag/0.0.11376425141)
* [First1KGreek (release 1.1.11352615003)](https://github.com/OpenGreekAndLatin/First1KGreek/releases/tag/1.1.11352615003)
* [PatristicTextArchive (release 1.1.11363682704)](https://github.com/PatristicTextArchive/pta_data/releases/tag/1.1.11363682704)

In general, OGA contains one edition for each work, with 90 exceptions
documented in [urn_cts/texts/duplicates_tlg_pta.xml](https://github.com/OperaGraecaAdnotata/OGA/blob/main/urn_cts/texts/duplicates_tlg_pta.xml). The list
of all texts included in OGA is in [urn_cts/texts/urn_cts_plus_date_label.xml](https://github.com/OperaGraecaAdnotata/OGA/blob/main/urn_cts/texts/urn_cts_plus_date_label.xml).

Because of the corpus large size,
the actual corpus data and its documentation
are made available on Zenodo at

* https://doi.org/10.5281/zenodo.8158675

The data can be queried (also) through the ANNIS 4 search tool at:

* https://annis.varro.informatik.uni-leipzig.de/oga020

To know more about how to query the corpus with Annis,
see the documentation in the folder `query`, where examples can be
found.

ANNIS can also be easily run on a desktop computer: consider to use the
desktop version with the data (~21G) made available in Zenodo.

An overview of the corpus can be read on the accompanying website at

* https://varro.informatik.uni-leipzig.de/oga/en/index.html

The present repository contains a few
useful manually annotated files used to create annotations in OGA,
whose expansion and correction anyone can contribute to by opening
a GitHub Issue or Discussion. 

The corpus can be queried by:

1. word form (i.e., token)
2. lemma
3. morphology (POS and morphological features)
4. syntax (dependency syntax following the AGDT annotation scheme)
5. CTS URN for work, author, and edition
6. CTS passage for each work (e.g., "book", "section", etc.) 
6. author name
7. work title
8. alleged composition date for each work
9. (experimental) IPA transcription of word form (the 5th BCE Attic one)

The morphosyntactic annotation and lemmatization are the outputs of
(i) a parser and (ii) lemmatizer trained on 1,2M+ tokens of AGDT data 
(a much larger dataset than all UD ones combined): the
parser and lemmatizer are documented in the article 
[A State-of-the-Art Morphosyntactic Parser and Lemmatizer for Ancient Greek](https://arxiv.org/abs/2410.12055). Since the training dataset contained 
a large selection of texts of different centuries and genres, 
the models used for OGA are expected to generalize much
better than the existing ones trained on much smaller (UD) datasets. 
The final scores for the models are:

|POS|XPOS|Feats|ALLTags|UAS|LAS|Lemmas|
|-----|-----|----|----|----|----|----|
|96.41|91.90|94.77|91.56|82.60|77.10|91.41|

The annotations for CTS URN, CTS passage, author name, and work title are
retrieved automatically from the original texts (and therefore they may
contain errors and inconsistencies).

The annotation for work composition dates has been done manually and 
is work-in-progress 
(see `work_chronology/chronology_greek_works.xml`).

The IPA transcription is based on a ByT5 model that achieved an accuracy
of **0.83** (correct IPA transcriptions) on Greek and Latin data 
from Wiktionary. The IPA transcription is the 5th BCE Attic, like the one
for [ἄξιοι](https://en.wiktionary.org/wiki/%E1%BC%84%CE%BE%CE%B9%CE%BF%CE%B9#Ancient_Greek).

The present repository is organized thus (further details within each folder):
1. `abbreviations` contains a file useful for tokenization
2. `annotation_example` contains an unzipped example of the
annotation layers, which is useful for inspection
3. `elision` contains a file used for tokenization
4. `query` contains information to query the corpus
5. `tokenize` contains files used for tokenization
6. `urn_cts` contains files with bibliographic information
about the texts in OGA
7. `work_chronology` contains a manually annotated file with 
the alleged composition dates of Greek works, which continues to be updated

## Citation

If you use OGA v0.2.0 or material within this repository, please cite it thus
(the following article describes an earlier version of OGA, i.e., v0.1.0, but
is still relevant):

```
Giuseppe G. A. Celano. Opera Graeca Adnotata: Building a 34M+ Token Multilayer Corpus for Ancient Greek. arXiv https://arxiv.org/abs/2404.00739.
```

```
@misc{celano2024operagraecaadnotatabuilding,
      title=         {Opera Graeca Adnotata: Building a 34M+ Token Multilayer Corpus for Ancient Greek}, 
      author=        {Giuseppe G. A. Celano},
      year=          {2024},
      eprint=        {2404.00739},
      archivePrefix= {arXiv},
      primaryClass=  {cs.CL},
      url=           {https://arxiv.org/abs/2404.00739}, 
}
```
Direct citation of the corpus is: 

```
Giuseppe G. A. Celano. 2023. Opera Graeca Adnotata (v0.2.0). Zenodo.
https://doi.org/10.5281/zenodo.8158675
```
```
@misc{celanoOGA010,
author =    {Giuseppe G. A. Celano},
title =     {Opera Graeca Adnotata},
year =      {2023},
publisher = {Zenodo},
version =   {v0.2.0},
doi =       {10.5281/zenodo.8158675},
url =       {https://doi.org/10.5281/zenodo.8158675}
}
```
## Contact
Dr. Giuseppe G. A. Celano<br/>
Universität Leipzig<br/>
Institute of Computer Science, NLP<br/>
Augustusplatz 10<br/>
04109 Leipzig<br/>
Deutschland<br/>
*mysurname* at informatik.uni-leipzig.de<br/>

## Funder

<a href="http://www.dfg.de/index.jsp" target="_blank">
<img src="https://upload.wikimedia.org/wikipedia/commons/8/86/DFG-logo-blau.svg" 
width="" height="40" alt=""/>
</a>

(Project number: 408121292)

## Licence

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">
<img alt="Creative Commons License" style="border-width:0" 
src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br/>
This work is licensed under a <a rel="license" 
href="http://creativecommons.org/licenses/by-sa/4.0/">
Creative Commons Attribution-ShareAlike 4.0 International License</a> (for more
details, look also at the repositories of the original texts mentioned above).
