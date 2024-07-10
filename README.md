# Opera Graeca Adnotata

This repository contains some files used to create 
a multilayer corpus
of Greek texts, **Opera Graeca Adnotata** 
(base texts: 1,687 files and 34,172,140 tokens)
(see also
the website http://oga.informatik.uni-leipzig.de/en/index.html). 🏋️‍❤️😃

Because of the large size of the data, this repository contains a few
manually annotated files used to create the annotations, 
whose version control can be useful. 
The actual corpus data are made available on Zenodo at

* https://doi.org/10.5281/zenodo.8158675

The original Greek texts (see `original_Greek_files/merge`)
have been tokenized, sentence segmented, morphosyntactically annotated
using a standoff format, which allows for smooth
expansion of the corpus via addition of any kind of annotation layer.
The current release also contains annotation layers that allow searching for
author, work title, CTS URN, and passage.

The repository is organized thus (further details within each folder):
1. `abbreviations` contains a file useful for tokenization.
2. `annotation_example` contains an unzipped example of the
annotation layers, which is useful for inspection.
3. `elision` contains a file used for tokenization.
4. `tokenize` contains files used for tokenization.
5. `urn_cts` contains files with bibliographic information
about the texts in *Opera Graeca Adnotata*.

The present work should be cited so:

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

# Contact
Dr. Giuseppe G. A. Celano<br/>
Universität Leipzig<br/>
Institute of Computer Science, NLP<br/>
Augustusplatz 10<br/>
04109 Leipzig<br/>
Deutschland<br/>
*mysurname* at informatik.uni-leipzig.de<br/>

# Funder

<a href="http://www.dfg.de/index.jsp" target="_blank">
<img src="https://upload.wikimedia.org/wikipedia/commons/8/86/DFG-logo-blau.svg" 
width="" height="40" alt=""/>
</a>

(Project number: 408121292)

# Licence

The license is the same as that of the original texts (as required by
their license: follow the links in `original_Greek_files/README.md`
for more details):

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">
<img alt="Creative Commons License" style="border-width:0" 
src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br/>
This work is licensed under a <a rel="license" 
href="http://creativecommons.org/licenses/by-sa/4.0/">
Creative Commons Attribution-ShareAlike 4.0 International License</a>.
