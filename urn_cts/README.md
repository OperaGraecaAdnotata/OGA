# URN CTS

This folder contains files with bibliographic information for the texts
included in *Opera Graeca Adnotata*.

The file `texts/urn_cts.xml` has been created automatically by using the
information contained in the `__cts__.xml` files in the original repositories
(see the folder `../original_Greek_files`). This information is not always
consistent (e.g., different languages used for work titles).

This folder also contains information extracted from the Perseus catalogue:
`texts/cts_urn_author_work.json` and `texts/tlg.txt`. These files have not
been used for *Opera Graeca Adnotata*.

The file `texts/table_author_work_urn-cts.md` is created to show the possible
values for the Annis Query Language attributes
`@* author=`, `@* title=`, `@* urn_cts=`, and `cts=`:
read `../relannis/README.md` for more information.

TO DO:
- [ ] create a file with checked information about author, title,
and date of a work (`texts/urn_cts_edited.xml`)
