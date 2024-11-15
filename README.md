# Opera Graeca Adnotata v0.2.0

This repository contains some files used to create 
**Opera Graeca Adnotata** (OGA), a multilayer corpus
of Greek texts (base texts: 1,999 files and 40M+ tokens) 🏋️‍❤️😃

Because of its large size,
the actual corpus data are made available on Zenodo at

* https://doi.org/10.5281/zenodo.8158675

Detailed information on the corpus can be found 
in the article https://arxiv.org/abs/2404.00739.

An overview can also be read in the accompanying website at

* https://varro.informatik.uni-leipzig.de/oga/en/index.html

The data can also be queried via the Annis search tool at:

* https://annis.varro.informatik.uni-leipzig.de/

The present repository contains a few
useful manually annotated files used to create annotations in OGA, 
whose error correction anyone can contribute to here. 

The original Greek texts in OGA
have been tokenized, sentence segmented, morphosyntactically annotated
using a standoff format, which allows for smooth
expansion of the corpus via addition of any kind of annotation layer. 
The current release (v0.1.0) also contains annotation layers that allow searching for
author, work title, CTS URN, and passage.

The present repository is organized thus (further details within each folder):
1. `abbreviations` contains a file useful for tokenization.
2. `annotation_example` contains an unzipped example of the
annotation layers, which is useful for inspection.
3. `elision` contains a file used for tokenization.
4. `tokenize` contains files used for tokenization.
5. `urn_cts` contains files with bibliographic information
about the texts in OGA.
6. `work_chronology` contains a file with the alleged composition dates
of Greek works. This file has not been used for OGAv0.1.0.

## Citation

If you use OGA or material within this repository, please cite it so:

```
Giuseppe G. A. Celano. Opera Graeca Adnotata: Building a 34M+ Token Multilayer Corpus for Ancient Greek. arXiv https://arxiv.org/abs/2404.00739.
```

```
@misc{celano2024operagraecaadnotatabuilding,
      title={Opera Graeca Adnotata: Building a 34M+ Token Multilayer Corpus for Ancient Greek}, 
      author={Giuseppe G. A. Celano},
      year={2024},
      eprint={2404.00739},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2404.00739}, 
}
```
Direct citation of the corpus is: 

```
Giuseppe G. A. Celano. 2023. Opera Graeca Adnotata (v0.1.0). Zenodo.
https://doi.org/10.5281/zenodo.8158675
```
```
@misc{celanoOGA010,
author = {Giuseppe G. A. Celano},
title =  {Opera Graeca Adnotata},
year = {2023},
publisher = {Zenodo},
version = {v0.1.0},
doi = {10.5281/zenodo.8158675},
url = {https://doi.org/10.5281/zenodo.8158675}
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

The license is the same as that of the original texts (as required by
their license: follow the links in `original_Greek_files/README.md`
in the above-mentioned Zenodo repository for more details):

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">
<img alt="Creative Commons License" style="border-width:0" 
src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br/>
This work is licensed under a <a rel="license" 
href="http://creativecommons.org/licenses/by-sa/4.0/">
Creative Commons Attribution-ShareAlike 4.0 International License</a>.
