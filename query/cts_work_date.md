# CTS and Work Date Annotation

The table [below](#keys-and-values) shows the values for the keys:

* urn_cts
* urn_cts_author
* urn_cts_work
* urn_cts_edition
* author
* title
* cts
* work_date

For example, the values for `urn_cts`, `urn_cts_author`, `urn_cts_work`,
`urn_cts_edition`, `author`, and `title`
for the work with CTS URN `tlg0615.tlg001.1st1K-grc1` are, respectively,
`tlg0615.tlg001.1st1K-grc1`, `tlg0615`, `tlg001`, `1st1K-grc1`, `Aspasius`,
and `In Ethica Nichomachea Commentaria` (check it
in the [table](#keys-and-values)).

## CTS URN

The metadata concerning CTS URNs (which include author names and work titles)
were retrieved automatically from the
texts. This means that their values may contain
inconsistencies and errors, which can also be identified
in the table [below](#keys-and-values).

The field `cts` refers to a passage inside a work. In the
[table](#keys-and-values), the column `cts` tries to provide
a summary of all possible values: for example, `1-2_1-8` means
that the text has two main divisions (`_` identifies them)
and that the ranges for them are
1-2 and 1-8, respectively. Therefore, a sound query could be `cts=1_7`.

The values found in the column `cts` are sometimes a (long) list, if
the range for a specific division does not consist of pure numbers.
More in general, inconsistencies and errors are present since the
original texts sometimes provide slightly different CTS URN
implementations. For example, the texts from the PTA repository sometimes
specify the CTS URN of a work as a field in the XPATH expression within
`<refsDecl n="CTS">`, and therefore this also appears in the values of the
`cts` key.

## Work Dates

At the moment, ANNIS 4 has no support for numbers. This means that, for now,
a work's composition date must be modeled as a string.
For this reason, ISO 8601 format dates, which
were annotated manually by one annotator and continue to be corrected
(see [file](../work_chronology/texts/chronology_greek_works.xml)),
were transformed into labels such as `m3_2`or `p2_1`.

`m3_2` means "2nd half of the 3rd century BCE", while `p2_1` "1st half of the
2nd century CE". "m" stands for "minus" (i.e., BCE) and "p" for "plus"
(i.e., CE). The first number after "m" or "p"
refers to the century and the last one to the half.

As is known, the composition date of an ancient work is often uncertain. For
this reason, the original 
[ISO 8601 format dates](../work_chronology/texts/chronology_greek_works.xml)
specify a range (alleged initial date and alleged end date). For example,
Euripides' Cyclops has the date `-0411-01/-0405-12`, which has been converted
into the label "m5_2" (i.e., 2nd half of the 5th century BCE).

If an alleged date range spans over different century halves (this usually
means a very uncertain date),
only the longer half is kept (e.g., `+0096-01/+0116-12` corresponds to "p2_1").
Since some date ranges can span over a long period comprising many
century halves with the same temporal extension (i.e., 50 years), a value for
`work_date` can look like `m9_1/m9_2/m8_1`. For this reason, it makes sense
to query work dates using regular expressions, such as `/.*m9_2.*/`,
which catches works with a date label corrsponding to `m9_2`
and works with date labels *including* `m9_2`.


## Keys and Values

<table>
  <thead>
    <tr>
      <th>urn_cts</th>
      <th>author</th>
      <th>title</th>
      <th>cts</th>
      <th>work_date</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ggm0001.ggm001.1st1K-grc1</td>
      <td>Anonymous</td>
      <td>Anametresis Pontou</td>
      <td>1-2_1-8</td>
      <td>p1_2/p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>ogl0001.ogl001.1st1K-grc1</td>
      <td>Pinytus, Saint, Bishop of Knossos</td>
      <td>De Epistola Pinyti ad Dionysium</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>pta0001.pta001.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De fide et lege naturae</td>
      <td>urn:cts:pta:pta0001.pta001.pta-grc1_1-11</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta002.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De paenitentia et compunctione</td>
      <td>urn:cts:pta:pta0001.pta002.pta-grc1_1-7</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta003.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In ascensionem domini nostri Iesu Christi et in principium Actorum</td>
      <td>urn:cts:pta:pta0001.pta003.pta-grc1_1-40</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta004.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De spiritu sancto</td>
      <td>urn:cts:pta:pta0001.pta004.pta-grc1_1-11</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta005.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De Christo pastore et ove</td>
      <td>urn:cts:pta:pta0001.pta005.pta-grc1_1-4</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta006.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In psalmum 96</td>
      <td>urn:cts:pta:pta0001.pta006.pta-grc1_1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta007.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In psalmum 95</td>
      <td>urn:cts:pta:pta0001.pta007.pta-grc1_1-7</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta008.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Homilia de legislatore</td>
      <td>urn:cts:pta:pta0001.pta008.pta-grc1_1-7</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta009.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: In qua potestate haec facis</td>
      <td>urn:cts:pta:pta0001.pta009.pta-grc1_1-8</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta010.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Quomodo animam acceperit Adamus</td>
      <td>urn:cts:pta:pta0001.pta010.pta-grc1_1-15</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta011.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De serpente homilia</td>
      <td>urn:cts:pta:pta0001.pta011.pta-grc1_1-10</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta012.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Oratio in dedicationem pretiosae et uiuificae crucis</td>
      <td>urn:cts:pta:pta0001.pta012.pta-grc1_1-1</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta013.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Genesim sermo 2</td>
      <td>urn:cts:pta:pta0001.pta013.pta-grc1_1-2</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta014.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: Pone manum tuam</td>
      <td>urn:cts:pta:pta0001.pta014.pta-grc1_1-1</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta015.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In meretricem et pharisaeum</td>
      <td>urn:cts:pta:pta0001.pta015.pta-grc1_1-2</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta016.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In filium prodigum</td>
      <td>urn:cts:pta:pta0001.pta016.pta-grc1_1-18</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta017.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: Quomodo scit litteras</td>
      <td>urn:cts:pta:pta0001.pta017.pta-grc1_1-5</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta018.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Chananaeam et Pharaonem</td>
      <td>urn:cts:pta:pta0001.pta018.pta-grc1_1-4</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta019.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In dictum apostoli: Non quod volo facio</td>
      <td>urn:cts:pta:pta0001.pta019.pta-grc1_1-5</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta020.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In incarnationem domini</td>
      <td>urn:cts:pta:pta0001.pta020.pta-grc1_1-8</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta021.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In proditionem servatoris</td>
      <td>urn:cts:pta:pta0001.pta021.pta-grc1_1-4</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta022.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De fide</td>
      <td>urn:cts:pta:pta0001.pta022.pta-grc1_1-1</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta023.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Contra Iudaeos in serpentem aeneum</td>
      <td>urn:cts:pta:pta0001.pta023.pta-grc1_1-12</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta024.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De sacrificiis Caini</td>
      <td>urn:cts:pta:pta0001.pta024.pta-grc1_1-1</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta025.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De sigillis sermo</td>
      <td>urn:cts:pta:pta0001.pta025.pta-grc1_1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta026.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: in principium erat verbum</td>
      <td>urn:cts:pta:pta0001.pta026.pta-grc1_1-3</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta027.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In sanctam pentecosten</td>
      <td>urn:cts:pta:pta0001.pta027.pta-grc1_1-15</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta028.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In theophaniam</td>
      <td>urn:cts:pta:pta0001.pta028.pta-grc1_1-1</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta029.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In pretiosam et vivificam crucem</td>
      <td>urn:cts:pta:pta0001.pta029.pta-grc1_1-5</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta030.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Homilia de pace</td>
      <td>urn:cts:pta:pta0001.pta030.pta-grc1_1-11</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta031.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: Pater, transeat a me calix iste</td>
      <td>urn:cts:pta:pta0001.pta031.pta-grc1_1-29</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta032.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Homilia de lotione pedum</td>
      <td>urn:cts:pta:pta0001.pta032.pta-grc1_1-23</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta033.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Homilia de quinque aetatibus mundi</td>
      <td>urn:cts:pta:pta0001.pta033.pta-grc1_1-1</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta034.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De centurione et contra Manichaeos et Apolinaristas</td>
      <td>urn:cts:pta:pta0001.pta034.pta-grc1_1-34</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta036.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Noe et filios eius, de cherubim et in propthetam Oseam</td>
      <td>urn:cts:pta:pta0001.pta036.pta-grc1_1-40</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta037.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Iudaeos et Graecos</td>
      <td>urn:cts:pta:pta0001.pta037.pta-grc1_1-48</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta038.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: Secundum imaginem et similitudinem</td>
      <td>urn:cts:pta:pta0001.pta038.pta-grc1_1-45</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta040.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De caeco et Zacchaeo</td>
      <td>urn:cts:pta:pta0001.pta040.pta-grc1_1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta041.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: Quando ipsi subiciet omnia</td>
      <td>urn:cts:pta:pta0001.pta041.pta-grc1_1-15</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta042.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In illud: Genimina viperarum</td>
      <td>urn:cts:pta:pta0001.pta042.pta-grc1_1-3_1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta043.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Homilia de Noe et de arca</td>
      <td>urn:cts:pta:pta0001.pta043.pta-grc1_1-19</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta044.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Genesim sermo 1</td>
      <td>urn:cts:pta:pta0001.pta044.pta-grc1_1-2</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta045.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Iob sermo 1</td>
      <td>1-2</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta046.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Iob sermo 2</td>
      <td>1-2</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta047.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Iob sermo 3</td>
      <td>1-4</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta048.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Iob sermo 4</td>
      <td>1-4</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta049.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De tribus pueris sermo</td>
      <td>urn:cts:pta:pta0001.pta049.pta-grc1_1-3</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta050.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De caeco nato</td>
      <td>urn:cts:pta:pta0001.pta050.pta-grc1_1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta051.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Encomium in sanctos martyres</td>
      <td>urn:cts:pta:pta0001.pta051.pta-grc1_1-32</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta052.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In postremum iudicium</td>
      <td>urn:cts:pta:pta0001.pta052.pta-grc1_1-15</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta053.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In accensionem domini</td>
      <td>urn:cts:pta:pta0001.pta053.pta-grc1_1-1</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta054.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>De cruce et latrone</td>
      <td>urn:cts:pta:pta0001.pta054.pta-grc1_1-18</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta055.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>Oratio de exaltatione Crucis</td>
      <td>urn:cts:pta:pta0001.pta055.pta-grc1_1-10</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta056.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In Temptationem Domini Nostri Iesu Christi</td>
      <td>urn:cts:pta:pta0001.pta056.pta-grc1_1-22</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta057.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In cosmogoniam homilia 1</td>
      <td>1-7</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta058.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In cosmogoniam homilia 2</td>
      <td>1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta059.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In cosmogoniam homilia 3</td>
      <td>1-7</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta060.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In cosmogoniam homilia 4</td>
      <td>1-10</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta061.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In cosmogoniam homilia 5</td>
      <td>1-9</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0001.pta062.pta-grc1</td>
      <td>Severian of Gabala</td>
      <td>In cosmogoniam homilia 6</td>
      <td>1-10</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0003.pta007.pta-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Contra Marcellum</td>
      <td>urn:cts:pta:pta0003.pta007.pta-grc1_1-2_1-4_1-31</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0003.pta009.pta-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>De ecclesiastica theologia</td>
      <td>urn:cts:pta:pta0003.pta009.pta-grc1_1-3_praefatio, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25_1-2</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0003.pta017.pta-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Commentarius in Isaiam</td>
      <td>urn:cts:pta:pta0003.pta017.pta-grc1_1-2_1-58</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>pta0004.pta003.pta-grc1</td>
      <td>Theodoret of Cyrrhus</td>
      <td>Historia ecclesiastica</td>
      <td>urn:cts:pta:pta0004.pta003.pta-grc1_1-5_pin, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0005.pta001.pta-grc1</td>
      <td>Cyrill of Alexandria</td>
      <td>De adoratione et cultu in spiritu et ueritate</td>
      <td>urn:cts:pta:pta0005.pta001.pta-grc1_0_Index, Titulus</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0005.pta002.pta-grc1</td>
      <td>Cyrill of Alexandria</td>
      <td>Glaphyra in Pentateuchum</td>
      <td>urn:cts:pta:pta0005.pta002.pta-grc1_Gen, Ex, Lev, Num, Dt_1-1_2-5_1-3</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0006.pta001.pta-grc1</td>
      <td>Hesychius of Jerusalem</td>
      <td>Commentarius magnus in Psalmos</td>
      <td>urn:cts:pta:pta0006.pta001.pta-grc1_Ps_37-37_1-Ps</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0007.pta007.pta-grc1</td>
      <td>Origen</td>
      <td>Exhortatio ad martyrium</td>
      <td>urn:cts:pta:pta0007.pta007.pta-grc1_1-51</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>pta0007.pta008.pta-grc1</td>
      <td>Origen</td>
      <td>De oratione</td>
      <td>1-34_1-1</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>pta0012.pta001.pta-grc1</td>
      <td>Sozomen</td>
      <td>Historia ecclesiastica</td>
      <td>urn:cts:pta:pta0012.pta001.pta-grc1_praefatio, 1, 2, 3, 4, 5, 6, 7, 8, 9_1-17_1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>pta0013.pta003.pta-grc1</td>
      <td>Amphilochius of Iconium</td>
      <td>Epistula synodalis</td>
      <td>, urn:cts:pta:pta0013.pta003.pta-grc1_1-4</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>pta0022.pta001.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Contra gentes</td>
      <td>, urn:cts:pta:pta0022.pta001.pta-grc1_1-47</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta002.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>De incarnatione</td>
      <td>urn:cts:pta:pta0022.pta002.pta-grc1_1-57</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>pta0022.pta003.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>De decretis Nicaenae synodi</td>
      <td>1-42_1-3</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta004.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>De sententia Dionysii</td>
      <td>1-27_1-4</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta010.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Apologia ad Constantium</td>
      <td>1-35_1-4</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta011.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Epistula ad Ioannem et Antiochum</td>
      <td>urn:cts:pta:pta0022.pta011.pta-grc1_pr, 1, 2, 3, 4</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta012.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Epistula ad Palladium</td>
      <td>urn:cts:pta:pta0022.pta012.pta-grc1_pr, 1, 2, 3, 4, 5, 6, 7</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta013.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Epistula ad Dracontium</td>
      <td>1-10_1-5</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta014.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Epistula ad Afros</td>
      <td>1-11_1-2</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta015.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Tomus ad Antiochenos</td>
      <td>1-11_1-3</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta016.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Epistula ad Jovianum</td>
      <td>praef, 1, 2, 3, 4_1-2</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0022.pta017.pta-grc1</td>
      <td>Athanasius of Alexandria</td>
      <td>Petitiones Arianorum</td>
      <td>1-4_1-2</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0023.pta001.pta-grc1</td>
      <td>Marcellus of Ancyra</td>
      <td>Fragmenta</td>
      <td>1-129</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0029.pta002.pta-grc1</td>
      <td>Ps.-Athanasius of Alexandria</td>
      <td>De sabbatis et circumcisione</td>
      <td>urn:cts:pta:pta0029.pta002.pta-grc1_1-6</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0030.pta016.pta-grc2</td>
      <td>Eusebius (“Alexandrinus”)</td>
      <td>De die dominica</td>
      <td>urn:cts:pta:pta0030.pta016.pta-grc2_1-6</td>
      <td>p5_2</td>
    </tr>
    <tr>
      <td>pta0036.pta001.pta-grc1</td>
      <td>Anonymus of Cyzicus</td>
      <td>Historia ecclesiastica</td>
      <td>praefatio, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38_praefatio, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38_1-20</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>pta0037.pta001.pta-grc1</td>
      <td>Hippolytus of Rome</td>
      <td>Commentarii in Danielem</td>
      <td>1-59_1-59_1-3</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>pta0038.pta001.pta-grc1</td>
      <td>Hermas</td>
      <td>Pastor</td>
      <td>visio, mandatum, similitudo_1-10_1-4_1-3ad4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>pta0039.pta001.pta-grc1</td>
      <td>Anonymus (Pseudo-John Chrysostom)</td>
      <td>Homilia de dominica die</td>
      <td>urn:cts:pta:pta0039.pta001.pta-grc1_1-7</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>pta0040.pta001.pta-grc1</td>
      <td>Anonymus (Pseudo-John Chrysostom / Pseudo-Basil of Caesarea)</td>
      <td>Homilia de sancta dominica</td>
      <td>urn:cts:pta:pta0040.pta001.pta-grc1_1-6</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>pta0041.pta001.pta-grc1</td>
      <td>Anonymus (Author of Vita Cononis)</td>
      <td>Vita sancti Cononis Bidanae</td>
      <td>1-4_1-2_1-2_1-</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>pta0100.pta001.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 1: Theologische Erklärung alexandrinischer Kleriker an Alexander von Alexandrien</td>
      <td>urn:cts:pta:pta0100.pta001.pta-grc1_1-5</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta002.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 2: Briefe des Alexander von Alexandrien</td>
      <td>1-2_1-21</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta003.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 3: Regest eines Rundbriefes einer Synode in Bithynien</td>
      <td>1-1</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta004.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 4: Brief des Eusebius von Nikomedien an Paulinus von Tyrus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta005.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 5: Referate eines</td>
      <td>urn:cts:pta:pta0100.pta005.pta-grc1_1-4</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta006.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 6: Fragment eines Briefes des Presbyters Georgius an Alexander von Alexandrien</td>
      <td>urn:cts:pta:pta0100.pta006.pta-grc1_1-1</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta007.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 7: Fragment eines Briefes des Presbyters Georgius an die »Arianer« in Alexandrien</td>
      <td>urn:cts:pta:pta0100.pta007.pta-grc1_1-1</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta008.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 8: Regeste eines Briefes</td>
      <td>urn:cts:pta:pta0100.pta008.pta-grc1_1-1</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta009.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 9: Fragment eines Briefes des Eusebius von Caesarea an Alexander von Alexandrien</td>
      <td>urn:cts:pta:pta0100.pta009.pta-grc1_1-5</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta0100.pta010.pta-grc1</td>
      <td>Dokumente zur Geschichte des arianischen Streites (Athanasius Werke III)</td>
      <td>Dok. 10: Fragmente eines Briefes des Eusebius von Caesarea an Euphration von Balaneae</td>
      <td>urn:cts:pta:pta0100.pta010.pta-grc1_1-5</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>pta9999.pta001.pta-grc1</td>
      <td>Bible</td>
      <td>Genesis</td>
      <td>urn:cts:pta:pta9999.pta001.pta-grc1_1-50_1-26</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>pta9999.pta002.pta-grc1</td>
      <td>Bible</td>
      <td>Exodus</td>
      <td>urn:cts:pta:pta9999.pta002.pta-grc1_1-40_1-38</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>pta9999.pta003.pta-grc1</td>
      <td>Bible</td>
      <td>Leviticus</td>
      <td>urn:cts:pta:pta9999.pta003.pta-grc1_1-27_1-34</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>pta9999.pta004.pta-grc1</td>
      <td>Bible</td>
      <td>Numeri</td>
      <td>urn:cts:pta:pta9999.pta004.pta-grc1_1-36_1-13</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>pta9999.pta005.pta-grc1</td>
      <td>Bible</td>
      <td>Deuteronomium</td>
      <td>urn:cts:pta:pta9999.pta005.pta-grc1_1-34_1-12</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>pta9999.pta006.pta-grc1</td>
      <td>Bible</td>
      <td>Josue</td>
      <td>urn:cts:pta:pta9999.pta006.pta-grc1_1-24_1-33b</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta007.pta-grc1</td>
      <td>Bible</td>
      <td>Judices</td>
      <td>urn:cts:pta:pta9999.pta007.pta-grc1_1-21_1-25</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta008.pta-grc1</td>
      <td>Bible</td>
      <td>Ruth</td>
      <td>urn:cts:pta:pta9999.pta008.pta-grc1_1-4_1-22</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta009.pta-grc1</td>
      <td>Bible</td>
      <td>Regnorum I</td>
      <td>urn:cts:pta:pta9999.pta009.pta-grc1_1-31_1-13</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta010.pta-grc1</td>
      <td>Bible</td>
      <td>Regnorum II</td>
      <td>urn:cts:pta:pta9999.pta010.pta-grc1_1-24_1-25</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta011.pta-grc1</td>
      <td>Bible</td>
      <td>Regnorum III</td>
      <td>urn:cts:pta:pta9999.pta011.pta-grc1_1-22_1-54</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta012.pta-grc1</td>
      <td>Bible</td>
      <td>Regnorum IV</td>
      <td>urn:cts:pta:pta9999.pta012.pta-grc1_1-25_1-30</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta013.pta-grc1</td>
      <td>Bible</td>
      <td>Paralipomenon I</td>
      <td>urn:cts:pta:pta9999.pta013.pta-grc1_1-29_1-30</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta014.pta-grc1</td>
      <td>Bible</td>
      <td>Paralipomenon II</td>
      <td>urn:cts:pta:pta9999.pta014.pta-grc1_1-36_1-23</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta016.pta-grc1</td>
      <td>Bible</td>
      <td>Esdrae I</td>
      <td>urn:cts:pta:pta9999.pta016.pta-grc1_1-9_1-55</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta017.pta-grc1</td>
      <td>Bible</td>
      <td>Esdrae II</td>
      <td>urn:cts:pta:pta9999.pta017.pta-grc1_1-23_1-31</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta020.pta-grc1</td>
      <td>Bible</td>
      <td>Esther</td>
      <td>urn:cts:pta:pta9999.pta020.pta-grc1_1-10_1a, 1b, 1c, 1d, 1e, 1f, 1g, 1h, 1i, 1k, 1l, 1m, 1n, 1o, 1p, 1q, 1r, 1s, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 1, 23, 13a, 13b, 13c, 13d, 13e, 13f, 13g, 17a, 17b, 17c, 17d, 17e, 17f, 17g, 17h, 17i, 17k, 17l, 17m, 17n, 17o, 17p, 17q, 17r, 17s, 17t, 17u, 17w, 17x, 17y, 17z, 2a, 2b, 12a, 12b, 12c, 12d, 12e, 12f, 12g, 12h, 12i, 12k, 12l, 12m, 12n, 12o, 12p, 12q, 12r, 12s, 12t, 12u, 12x, 24, 25, 26, 27, 28, 29, 31, 32, 3a, 3b, 3c, 3d, 3e, 3f, 3g, 3h, 3i, 3k, 3l</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta021.pta-grc1</td>
      <td>Bible</td>
      <td>Judith</td>
      <td>urn:cts:pta:pta9999.pta021.pta-grc1_1-16_1-25</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta022.pta-grc1</td>
      <td>Bible</td>
      <td>Tobias</td>
      <td>urn:cts:pta:pta9999.pta022.pta-grc1_1-14_1-15</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta023.pta-grc1</td>
      <td>Bible</td>
      <td>Machabaeorum I</td>
      <td>urn:cts:pta:pta9999.pta023.pta-grc1_1-16_1-24</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta024.pta-grc1</td>
      <td>Bible</td>
      <td>Machabaeorum II</td>
      <td>urn:cts:pta:pta9999.pta024.pta-grc1_1-15_1-39</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta025.pta-grc1</td>
      <td>Bible</td>
      <td>Machabaeorum III</td>
      <td>urn:cts:pta:pta9999.pta025.pta-grc1_1-7_1-23</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta026.pta-grc1</td>
      <td>Bible</td>
      <td>Machabaeorum IV</td>
      <td>urn:cts:pta:pta9999.pta026.pta-grc1_1-18_1-24</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta031.pta-grc1</td>
      <td>Bible</td>
      <td>Psalmi</td>
      <td>urn:cts:pta:pta9999.pta031.pta-grc1_1-151_1-7</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta032.pta-grc1</td>
      <td>Bible</td>
      <td>Odae</td>
      <td>urn:cts:pta:pta9999.pta032.pta-grc1_1-14_t, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 46, 47, 48, 49, 50, 51</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta033.pta-grc1</td>
      <td>Bible</td>
      <td>Proverbia</td>
      <td>urn:cts:pta:pta9999.pta033.pta-grc1_1-31a_1-31</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta034.pta-grc1</td>
      <td>Bible</td>
      <td>Ecclesiastes</td>
      <td>urn:cts:pta:pta9999.pta034.pta-grc1_1-12_1-14</td>
      <td>m3_1/m3_2/m2_1/m2_2</td>
    </tr>
    <tr>
      <td>pta9999.pta035.pta-grc1</td>
      <td>Bible</td>
      <td>Canticum</td>
      <td>urn:cts:pta:pta9999.pta035.pta-grc1_1-8_1-14</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta036.pta-grc1</td>
      <td>Bible</td>
      <td>Job</td>
      <td>urn:cts:pta:pta9999.pta036.pta-grc1_1-42_1-17e</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>pta9999.pta037.pta-grc1</td>
      <td>Bible</td>
      <td>Sapientia Salomonis</td>
      <td>urn:cts:pta:pta9999.pta037.pta-grc1_1-19_1-22</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta038.pta-grc1</td>
      <td>Bible</td>
      <td>Siracides</td>
      <td>urn:cts:pta:pta9999.pta038.pta-grc1_p, t, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51_t, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 27, 28, 29, 30, 31, 32, 33, 34, 35, 26, 36, 37</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta039.pta-grc1</td>
      <td>Bible</td>
      <td>Psalmi Salomonis</td>
      <td>urn:cts:pta:pta9999.pta039.pta-grc1_1-18_1-12</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta040.pta-grc1</td>
      <td>Bible</td>
      <td>Osee</td>
      <td>urn:cts:pta:pta9999.pta040.pta-grc1_1-14_1-10</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta041.pta-grc1</td>
      <td>Bible</td>
      <td>Amos</td>
      <td>urn:cts:pta:pta9999.pta041.pta-grc1_1-9_1-15</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta042.pta-grc1</td>
      <td>Bible</td>
      <td>Michaeas</td>
      <td>urn:cts:pta:pta9999.pta042.pta-grc1_1-7_1-20</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta043.pta-grc1</td>
      <td>Bible</td>
      <td>Joel</td>
      <td>urn:cts:pta:pta9999.pta043.pta-grc1_1-4_1-21</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta044.pta-grc1</td>
      <td>Bible</td>
      <td>Abdias</td>
      <td>urn:cts:pta:pta9999.pta044.pta-grc1_1-21</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta045.pta-grc1</td>
      <td>Bible</td>
      <td>Jonas</td>
      <td>urn:cts:pta:pta9999.pta045.pta-grc1_1-4_1-11</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta046.pta-grc1</td>
      <td>Bible</td>
      <td>Nahum</td>
      <td>urn:cts:pta:pta9999.pta046.pta-grc1_1-3_1-19</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta047.pta-grc1</td>
      <td>Bible</td>
      <td>Habacuc</td>
      <td>urn:cts:pta:pta9999.pta047.pta-grc1_1-3_1-19</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta048.pta-grc1</td>
      <td>Bible</td>
      <td>Sophonias</td>
      <td>urn:cts:pta:pta9999.pta048.pta-grc1_1-3_1-20</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta049.pta-grc1</td>
      <td>Bible</td>
      <td>Aggaeus</td>
      <td>urn:cts:pta:pta9999.pta049.pta-grc1_1-2_1-23</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta050.pta-grc1</td>
      <td>Bible</td>
      <td>Zacharias</td>
      <td>urn:cts:pta:pta9999.pta050.pta-grc1_1-14_1-21</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta051.pta-grc1</td>
      <td>Bible</td>
      <td>Malachias</td>
      <td>urn:cts:pta:pta9999.pta051.pta-grc1_1-3_1-24</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta052.pta-grc1</td>
      <td>Bible</td>
      <td>Isaias</td>
      <td>urn:cts:pta:pta9999.pta052.pta-grc1_1-66_1-24</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta053.pta-grc1</td>
      <td>Bible</td>
      <td>Jeremias</td>
      <td>urn:cts:pta:pta9999.pta053.pta-grc1_1-52_1-34</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta054.pta-grc1</td>
      <td>Bible</td>
      <td>Baruch</td>
      <td>urn:cts:pta:pta9999.pta054.pta-grc1_1-5_1-9</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta055.pta-grc1</td>
      <td>Bible</td>
      <td>Threni seu Lamentationes</td>
      <td>urn:cts:pta:pta9999.pta055.pta-grc1_1-5_t, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 25, 27, 28, 30, 31, 32, 33, 34, 35, 37, 39, 40, 41, 43, 44, 46, 47, 48, 49, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta056.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Jeremiae</td>
      <td>urn:cts:pta:pta9999.pta056.pta-grc1_1-72</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta059.pta-grc1</td>
      <td>Bible</td>
      <td>Ezechiel</td>
      <td>urn:cts:pta:pta9999.pta059.pta-grc1_1-48_1-35</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta060.pta-grc1</td>
      <td>Bible</td>
      <td>Susanna</td>
      <td>urn:cts:pta:pta9999.pta060.pta-grc1_1-64</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta061.pta-grc1</td>
      <td>Bible</td>
      <td>Daniel</td>
      <td>urn:cts:pta:pta9999.pta061.pta-grc1_1-12_1-13</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta062.pta-grc1</td>
      <td>Bible</td>
      <td>Bel et Draco</td>
      <td>urn:cts:pta:pta9999.pta062.pta-grc1_1-42</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta063.pta-grc1</td>
      <td>Bible</td>
      <td>Evangelium secundum Matthaeum</td>
      <td>urn:cts:pta:pta9999.pta063.pta-grc1_1-28_1-20</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta064.pta-grc1</td>
      <td>Bible</td>
      <td>Evangelium secundum Marcum</td>
      <td>urn:cts:pta:pta9999.pta064.pta-grc1_1-16_1-20</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta065.pta-grc1</td>
      <td>Bible</td>
      <td>Evangelium secundum Lucam</td>
      <td>urn:cts:pta:pta9999.pta065.pta-grc1_1-24_1-53</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta066.pta-grc1</td>
      <td>Bible</td>
      <td>Evangelium secundum Ioannem</td>
      <td>urn:cts:pta:pta9999.pta066.pta-grc1_1-21_1-25</td>
      <td>p1_2/p2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta067.pta-grc1</td>
      <td>Bible</td>
      <td>Acta apostolorum</td>
      <td>urn:cts:pta:pta9999.pta067.pta-grc1_1-28_1-31</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta068.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Romanos</td>
      <td>urn:cts:pta:pta9999.pta068.pta-grc1_1-16_1-24</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta069.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Corinthios I</td>
      <td>urn:cts:pta:pta9999.pta069.pta-grc1_1-16_1-24</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta070.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Corinthios II</td>
      <td>urn:cts:pta:pta9999.pta070.pta-grc1_1-13_1-13</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta071.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Galatas</td>
      <td>urn:cts:pta:pta9999.pta071.pta-grc1_1-6_1-18</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>pta9999.pta072.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Ephesios</td>
      <td>urn:cts:pta:pta9999.pta072.pta-grc1_1-6_1-24</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta073.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Philippenses</td>
      <td>urn:cts:pta:pta9999.pta073.pta-grc1_1-4_1-23</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta074.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Colossenses</td>
      <td>urn:cts:pta:pta9999.pta074.pta-grc1_1-4_1-18</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta075.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Thessalonicenses I</td>
      <td>urn:cts:pta:pta9999.pta075.pta-grc1_1-5_1-28</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta076.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Thessalonicenses II</td>
      <td>urn:cts:pta:pta9999.pta076.pta-grc1_1-3_1-18</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta077.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Timotheum I</td>
      <td>urn:cts:pta:pta9999.pta077.pta-grc1_1-6_1-21</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta078.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Timotheum II</td>
      <td>urn:cts:pta:pta9999.pta078.pta-grc1_1-4_1-22</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta079.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Titum</td>
      <td>urn:cts:pta:pta9999.pta079.pta-grc1_1-3_1-15</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta080.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Philemonem</td>
      <td>urn:cts:pta:pta9999.pta080.pta-grc1_1-1_1-25</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta081.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Pauli ad Hebraeos</td>
      <td>urn:cts:pta:pta9999.pta081.pta-grc1_1-13_1-25</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta082.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Iacobi</td>
      <td>urn:cts:pta:pta9999.pta082.pta-grc1_1-5_1-20</td>
      <td>p1_2/p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>pta9999.pta083.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Petri I</td>
      <td>urn:cts:pta:pta9999.pta083.pta-grc1_1-5_1-14</td>
      <td>p1_2/p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>pta9999.pta084.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Petri II</td>
      <td>urn:cts:pta:pta9999.pta084.pta-grc1_1-3_1-18</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta085.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Ioannis I</td>
      <td>urn:cts:pta:pta9999.pta085.pta-grc1_1-5_1-21</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>pta9999.pta086.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Ioannis II</td>
      <td>urn:cts:pta:pta9999.pta086.pta-grc1_1-1_1-13</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta087.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Ioannis III</td>
      <td>urn:cts:pta:pta9999.pta087.pta-grc1_1-1_1-15</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta088.pta-grc1</td>
      <td>Bible</td>
      <td>Epistula Iuda</td>
      <td>urn:cts:pta:pta9999.pta088.pta-grc1_1-25</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>pta9999.pta089.pta-grc1</td>
      <td>Bible</td>
      <td>Apocalypsis Ioannis</td>
      <td>urn:cts:pta:pta9999.pta089.pta-grc1_1-22_1-21</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>stoa0033a.tlg028.1st1K-grc1</td>
      <td>Pseudo-Aristotle</td>
      <td>De mundo</td>
      <td>1-7</td>
      <td>m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>stoa0033a.tlg043.1st1K-grc1</td>
      <td>Pseudo-Aristotle</td>
      <td>De spiritu</td>
      <td>1-9</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>stoa0121.stoa001.opp-grc1</td>
      <td>Eutropius</td>
      <td>Breviarium historiae romanae</td>
      <td>1-10_1-12</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>stoa0146d.stoa001.1st1K-grc1</td>
      <td>Hegemonius</td>
      <td>Acta Archelai</td>
      <td>5-13</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg0001.tlg001.perseus-grc2</td>
      <td>Apollonius Rhodius</td>
      <td>Argonautica</td>
      <td>1-4_1-1781</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0003.tlg001.perseus-grc2</td>
      <td>Thucydides</td>
      <td>History of the Peloponnesian War</td>
      <td>1-8_1-109_1-2</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0004.tlg001.perseus-grc2</td>
      <td>Diogenes Laertius</td>
      <td>Vitae philosophorum</td>
      <td>1-10_prol, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17_1-154</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0005.tlg001.perseus-grc2</td>
      <td>Theocritus</td>
      <td>Εἰδύλλια</td>
      <td>2-30_1-32</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0005.tlg002.perseus-grc2</td>
      <td>Theocritus</td>
      <td>Ἐπιγράμματα</td>
      <td>1-24_1-125</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0005.tlg003.1st1K-grc1</td>
      <td>Theocritus</td>
      <td>Syrinx</td>
      <td>1-20</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0006.tlg001.perseus-grc2</td>
      <td>Euripides</td>
      <td>Cyclops</td>
      <td>1-709</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg002.perseus-grc2</td>
      <td>Euripides</td>
      <td>Alcestis</td>
      <td>1-1163</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg003.perseus-grc2</td>
      <td>Euripides</td>
      <td>Medea</td>
      <td>1-1419</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg004.perseus-grc2</td>
      <td>Euripides</td>
      <td>Heracleidae</td>
      <td>1-1055</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg005.perseus-grc2</td>
      <td>Euripides</td>
      <td>Hippolytus</td>
      <td>1-1466</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg006.perseus-grc2</td>
      <td>Euripides</td>
      <td>Andromache</td>
      <td>1-1288</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg007.perseus-grc2</td>
      <td>Euripides</td>
      <td>Hecuba</td>
      <td>1-1295</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg008.perseus-grc2</td>
      <td>Euripides</td>
      <td>Suppliants</td>
      <td>1-1234</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0006.tlg009.perseus-grc2</td>
      <td>Euripides</td>
      <td>Heracles</td>
      <td>1-1428</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg010.perseus-grc2</td>
      <td>Euripides</td>
      <td>Ion</td>
      <td>1-1622</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg011.perseus-grc2</td>
      <td>Euripides</td>
      <td>The Trojan Women</td>
      <td>1-1332</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg012.perseus-grc2</td>
      <td>Euripides</td>
      <td>Electra</td>
      <td>1-1359</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg013.perseus-grc2</td>
      <td>Euripides</td>
      <td>Iphigenia in Tauris</td>
      <td>1-1499</td>
      <td>m5_2m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg014.perseus-grc2</td>
      <td>Euripides</td>
      <td>Helen</td>
      <td>1-1692</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg015.perseus-grc2</td>
      <td>Euripides</td>
      <td>Phoenissae</td>
      <td>1-1766</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg016.perseus-grc2</td>
      <td>Euripides</td>
      <td>Orestes</td>
      <td>1-1693</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg017.perseus-grc2</td>
      <td>Euripides</td>
      <td>Bacchae</td>
      <td>1-1392</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg018.perseus-grc2</td>
      <td>Euripides</td>
      <td>Iphigenia in Aulis</td>
      <td>49-1629</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg019.perseus-grc2</td>
      <td>Euripides</td>
      <td>Rhesus</td>
      <td>1-996</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0006.tlg020.1st1K-grc1</td>
      <td>Euripides</td>
      <td>Fragmenta</td>
      <td>1-1132</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg001.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Theseus</td>
      <td>1-36_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg002.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Romulus</td>
      <td>1-29_1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg003.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Theseus and Romulus</td>
      <td>1-6_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg004.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Lycurgus</td>
      <td>1-31_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg005.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Numa</td>
      <td>1-22_1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg006.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Lycurgus and Numa</td>
      <td>1-4_1-8</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg007.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Solon</td>
      <td>1-32_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg008.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Publicola</td>
      <td>1-23_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg009.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Solon and Publicola</td>
      <td>1-4_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg010.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Themistocles</td>
      <td>1-32_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg011.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Camillus</td>
      <td>1-43_1-1</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg012.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Pericles</td>
      <td>1-39_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg013.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Fabius Maximus</td>
      <td>1-27_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg014.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Pericles and Fabius Maximus</td>
      <td>1-3_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg015.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Alcibiades</td>
      <td>1-39_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg016.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Caius Marcius Coriolanus</td>
      <td>1-39_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg017.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Alcibiades and Coriolanus</td>
      <td>1-5_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg018.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Timoleon</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39_1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg019.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Aemilius Paulus</td>
      <td>2-39_1-10</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg020.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Timoleon and Aemilius</td>
      <td>1-2_1-12</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg021.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Pelopidas</td>
      <td>1-35_1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg022.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Marcellus</td>
      <td>1-30_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg023.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Pelopidas and Marcellus</td>
      <td>1-3_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg024.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Aristides</td>
      <td>1-27_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg025.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Marcus Cato</td>
      <td>1-27_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg026.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Aristides and Marcus Cato</td>
      <td>1-6_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg027.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Philopoemen</td>
      <td>1-21_1-6</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg028.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Titus Flamininus</td>
      <td>1-21_1-8</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg029.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Philopoemen and Titus</td>
      <td>1-3_1-3</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg030.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Pyrrhus</td>
      <td>1-34_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg031.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Caius Marius</td>
      <td>1-46_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg032.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Lysander</td>
      <td>1-30_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg033.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Sulla</td>
      <td>1-38_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg034.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Lysander and Sulla</td>
      <td>1-5_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg035.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Cimon</td>
      <td>1-19_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg036.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Lucullus</td>
      <td>1-43_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg037.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Lucullus and Cimon</td>
      <td>1-3_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg038.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Nicias</td>
      <td>1-30_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg039.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Crassus</td>
      <td>1-33_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg040.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Nicias and Crassus</td>
      <td>1-5_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg041.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Eumenes</td>
      <td>1-19_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg042.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Sertorius</td>
      <td>1-27_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg043.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Sertorius and Eumenes</td>
      <td>1-2_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg044.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Agesilaus</td>
      <td>1-40_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg045.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Pompey</td>
      <td>1-80_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg046.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Agesilaus and Pompey</td>
      <td>1-5_1-1</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg047.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Alexander</td>
      <td>1-77_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg048.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Caesar</td>
      <td>1-69_1-8</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg049.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Phocion</td>
      <td>1-38_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg050.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Cato the Younger</td>
      <td>1-73_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg051.perseus-grc1</td>
      <td>Plutarch</td>
      <td>Agis and Cleomenes</td>
      <td>Agis, Cleomenes_1-39_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg052.perseus-grc1</td>
      <td>Plutarch</td>
      <td>Tiberius and Caius Gracchus</td>
      <td>Tiberius, Caius_1-19_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg053.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Agis and Cleomenes and the Gracchi</td>
      <td>1-5_1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg054.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Demosthenes</td>
      <td>1-31_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg055.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Cicero</td>
      <td>1-49_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg056.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Demosthenes and Cicero</td>
      <td>1-5_1-1</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg057.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Demetrius</td>
      <td>1-53_1-4</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg058.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Antony</td>
      <td>1-87_1-4</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg059.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Demetrius and Antony</td>
      <td>1-6_1-2</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg060.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Dion</td>
      <td>1-58_1-10</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg061.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Brutus</td>
      <td>1-53_1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg062.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparison of Dion and Brutus</td>
      <td>1-5_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg063.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Aratus</td>
      <td>1-54_1-3</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg064.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Artaxerxes</td>
      <td>1-30_1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg065.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Galba</td>
      <td>1-29_1-4</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg066.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Otho</td>
      <td>1-18_1-4</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg067.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De liberis educandis</td>
      <td>1-20</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg068.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Quomodo adolescens poetas audire debeat</td>
      <td>1-14</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg069.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De recta ratione audiendi</td>
      <td>1-18</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg070.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Quomodo adulator ab amico internoscatur</td>
      <td>1-37</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg071.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Quomodo quis suos in virtute sentiat profectus</td>
      <td>1-17</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg072.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De capienda ex inimicis utilitate</td>
      <td>1-11</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg073.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De amicorum multitudine</td>
      <td>1-9</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg074.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De fortuna</td>
      <td>1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg075.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De virtute et vitio</td>
      <td>1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg076.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Consolatio ad Apollonium</td>
      <td>1-37</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg077.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De tuenda sanitate praecepta</td>
      <td>1-27</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg078.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Conjugalia Praecepta</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg079.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Septem sapientium convivium</td>
      <td>1-21</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg080.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Superstitione</td>
      <td>1-14</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg081.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Regum et imperatorum apophthegmata</td>
      <td>1-92_1-15</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg082.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Apophthegmata Laconica</td>
      <td>1-69_1-72</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg082a.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Instituta Laconia</td>
      <td>1-42</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg082b.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Lacaenarum Apophthegmata</td>
      <td>1-5_1-30</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg083.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Mulierum virtutes</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg084a.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Quaestiones Romanae</td>
      <td>1-113</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg084b.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Quaestiones Graecae</td>
      <td>1-59</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg085.perseus-grc3</td>
      <td>Plutarch</td>
      <td>Parallela minora</td>
      <td>intro, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg086.perseus-grc3</td>
      <td>Plutarch</td>
      <td>De fortuna Romanorum</td>
      <td>1-13</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg087.perseus-grc3</td>
      <td>Plutarch</td>
      <td>De Alexandri magni fortuna aut virtute</td>
      <td>1-2_1-13</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg088.perseus-grc3</td>
      <td>Plutarch</td>
      <td>De gloria Atheniensium</td>
      <td>1-8</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg089.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Iside et Osiride</td>
      <td>1-80</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg090.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De E apud Delphos</td>
      <td>1-21</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg091.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Pythiae oraculis</td>
      <td>1-30</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg092.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Defectu Oraculorum</td>
      <td>1-52</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg093.perseus-grc2</td>
      <td>Plutarch</td>
      <td>An Virtus Doceri Possit</td>
      <td>1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg094.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Virtute Morali</td>
      <td>1-12</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg095.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De cohibenda ira</td>
      <td>1-16</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg096.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Tranquillitate Animi</td>
      <td>1-20</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg097.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De fraterno amore</td>
      <td>1-21</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg098.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Amore Prolis</td>
      <td>1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg099.perseus-grc2</td>
      <td>Plutarch</td>
      <td>An vitiositas ad infelicitatem sufficia</td>
      <td>1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg100.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Animine an corporis affectiones sint peiores</td>
      <td>1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg101.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Garrulitate</td>
      <td>1-23</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg102.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De curiositate</td>
      <td>1-16</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg103.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Cupiditate Divitiarum</td>
      <td>1-10</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg104.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Vitioso Pudore</td>
      <td>1-19</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg105.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Invidia et Odio</td>
      <td>1-8</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg106.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Se Ipsum Citra Invidiam Laudando</td>
      <td>1-22</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg107.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Sera Numinis Vindicta</td>
      <td>1-33</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg108.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Fato</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg109.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Genio Socratis</td>
      <td>1-34</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg110.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De exilio</td>
      <td>1-17</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg111.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Consolatio Ad Uxorem</td>
      <td>1-11</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0007.tlg112.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Quaestiones Convivales</td>
      <td>1-9_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 12, 13, 14, 15_1-2</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg113.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Amatorius</td>
      <td>1-26</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg114.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Amatoriae Narrationes</td>
      <td>1-5</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg115.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Maxime Cum Principibus Viris Philosopho Esse Disserendum</td>
      <td>1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg116.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Ad principem ineruditum</td>
      <td>1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg117.perseus-grc2</td>
      <td>Plutarch</td>
      <td>An seni respublica gerenda sit</td>
      <td>1-28</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg118.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Praecepta gerendae reipublicae</td>
      <td>1-32</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg119.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De unius in republica dominatione, populari statu, et paucorum imperio</td>
      <td>1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg120.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De vitando aere alieno</td>
      <td>1-8</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg121.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Vitae decem oratorum</td>
      <td>1-13_1-1</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg122.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Comparationis Aristophanis et Menandri compendium</td>
      <td>1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg123.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Heroditi malignate</td>
      <td>1-43</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg125.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Quaestiones Naturales</td>
      <td>1-39</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg126.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Facie Quae in orbe Lunae Apparet</td>
      <td>1-30</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg127.perseus-grc3</td>
      <td>Plutarch</td>
      <td>De primo frigido</td>
      <td>1-23</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg128.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Aquane an ignis sit utilior</td>
      <td>1-13</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg129.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De sollertia animalium</td>
      <td>1-37</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg130.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Bruta animalia ratione uti</td>
      <td>1-10</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg131.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De esu carnium I</td>
      <td>1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg132.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De esu carnium II</td>
      <td>1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg133.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Platonicae quaestiones</td>
      <td>1-10_1-8</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg134.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De animae procreatione in Timaeo</td>
      <td>1-33</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg135.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Epitome libri de animae procreatione in Timaeo</td>
      <td>1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg136.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De Stoicorum repugnantiis</td>
      <td>1-47</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg137.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Compendium argumenti Stoicos absurdiora poetis dicere</td>
      <td>1-6</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg138.perseus-grc2</td>
      <td>Plutarch</td>
      <td>De communibus notitiis adversus Stoicos</td>
      <td>1-50</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg139.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Non Posse Suaviter Vivi Secundum Epicurum</td>
      <td>1-31</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg140.perseus-grc2</td>
      <td>Plutarch</td>
      <td>Adversus Coloten</td>
      <td>1-34</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg141.perseus-grc2</td>
      <td>Plutarch</td>
      <td>An Recte Dictum Sit Latenter Esse Vivendum</td>
      <td>1-7</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg146.1st1K-grc1</td>
      <td>Plutarch</td>
      <td>Παροιμίαι αἷς Ἀλεξανδρεῖς ἐχρῶντο</td>
      <td>1-2_1-31</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0007.tlg147.1st1K-grc1</td>
      <td>Plutarch</td>
      <td>Ἐκλογὴ περὶ τῶν ἀδυνάτων</td>
      <td>1-52</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0008.tlg001.perseus-grc3</td>
      <td>Athenaeus of Naucratis</td>
      <td>Deipnosophistae</td>
      <td>1-15_1-63</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg001.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Against Euthynus</td>
      <td>1-21</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg002.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Against Callimachus</td>
      <td>1-68</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg003.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Against Lochites</td>
      <td>1-22</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg004.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Concerning the Team of Horses</td>
      <td>1-50</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg005.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Trapeziticus</td>
      <td>1-58</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg006.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Aegineticus</td>
      <td>1-51</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg007.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Demonicus</td>
      <td>1-52</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg008.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Against the Sophists</td>
      <td>1-22</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg009.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Helen</td>
      <td>1-69</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg010.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Busiris</td>
      <td>1-50</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg011.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Panegyricus</td>
      <td>1-189</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg012.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Plataicus</td>
      <td>1-63</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg013.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Nicocles</td>
      <td>1-54</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg014.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Nicocles or the Cyprians</td>
      <td>1-64</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg015.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Evagoras</td>
      <td>1-81</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg016.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Archidamus</td>
      <td>1-111</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg017.perseus-grc2</td>
      <td>Isocrates</td>
      <td>On the Peace</td>
      <td>1-145</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg018.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Areopagiticus</td>
      <td>1-84</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg019.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Antidosis</td>
      <td>1-323</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg020.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Philip</td>
      <td>1-155</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg021.perseus-grc2</td>
      <td>Isocrates</td>
      <td>Panathenaicus</td>
      <td>1-272</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg022.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Dionysius</td>
      <td>1-1</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg023.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To the Children of Jason</td>
      <td>6-6</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg024.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Archidamus</td>
      <td>9-9</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0010.tlg025.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To the Rulers of the Mytilenaeans</td>
      <td>8-8</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg026.perseus-grc3</td>
      <td>Isocrates</td>
      <td>To Timotheus</td>
      <td>7-7</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg027.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Philip, I</td>
      <td>2-2</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg028.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Alexander</td>
      <td>5-5</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg029.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Antipater</td>
      <td>4-4</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0010.tlg030.perseus-grc2</td>
      <td>Isocrates</td>
      <td>To Philip, II</td>
      <td>3-3</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg001.perseus-grc2</td>
      <td>Sophocles</td>
      <td>Trachiniae</td>
      <td>1-1278</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg002.perseus-grc2</td>
      <td>Sophocles</td>
      <td>Antigone</td>
      <td>1-1353</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg003.1st1K-grc1</td>
      <td>Sophocles</td>
      <td>Ajax</td>
      <td>1-1394</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg004.perseus-grc2</td>
      <td>Sophocles</td>
      <td>Oedipus Tyrannus</td>
      <td>1-1530</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg005.perseus-grc2</td>
      <td>Sophocles</td>
      <td>Electra</td>
      <td>1-1510</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg006.perseus-grc2</td>
      <td>Sophocles</td>
      <td>Philoctetes</td>
      <td>1-1471</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg007.perseus-grc2</td>
      <td>Sophocles</td>
      <td>Oedipus at Colonus</td>
      <td>1-1779</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0011.tlg008.perseus-grc2</td>
      <td>Sophocles</td>
      <td>Ichneutae</td>
      <td>1-419</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0012.tlg001.perseus-grc2</td>
      <td>Homer</td>
      <td>Iliad</td>
      <td>1-24_1-804</td>
      <td>m8_1</td>
    </tr>
    <tr>
      <td>tlg0012.tlg002.perseus-grc2</td>
      <td>Homer</td>
      <td>Odyssey</td>
      <td>1-24_1-548</td>
      <td>m8_1</td>
    </tr>
    <tr>
      <td>tlg0012.tlg003.perseus-grc1</td>
      <td>Homer</td>
      <td>Epigrams</td>
      <td>1-17_1-4</td>
      <td>m8_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg001.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 1 to Dionysus</td>
      <td>1-21</td>
      <td>m7_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg002.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 2 to Demeter</td>
      <td>1-495</td>
      <td>m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg003.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 3 to Delian and Pythian Apollo</td>
      <td>1-546</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg004.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 4 to Hermes</td>
      <td>1-580</td>
      <td>m7_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg005.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 5 to Aphrodite</td>
      <td>1-293</td>
      <td>m7_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg006.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 6 to Aphrodite</td>
      <td>1-21</td>
      <td>m7_1/m7_2/m6_1/m6_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg007.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 7 to Dionysus</td>
      <td>1-59</td>
      <td>m6_2/m5_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg008.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 8 to Ares</td>
      <td>1-17</td>
      <td>p3_2/p4_1/p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg009.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 9 to Artemis</td>
      <td>1-9</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg010.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 10 to Aphrodite</td>
      <td>1-6</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg011.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 11 To Athena</td>
      <td>1-5</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg012.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 12 to Hera</td>
      <td>1-5</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg013.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 13 to Demeter</td>
      <td>1-3</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg014.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 14 to the Mother of the Gods</td>
      <td>1-6</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg015.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 15 To Heracles</td>
      <td>1-9</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg016.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 16 To Asclepius</td>
      <td>1-5</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg017.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 17 To the Dioscuri</td>
      <td>1-5</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg018.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 18 to Hermes</td>
      <td>1-12</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg019.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 19 to Pan</td>
      <td>1-49</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg020.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 20 To Hephaestus</td>
      <td>1-8</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg021.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 21 To Apollo</td>
      <td>1-5</td>
      <td>m6_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg022.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 22 To Poseidon</td>
      <td>1-7</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg023.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 23 to Zeus</td>
      <td>1-4</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg024.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 24 To Hestia</td>
      <td>1-5</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg025.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 25 To the Muses and Apollo</td>
      <td>1-7</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg026.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 26 To Dionysus</td>
      <td>1-13</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg027.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 27 to Artemis</td>
      <td>1-22</td>
      <td>m7_1/m7_2/m6_1/m6_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg028.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 28 to Athena</td>
      <td>1-18</td>
      <td>m7_1/m7_2/m6_1/m6_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg029.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 29 to Hestia</td>
      <td>1-14</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg030.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 30 to Earth</td>
      <td>1-19</td>
      <td>m7_1/m7_2/m6_1/m6_2</td>
    </tr>
    <tr>
      <td>tlg0013.tlg031.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 31 to Helios</td>
      <td>1-19</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg032.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 32 To Selene</td>
      <td>1-20</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0013.tlg033.perseus-grc2</td>
      <td>Homeric Hymns</td>
      <td>Hymn 33 To the Dioscuri</td>
      <td>1-19</td>
      <td>m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg001.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>First Olynthiac</td>
      <td>1-28</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg002.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Second Olynthiac</td>
      <td>1-31</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg003.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Third Olynthiac</td>
      <td>1-36</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg004.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>First Philippic</td>
      <td>1-51</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg005.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On the Peace</td>
      <td>1-25</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg006.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Second Philippic</td>
      <td>1-37</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg007.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On Halonnesus</td>
      <td>1-46</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg008.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On the Chersonese</td>
      <td>1-77</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg009.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Third Philippic</td>
      <td>1-76</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg010.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Fourth Philippic</td>
      <td>1-76</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg011.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Answer to Philip’s Letter</td>
      <td>1-23</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg012.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Philip’s Letter</td>
      <td>1-23</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg013.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On Organization</td>
      <td>1-36</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg014.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On the Navy-Boards</td>
      <td>1-41</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg015.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>For the Liberty of the Rhodians</td>
      <td>1-35</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg016.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>For the People of Megalopolis</td>
      <td>1-32</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg017.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On the Treaty with Alexander</td>
      <td>1-30</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg018.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On the Crown</td>
      <td>1-324</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg019.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On the False Embassy</td>
      <td>1-343</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg020.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Leptines</td>
      <td>1-167</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg021.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Meidias</td>
      <td>1-227</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg022.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Androtion</td>
      <td>1-78</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg023.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Aristocrates</td>
      <td>1-220</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg024.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Timocrates</td>
      <td>1-218</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg025.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Aristogeiton I</td>
      <td>1-101</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg026.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Aristogeiton II</td>
      <td>1-27</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg027.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Aphobus I</td>
      <td>1-69</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg028.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Aphobus II</td>
      <td>1-24</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg029.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Aphobus III</td>
      <td>1-60</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg030.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Onetor I</td>
      <td>1-39</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg031.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Onetor II</td>
      <td>1-14</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg032.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Zenothemis</td>
      <td>1-32</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg033.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Apaturius</td>
      <td>1-38</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg034.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Phormio</td>
      <td>1-52</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg035.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Lacritus</td>
      <td>1-56</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg036.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>For Phormio</td>
      <td>1-62</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg037.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Pantaenetus</td>
      <td>1-60</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg038.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Nausimachus and Xenopeithes</td>
      <td>1-28</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg039.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Boeotus I</td>
      <td>1-41</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg040.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Boeotus II</td>
      <td>1-61</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg041.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Spudias</td>
      <td>1-30</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg042.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Phaenippus</td>
      <td>1-32</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg043.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Macartatus</td>
      <td>1-84</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg044.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Leochares</td>
      <td>1-68</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg045.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Stephanus I</td>
      <td>1-88</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg046.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Stephanus II</td>
      <td>1-28</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg047.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Evergus and Mnesibulus</td>
      <td>1-82</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg048.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Olympiodorus</td>
      <td>1-58</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg049.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Apollodorus Against Timotheus</td>
      <td>1-69</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg050.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Apollodorus Against Polycles</td>
      <td>1-68</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg051.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>On the Trierarchic Crown</td>
      <td>1-22</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg052.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Apollodorus Against Callippus</td>
      <td>1-33</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg053.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Apollodorus Against Nicostratus</td>
      <td>1-29</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0014.tlg054.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Conon</td>
      <td>1-44</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg055.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Callicles</td>
      <td>1-35</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg056.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Dionysodorus</td>
      <td>1-50</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg057.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Eubulides</td>
      <td>1-70</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg058.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Against Theocrines</td>
      <td>1-70</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg059.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Theomnestus and Apollodorus Against Neaera</td>
      <td>1-126</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg060.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>The Funeral Speech</td>
      <td>1-37</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg061.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>The Erotic Essay</td>
      <td>1-57</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg062.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Exordia</td>
      <td>1-56_1-3</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0014.tlg063.perseus-grc2</td>
      <td>Demosthenes</td>
      <td>Letters</td>
      <td>1-6_1-2</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0015.tlg001.1st1K-grc1</td>
      <td>Herodian</td>
      <td>Ab excessu divi Marci</td>
      <td>1-8_1-8_1-8</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0016.tlg001.perseus-grc2</td>
      <td>Herodotus</td>
      <td>Histories</td>
      <td>1-9_1-122_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0017.tlg001.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On The Estate of Cleonymus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg002.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On the Estate of Menecles</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg003.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On The Estate Of Pyrrhus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg004.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On the Estate of Nicostratus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0017.tlg005.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On the Estate of Dicaeogenes</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg006.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On the Estate of Philoctemon</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg007.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On The Estate of Apollodorus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg008.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On The Estate of Ciron</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg009.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On the Estate of Astyphilus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg010.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On The Estate of Aristarchus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg011.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On the Estate of Hagnias</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0017.tlg012.perseus-grc2</td>
      <td>Isaeus</td>
      <td>On Behalf of Euphiletus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0018.tlg001.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Opificio Mundi</td>
      <td>1-172</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg002.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>Legum Allegoriarum Libri I-III</td>
      <td>1-3_1-253</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg003.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Cherubim</td>
      <td>1-130</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg004.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Sacrificiis Abelis Et Caini</td>
      <td>1-139</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg005.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>Quod Deterius Potiori Insidiari Soleat</td>
      <td>1-178</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg006.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Posteritate Caini</td>
      <td>1-185</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg007.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Gigantibus</td>
      <td>1-67</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg008.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>Quod Deus Sit Immutabilis</td>
      <td>1-183</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg009.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Agricultura</td>
      <td>1-181</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg010.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Plantatione</td>
      <td>1-177</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg011.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Ebrietate</td>
      <td>1-224</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg012.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Sobrietate</td>
      <td>1-69</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg013.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Confusione Linguarum</td>
      <td>1-198</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg014.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Migratione Abrahami</td>
      <td>1-225</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg015.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>Quis Rerum Divinarum Heres Sit</td>
      <td>1-316</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg016.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Congressu Eruditionis Gratia</td>
      <td>1-180</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg017.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Fuga Et Inventione</td>
      <td>1-213</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg018.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Mutatione Nominum</td>
      <td>1-270</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg019.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Somniis (lib. i-ii)</td>
      <td>1-2_1-302</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg020.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Abrahamo</td>
      <td>1-276</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg021.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Josepho</td>
      <td>1-270</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg022.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Vita Mosis (Lib. I-II)</td>
      <td>1-2_1-292</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg023.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Decalogo</td>
      <td>1-178</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg024.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Specialibus Legibus (lib. i‑iv)</td>
      <td>1-4_1-238</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg025.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Virtutibus</td>
      <td>1-227</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg026.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Praemiis Et Poenis Et De Exsecrationibus</td>
      <td>1-172</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg027.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>Quod Omnis Probus Liber Sit</td>
      <td>1-160</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg028.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Vita Contemplativa</td>
      <td>1-90</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg029.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>De Aeternitate Mundi</td>
      <td>1-150</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg030.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>In Flaccum</td>
      <td>1-191</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0018.tlg031.1st1K-grc1</td>
      <td>Philo Judaeus</td>
      <td>Legatio Ad Gaium</td>
      <td>1-373</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0019.tlg001.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Acharnians</td>
      <td>1-1234</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg002.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Knights</td>
      <td>1-1408</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg003.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Clouds</td>
      <td>1-1511</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg004.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Wasps</td>
      <td>1-1537</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg005.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Peace</td>
      <td>1-1357</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg006.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Birds</td>
      <td>1-1765</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg007.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Lysistrata</td>
      <td>1-1320</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg008.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Thesmophoriazusae</td>
      <td>1-1231</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg009.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Frogs</td>
      <td>1-1533</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0019.tlg010.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Ecclesiazusae</td>
      <td>1-1183</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0019.tlg011.perseus-grc2</td>
      <td>Aristophanes</td>
      <td>Wealth</td>
      <td>1-1209</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0020.tlg001.perseus-grc2</td>
      <td>Hesiod</td>
      <td>Theogony</td>
      <td>1-1022</td>
      <td>m9_1/m9_2/m8_1</td>
    </tr>
    <tr>
      <td>tlg0020.tlg002.perseus-grc2</td>
      <td>Hesiod</td>
      <td>Works and Days</td>
      <td>1-828</td>
      <td>m9_1/m9_2/m8_1</td>
    </tr>
    <tr>
      <td>tlg0020.tlg003.perseus-grc2</td>
      <td>Hesiod</td>
      <td>Shield of Heracles</td>
      <td>1-480</td>
      <td>m9_1/m9_2/m8_1</td>
    </tr>
    <tr>
      <td>tlg0022.tlg001.1st1K-grc1</td>
      <td>Nicander of Colophon</td>
      <td>Theriaca</td>
      <td>1-958</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0022.tlg002.1st1K-grc1</td>
      <td>Nicander of Colophon</td>
      <td>Alexipharmaca</td>
      <td>1-630</td>
      <td>m3_2/m2_1</td>
    </tr>
    <tr>
      <td>tlg0023.tlg001.perseus-grc2</td>
      <td>Oppian</td>
      <td>Halieutica</td>
      <td>1-5_1-680</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0024.tlg001.perseus-grc2</td>
      <td>Oppian of Apamea</td>
      <td>Cynegetica</td>
      <td>1-4_1-453</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0026.tlg001.perseus-grc2</td>
      <td>Aeschines</td>
      <td>Against Timarchus</td>
      <td>1-196</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0026.tlg002.perseus-grc2</td>
      <td>Aeschines</td>
      <td>On the Embassy</td>
      <td>1-184</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0026.tlg003.perseus-grc2</td>
      <td>Aeschines</td>
      <td>Against Ctesiphon</td>
      <td>1-260</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0026.tlg004.1st1K-grc1</td>
      <td>Aeschines</td>
      <td>Epistolae</td>
      <td>1-12_1-17</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0027.tlg001.perseus-grc2</td>
      <td>Andocides</td>
      <td>On the Mysteries</td>
      <td>1-150</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0027.tlg002.perseus-grc2</td>
      <td>Andocides</td>
      <td>On His Return</td>
      <td>1-28</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0027.tlg003.perseus-grc2</td>
      <td>Andocides</td>
      <td>On the Peace with Sparta</td>
      <td>1-41</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0027.tlg004.perseus-grc2</td>
      <td>Andocides</td>
      <td>Against Alcibiades</td>
      <td>1-42</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0028.tlg001.perseus-grc2</td>
      <td>Antiphon</td>
      <td>Against the Stepmother for Poisoning</td>
      <td>1-31</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0028.tlg002.perseus-grc2</td>
      <td>Antiphon</td>
      <td>The First Tetralogy</td>
      <td>1-4_1-12</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0028.tlg003.perseus-grc2</td>
      <td>Antiphon</td>
      <td>The Second Tetralogy</td>
      <td>1-4_1-10</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0028.tlg004.perseus-grc2</td>
      <td>Antiphon</td>
      <td>The Third Tetralogy</td>
      <td>1-4_1-11</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0028.tlg005.perseus-grc2</td>
      <td>Antiphon</td>
      <td>On the murder of Herodes</td>
      <td>1-96</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0028.tlg006.perseus-grc2</td>
      <td>Antiphon</td>
      <td>On the Choreutes</td>
      <td>1-51</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0029.tlg004.perseus-grc2</td>
      <td>Dinarchus</td>
      <td>Against Demosthenes</td>
      <td>1-114</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0029.tlg005.perseus-grc2</td>
      <td>Dinarchus</td>
      <td>Against Aristogiton</td>
      <td>1-26</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0029.tlg006.perseus-grc2</td>
      <td>Dinarchus</td>
      <td>Against Philocles</td>
      <td>1-22</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0030.tlg001.perseus-grc2</td>
      <td>Hyperides</td>
      <td>In Defence of Lycophron</td>
      <td>frag, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20_1-4b</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0030.tlg002.perseus-grc2</td>
      <td>Hyperides</td>
      <td>Against Philippides</td>
      <td>frag, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13_1-21</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0030.tlg003.perseus-grc2</td>
      <td>Hyperides</td>
      <td>Against Athenogenes</td>
      <td>1-frag</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0030.tlg004.perseus-grc2</td>
      <td>Hyperides</td>
      <td>In Defence of Euxenippus</td>
      <td>1-41</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0030.tlg005.perseus-grc2</td>
      <td>Hyperides</td>
      <td>Against Demosthenes</td>
      <td>frag, citations_1-9</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0030.tlg006.perseus-grc2</td>
      <td>Hyperides</td>
      <td>Funeral Oration</td>
      <td>1-43</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg001.perseus-grc2</td>
      <td>New Testament</td>
      <td>Matthew</td>
      <td>1-28_1-20</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg002.INTF-grc1</td>
      <td>New Testament</td>
      <td>Gospel of Mark</td>
      <td>1-1_1-45</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg003.perseus-grc2</td>
      <td>New Testament</td>
      <td>Luke</td>
      <td>1-24_1-53</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg004.perseus-grc2</td>
      <td>New Testament</td>
      <td>John</td>
      <td>1-21_1-25</td>
      <td>p1_2/p2_1</td>
    </tr>
    <tr>
      <td>tlg0031.tlg005.perseus-grc2</td>
      <td>New Testament</td>
      <td>Acts</td>
      <td>1-28_1-31</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg006.perseus-grc2</td>
      <td>New Testament</td>
      <td>Romans</td>
      <td>1-16_1-27</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg007.perseus-grc2</td>
      <td>New Testament</td>
      <td>1 Corinthians</td>
      <td>1-16_1-24</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg008.perseus-grc2</td>
      <td>New Testament</td>
      <td>2 Corinthians</td>
      <td>1-13_1-13</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg009.perseus-grc2</td>
      <td>New Testament</td>
      <td>Galatians</td>
      <td>1-6_1-18</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0031.tlg010.perseus-grc2</td>
      <td>New Testament</td>
      <td>Ephesians</td>
      <td>1-6_1-24</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg011.perseus-grc2</td>
      <td>New Testament</td>
      <td>Philippians</td>
      <td>1-4_1-23</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg012.perseus-grc2</td>
      <td>New Testament</td>
      <td>Colossians</td>
      <td>1-4_1-18</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg013.perseus-grc2</td>
      <td>New Testament</td>
      <td>1 Thessalonians</td>
      <td>1-5_1-28</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg014.perseus-grc2</td>
      <td>New Testament</td>
      <td>2 Thessalonians</td>
      <td>1-3_1-18</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg015.perseus-grc2</td>
      <td>New Testament</td>
      <td>1 Timothy</td>
      <td>1-6_1-21</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0031.tlg016.perseus-grc2</td>
      <td>New Testament</td>
      <td>2 Timothy</td>
      <td>1-4_1-22</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0031.tlg017.perseus-grc2</td>
      <td>New Testament</td>
      <td>Titus</td>
      <td>1-3_1-15</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg018.perseus-grc2</td>
      <td>New Testament</td>
      <td>Philemon</td>
      <td>1-1_1-25</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg019.perseus-grc2</td>
      <td>New Testament</td>
      <td>Hebrews</td>
      <td>1-13_1-25</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg020.perseus-grc2</td>
      <td>New Testament</td>
      <td>James</td>
      <td>1-5_1-20</td>
      <td>p1_2/p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg021.perseus-grc2</td>
      <td>New Testament</td>
      <td>1 Peter</td>
      <td>1-5_1-14</td>
      <td>p1_2/p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg022.perseus-grc2</td>
      <td>New Testament</td>
      <td>2 Peter</td>
      <td>1-3_1-18</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0031.tlg023.perseus-grc2</td>
      <td>New Testament</td>
      <td>1 John</td>
      <td>1-5_1-21</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0031.tlg024.perseus-grc2</td>
      <td>New Testament</td>
      <td>2 John</td>
      <td>1-1_1-13</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg025.perseus-grc2</td>
      <td>New Testament</td>
      <td>3 John</td>
      <td>1-1_1-15</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg026.perseus-grc2</td>
      <td>New Testament</td>
      <td>Jude</td>
      <td>1-1_1-25</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0031.tlg027.perseus-grc2</td>
      <td>New Testament</td>
      <td>Revelation</td>
      <td>1-22_1-21</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0032.tlg001.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Hellenica</td>
      <td>1-7_1-5_1-27</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg002.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Memorabilia</td>
      <td>1-4_1-8_1-11</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg003.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Economics</td>
      <td>1-21_1-12</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg004.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Symposium</td>
      <td>1-9_1-7</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg005.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Apology</td>
      <td>1-34</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg006.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Anabasis</td>
      <td>1-7_1-8_1-24</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg007.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Cyropaedia</td>
      <td>1-8_1-8_1-27</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg008.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Hiero</td>
      <td>1-11_1-15</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg009.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Agesilaus</td>
      <td>1-11_1-16</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg010.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Constitution of the Lacedaimonians</td>
      <td>1-15_1-9</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg011.perseus-grc2</td>
      <td>Xenophon</td>
      <td>Ways and Means</td>
      <td>1-6_1-3</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg012.perseus-grc2</td>
      <td>Xenophon</td>
      <td>On the Cavalry Commander</td>
      <td>1-9_1-9</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg013.perseus-grc2</td>
      <td>Xenophon</td>
      <td>On the Art of Horsemanship</td>
      <td>1-12_1-14</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0032.tlg014.perseus-grc2</td>
      <td>Xenophon</td>
      <td>On Hunting</td>
      <td>1-13_1-18</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0033.tlg001.perseus-grc2</td>
      <td>Pindar</td>
      <td>Olympian</td>
      <td>1-14_1-24</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0033.tlg002.perseus-grc2</td>
      <td>Pindar</td>
      <td>Pythian</td>
      <td>1-12_1-32</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0033.tlg003.perseus-grc2</td>
      <td>Pindar</td>
      <td>Nemean</td>
      <td>1-11_1-48</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0033.tlg004.perseus-grc2</td>
      <td>Pindar</td>
      <td>Isthmean</td>
      <td>1-8_1-70</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0034.tlg001.perseus-grc2</td>
      <td>Lycurgus</td>
      <td>Against Leocrates</td>
      <td>hyp, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0035.tlg001.perseus-grc2</td>
      <td>Moschus</td>
      <td>Eros Drapeta</td>
      <td>1-29</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg0035.tlg002.perseus-grc2</td>
      <td>Moschus</td>
      <td>Europa</td>
      <td>1-166</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg0035.tlg003.perseus-grc2</td>
      <td>Moschus</td>
      <td>Epitaphius Bios</td>
      <td>1-126</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg0035.tlg004.perseus-grc2</td>
      <td>Moschus</td>
      <td>Megara</td>
      <td>1-125</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg0035.tlg005.perseus-grc2</td>
      <td>Moschus</td>
      <td>Fragmenta</td>
      <td>4-7_1-6</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg0036.tlg001.perseus-grc2</td>
      <td>Bion of Phlossa</td>
      <td>Epitaphius Adonis</td>
      <td>1-98</td>
      <td>m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg0036.tlg002.perseus-grc2</td>
      <td>Bion of Phlossa</td>
      <td>Epithalamium Achillis et Deidameiae</td>
      <td>1-32</td>
      <td>m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg0036.tlg003.perseus-grc2</td>
      <td>Bion of Phlossa</td>
      <td>Fragmenta</td>
      <td>4-18_1-2</td>
      <td>m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg0037.tlg001.1st1K-grc1</td>
      <td>Anacharsis</td>
      <td>Epistulae</td>
      <td>1-10</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0039.tlg001.1st1K-grc1</td>
      <td>Mithridatis Epistula</td>
      <td>Epistula</td>
      <td>1-4</td>
      <td>p1_2/p2_1/p2_2</td>
    </tr>
    <tr>
      <td>tlg0041.tlg001.1st1K-grc1</td>
      <td>Chionis Epistulae</td>
      <td>Epistulae</td>
      <td>1-17_1-3</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0044.tlg001.1st1K-grc1</td>
      <td>Antiochus Epistolographus</td>
      <td>Epistulae</td>
      <td>1-2</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0045.tlg001.1st1K-grc1</td>
      <td>Artaxerxis Epistulae</td>
      <td>Epistulae</td>
      <td>1-2</td>
      <td>p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg0046.tlg001.1st1K-grc1</td>
      <td>Niciae Epistula</td>
      <td>Epistula</td>
      <td>1-1</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0048.tlg001.1st1K-grc1</td>
      <td>Philip II, King of Macedonia</td>
      <td>Epistulae</td>
      <td>1-8_1-1</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0053.tlg001.1st1K-grc1</td>
      <td>Phalaridis Epistulae</td>
      <td>Epistulae</td>
      <td>1-148_1-1</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg0055.tlg001.1st1K-grc1</td>
      <td>Themistocles</td>
      <td>Epistulae</td>
      <td>1-21</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0057.tlg001.1st1K-grc1</td>
      <td>Galen</td>
      <td>Adhortatio ad artes addiscendas</td>
      <td>1-14</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg002.1st1K-grc1</td>
      <td>Galen</td>
      <td>De optima doctrina</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg003.1st1K-grc1</td>
      <td>Galen</td>
      <td>Quod optimus medicus sit quoque philosophus</td>
      <td>1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg004.1st1K-grc1</td>
      <td>Galen</td>
      <td>De sectis ad eos qui introducuntur</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg006.1st1K-grc1</td>
      <td>Galen</td>
      <td>De constitutione artis medicae ad Patrophilum</td>
      <td>prooemium, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg007.1st1K-grc1</td>
      <td>Galen</td>
      <td>Ars Medica</td>
      <td>preface, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0057.tlg008.1st1K-grc1</td>
      <td>Galen</td>
      <td>De elementis ex Hippocrate</td>
      <td>1-2_1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg009.1st1K-grc1</td>
      <td>Galen</td>
      <td>De temperamentis</td>
      <td>1-3_1-21</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg010.1st1K-grc1</td>
      <td>Galen</td>
      <td>De naturalibus facultatibus</td>
      <td>1-3_1-15</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg011.1st1K-grc1</td>
      <td>Galen</td>
      <td>De anatomicis administrationibus</td>
      <td>1-9_1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg012.1st1K-grc1</td>
      <td>Galen</td>
      <td>De ossibus ad tirones</td>
      <td>prooemium, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg013.1st1K-grc1</td>
      <td>Galen</td>
      <td>De venarum arteriarumque dissectione</td>
      <td>1-10</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg014.1st1K-grc1</td>
      <td>Galen</td>
      <td>De nervorum dissectione</td>
      <td>1-17</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg015.1st1K-grc1</td>
      <td>Galen</td>
      <td>De instrumento odoratus</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg016.1st1K-grc1</td>
      <td>Galen</td>
      <td>De uteri dissectione</td>
      <td>1-10</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg017.1st1K-grc1</td>
      <td>Galen</td>
      <td>De usu partium corporis humani I-XI</td>
      <td>1-17_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg018.1st1K-grc1</td>
      <td>Galen</td>
      <td>De motu musculorum</td>
      <td>1-2_1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg019.1st1K-grc1</td>
      <td>Galen</td>
      <td>De Victu Attenuante</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg020.1st1K-grc1</td>
      <td>Galen</td>
      <td>De utilitate respirationis</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg021.1st1K-grc1</td>
      <td>Galen</td>
      <td>De semine</td>
      <td>1-2_1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg022.1st1K-grc1</td>
      <td>Galen</td>
      <td>De foetuum formatione</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg023.1st1K-grc1</td>
      <td>Galen</td>
      <td>An in arteriis sanguis contineatur</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg024.1st1K-grc1</td>
      <td>Galen</td>
      <td>De optima corporis nostri constitutione</td>
      <td>1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg025.1st1K-grc1</td>
      <td>Galen</td>
      <td>De bono habitu</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg027.1st1K-grc1</td>
      <td>Galen</td>
      <td>Quod animi mores corporis temperamenta sequantur</td>
      <td>1-11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg028.1st1K-grc1</td>
      <td>Galen</td>
      <td>De propriorum animi cuiuslibet affectuum dignotione et curatione</td>
      <td>1-10</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg029.1st1K-grc1</td>
      <td>Galen</td>
      <td>De animi cuiuslibet peccatorum dignotione et curatione</td>
      <td>1-7</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg030.1st1K-grc1</td>
      <td>Galen</td>
      <td>De atra bile</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg031.1st1K-grc1</td>
      <td>Galen</td>
      <td>De usu pulsuum</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg032.1st1K-grc1</td>
      <td>Galen</td>
      <td>De placitis Hippocratis et Platonis</td>
      <td>1-9_5-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg033.1st1K-grc1</td>
      <td>Galen</td>
      <td>Thrasybulus sive utrum medicinae sit an gymnasticae hygieine</td>
      <td>1-47</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg034.1st1K-grc1</td>
      <td>Galen</td>
      <td>De parvae pilae exercitio</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg035.1st1K-grc2</td>
      <td>Galen</td>
      <td>De venereis</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg036.1st1K-grc1</td>
      <td>Galen</td>
      <td>De sanitate tuenda</td>
      <td>1-6_1-15</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg037.1st1K-grc1</td>
      <td>Galen</td>
      <td>De alimentorum facultatibus</td>
      <td>1-3_1-41_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg038.1st1K-grc1</td>
      <td>Galen</td>
      <td>De rebus boni malique suci</td>
      <td>1-14</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg039.1st1K-grc1</td>
      <td>Galen</td>
      <td>De ptisana</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg040.1st1K-grc1</td>
      <td>Galen</td>
      <td>De dignotione ex insomniis</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg041.1st1K-grc1</td>
      <td>Galen</td>
      <td>De morborum differentiis</td>
      <td>1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg042.1st1K-grc1</td>
      <td>Galen</td>
      <td>De causis morborum</td>
      <td>1-11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg043.1st1K-grc1</td>
      <td>Galen</td>
      <td>De symptomatum differentiis</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg044.1st1K-grc1</td>
      <td>Galen</td>
      <td>De symptomatum causis</td>
      <td>1-3_1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg045.1st1K-grc1</td>
      <td>Galen</td>
      <td>De differentiis febrium</td>
      <td>1-2_1-18</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg046.1st1K-grc1</td>
      <td>Galen</td>
      <td>De morborum temporibus</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg047.1st1K-grc1</td>
      <td>Galen</td>
      <td>De totius morbi temporibus</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg048.1st1K-grc1</td>
      <td>Galen</td>
      <td>De typis</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg049.1st1K-grc1</td>
      <td>Galen</td>
      <td>Adversus eos qui de typis scripserunt vel de circuitibus</td>
      <td>1-7</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg050.1st1K-grc1</td>
      <td>Galen</td>
      <td>De plenitudine</td>
      <td>1-11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg051.1st1K-grc1</td>
      <td>Galen</td>
      <td>De tremore, palpitatione, convulsione et rigore</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg052.1st1K-grc1</td>
      <td>Galen</td>
      <td>De comate secundum Hippocratem</td>
      <td>1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg053.1st1K-grc1</td>
      <td>Galen</td>
      <td>De marcore</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg054.1st1K-grc1</td>
      <td>Galen</td>
      <td>De tumoribus praeter naturam</td>
      <td>1-17</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg055.1st1K-grc1</td>
      <td>Galen</td>
      <td>De inaequali intemperie</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg056.1st1K-grc1</td>
      <td>Galen</td>
      <td>De difficultate respirationis</td>
      <td>1-3_1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg057.1st1K-grc1</td>
      <td>Galen</td>
      <td>De locis affectis</td>
      <td>1-6_1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg058.1st1K-grc1</td>
      <td>Galen</td>
      <td>De pulsibus ad tirones</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg059.1st1K-grc1</td>
      <td>Galen</td>
      <td>De differentiis pulsuum</td>
      <td>1-4_1-17</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg060.1st1K-grc1</td>
      <td>Galen</td>
      <td>De dignoscendis pulsibus</td>
      <td>1-4_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg061.1st1K-grc1</td>
      <td>Galen</td>
      <td>De causis pulsuum</td>
      <td>1-4_1-27</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg062.1st1K-grc1</td>
      <td>Galen</td>
      <td>De praesagitione ex pulsibus</td>
      <td>1-4_1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg063.1st1K-grc1</td>
      <td>Galen</td>
      <td>Synopsis librorum suorum de pulsibus</td>
      <td>1-28</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg064.1st1K-grc1</td>
      <td>Galen</td>
      <td>De crisibus</td>
      <td>1-3_1-11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg065.1st1K-grc1</td>
      <td>Galen</td>
      <td>De diebus decretoriis</td>
      <td>1-3_1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg066.1st1K-grc1</td>
      <td>Galen</td>
      <td>De methodo medendi</td>
      <td>1-14_1-19</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg067.1st1K-grc1</td>
      <td>Galen</td>
      <td>Ad Glauconem de methodo medendi</td>
      <td>1-2_1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg068.1st1K-grc1</td>
      <td>Galen</td>
      <td>De venae sectione adversus Erasistratum</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg069.1st1K-grc1</td>
      <td>Galen</td>
      <td>De venae sectione adversus Erasistrateos Romae degentes</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg070.1st1K-grc1</td>
      <td>Galen</td>
      <td>De curandi ratione per venae sectionem</td>
      <td>1-23</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg071.1st1K-grc1</td>
      <td>Galen</td>
      <td>De hirudinibus, revulsione, cucurbitula, incisione et scarificatione</td>
      <td>1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg072.1st1K-grc1</td>
      <td>Galen</td>
      <td>De purgantium medicamentorum facultate</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg073.1st1K-grc1</td>
      <td>Galen</td>
      <td>Quos quibus catharticis medicamentis et quando purgare oporteat</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg074.1st1K-grc1</td>
      <td>Galen</td>
      <td>Pro puero epileptico consilium</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg075.1st1K-grc1</td>
      <td>Galen</td>
      <td>De simplicium medicamentorum temperamentis ac facultatibus I-VI</td>
      <td>6-11_1-2_1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg076.1st1K-grc1</td>
      <td>Galen</td>
      <td>De compositione medicamentorum secundum locos libri X</td>
      <td>1-10_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg077.1st1K-grc1</td>
      <td>Galen</td>
      <td>De compositione medicamentorum per genera</td>
      <td>1-7_1-16</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg078.1st1K-grc1</td>
      <td>Galen</td>
      <td>De antidotis</td>
      <td>1-2_1-16</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg079.1st1K-grc1</td>
      <td>Galen</td>
      <td>De theriaca ad Pisonem</td>
      <td>1-19</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0057.tlg081.1st1K-grc1</td>
      <td>Galen</td>
      <td>Institutio logica</td>
      <td>1-19</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg082.1st1K-grc1</td>
      <td>Galen</td>
      <td>De sophismatis seu captionibus penes dictionem</td>
      <td>1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg083.1st1K-grc1</td>
      <td>Galen</td>
      <td>De praenotione ad Epigenem</td>
      <td>1-14</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg084.1st1K-grc1</td>
      <td>Galen</td>
      <td>De substantia facultatum naturalium fragmentum</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg085.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis De natura hominis</td>
      <td>1-2_prooemium, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg086.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis vel Polybi Opus de Salubri Victus Ratione Privatorum Commentarius</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg087.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis De victu acutorum</td>
      <td>1-4_1-105</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg089.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis Epidemiarum I</td>
      <td>1-6_1-6_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, case1, case2, case3, case4, case5, case6, case7, case8, case9, case10, case11, case12, case13, case14, 87, 88</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg092.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis Aphorismos Commentarii VII</td>
      <td>1-7_1-81</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg093.1st1K-grc1</td>
      <td>Galen</td>
      <td>Adversus Lycum</td>
      <td>1-7</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg094.1st1K-grc1</td>
      <td>Galen</td>
      <td>Adversus ea quae Juliano in Hippocratis Aphorismos enuntiata sunt</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg095.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis De articulis</td>
      <td>1-4_prooemium, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg096.1st1K-grc1</td>
      <td>Galen</td>
      <td>De Humero iis Modis Prolapso quos Hippocrates non Vidit</td>
      <td>excursus, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg099.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis Prognosticum</td>
      <td>1-3_1-42</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg100.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis De fracturis</td>
      <td>1-3_prooemium, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg101.1st1K-grc1</td>
      <td>Galen</td>
      <td>In Hippocratis De officina medici</td>
      <td>1-3_prooemium, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg102.1st1K-grc1</td>
      <td>Galen</td>
      <td>De musculorum dissectione ad tirones</td>
      <td>1-37</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg103.1st1K-grc1</td>
      <td>Galen</td>
      <td>De consuetudinibus</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg107.1st1K-grc1</td>
      <td>Galen</td>
      <td>De experientia medica</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0057.tlg114.1st1K-grc1</td>
      <td>Galen</td>
      <td>De causis respirationis</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0058.tlg001.perseus-grc2</td>
      <td>Aeneas Tacticus</td>
      <td>Poliorcetica</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40_1-8</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg001.perseus-grc1</td>
      <td>Plato</td>
      <td>Euthyphro</td>
      <td>2-16</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg002.perseus-grc2</td>
      <td>Plato</td>
      <td>Apology</td>
      <td>17-42</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg003.perseus-grc2</td>
      <td>Plato</td>
      <td>Crito</td>
      <td>43-54</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg004.perseus-grc2</td>
      <td>Plato</td>
      <td>Phaedo</td>
      <td>57-118</td>
      <td>m4_1m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg005.perseus-grc2</td>
      <td>Plato</td>
      <td>Cratylus</td>
      <td>383-440</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg006.perseus-grc2</td>
      <td>Plato</td>
      <td>Theaetetus</td>
      <td>142-210</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg007.perseus-grc2</td>
      <td>Plato</td>
      <td>Sophist</td>
      <td>216-268</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg008.perseus-grc2</td>
      <td>Plato</td>
      <td>Statesman</td>
      <td>257-311</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg009.perseus-grc2</td>
      <td>Plato</td>
      <td>Parmenides</td>
      <td>126-166</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg010.perseus-grc2</td>
      <td>Plato</td>
      <td>Philebus</td>
      <td>11-67</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg011.perseus-grc2</td>
      <td>Plato</td>
      <td>Symposium</td>
      <td>172-223</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg012.perseus-grc2</td>
      <td>Plato</td>
      <td>Phaedrus</td>
      <td>227-279</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg013.perseus-grc2</td>
      <td>Plato</td>
      <td>Alcibiades 1</td>
      <td>103-135</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg014.perseus-grc2</td>
      <td>Plato</td>
      <td>Alcibiades 2</td>
      <td>138-151</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg015.perseus-grc2</td>
      <td>Plato</td>
      <td>Hipparchus</td>
      <td>225-232</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg016.perseus-grc2</td>
      <td>Plato</td>
      <td>Lovers</td>
      <td>132-139</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0059.tlg017.perseus-grc2</td>
      <td>Plato</td>
      <td>Theages</td>
      <td>121-131</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg018.perseus-grc2</td>
      <td>Plato</td>
      <td>Charmides</td>
      <td>153-176</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg019.perseus-grc2</td>
      <td>Plato</td>
      <td>Laches</td>
      <td>178-201</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg020.perseus-grc2</td>
      <td>Plato</td>
      <td>Lysis</td>
      <td>203-223</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg021.perseus-grc2</td>
      <td>Plato</td>
      <td>Euthydemus</td>
      <td>271-307</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg022.perseus-grc2</td>
      <td>Plato</td>
      <td>Protagoras</td>
      <td>309-362</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg023.perseus-grc2</td>
      <td>Plato</td>
      <td>Gorgias</td>
      <td>447-527</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg024.perseus-grc2</td>
      <td>Plato</td>
      <td>Meno</td>
      <td>70-100</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg025.perseus-grc2</td>
      <td>Plato</td>
      <td>Greater Hippias</td>
      <td>281-304</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg026.perseus-grc2</td>
      <td>Plato</td>
      <td>Lesser Hippias</td>
      <td>363-376</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg027.perseus-grc2</td>
      <td>Plato</td>
      <td>Ion</td>
      <td>530-542</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg028.perseus-grc2</td>
      <td>Plato</td>
      <td>Menexenus</td>
      <td>234-249</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg029.perseus-grc2</td>
      <td>Plato</td>
      <td>Cleitophon</td>
      <td>406-410</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg030.perseus-grc2</td>
      <td>Plato</td>
      <td>Republic</td>
      <td>1-10_327-621</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg031.perseus-grc2</td>
      <td>Plato</td>
      <td>Timaeus</td>
      <td>17-92</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg032.perseus-grc2</td>
      <td>Plato</td>
      <td>Critias</td>
      <td>106-121</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg033.perseus-grc2</td>
      <td>Plato</td>
      <td>Minos</td>
      <td>313-321</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg034.perseus-grc2</td>
      <td>Plato</td>
      <td>Laws</td>
      <td>1-12_624-969</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg035.perseus-grc2</td>
      <td>Plato</td>
      <td>Epinomis</td>
      <td>973-992</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg036.perseus-grc2</td>
      <td>Plato</td>
      <td>Letters</td>
      <td>1-13_309-363</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0059.tlg037.1st1K-grc1</td>
      <td>Plato</td>
      <td>Definitiones</td>
      <td>1-1</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0060.tlg001.perseus-grc4</td>
      <td>Diodorus Siculus</td>
      <td>Historical Library</td>
      <td>11-17_arg, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg001.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Asinus</td>
      <td>1-56</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg002.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Amores</td>
      <td>1-54</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg003.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Demosthenis encomium</td>
      <td>1-50</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg004.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Halcyon</td>
      <td>1-8</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg005.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Ocypus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg006.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Cynicus</td>
      <td>1-20</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg007.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Philopatris</td>
      <td>1-29</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0061.tlg008.1st1K-grc1</td>
      <td>Pseudo-Lucian</td>
      <td>Charidemus</td>
      <td>1-28</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg001.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Phalaris</td>
      <td>1-2_1-13</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0062.tlg002.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Hippias</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg003.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Bacchus</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg004.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Hercules</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg005.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Electrum</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg006.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Muscae Encomium</td>
      <td>1-12</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0062.tlg007.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Nigrinus</td>
      <td>prologue, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg008.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Demonax</td>
      <td>1-67</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg009.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De Domo</td>
      <td>1-32</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0062.tlg010.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Patriae encomium</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg011.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Macrobii</td>
      <td>1-29</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg012.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Verae historiae</td>
      <td>1-2_1-47</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg013.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Calumniae non temere credundum</td>
      <td>1-32</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg014.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Judicium vocalium</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg015.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Symposium</td>
      <td>1-48</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg016.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Cataplus</td>
      <td>1-29</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg017.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Juppiter Confutatus</td>
      <td>1-19</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg018.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Juppiter Tragoedus</td>
      <td>1-53</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg019.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Gallus</td>
      <td>1-33</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg020.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Prometheus</td>
      <td>1-21</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg021.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Icaromenippus</td>
      <td>1-34</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg022.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Timon</td>
      <td>1-58</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg023.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Contemplantes</td>
      <td>1-24</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg024.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Vitarum auctio</td>
      <td>1-27</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg025.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Piscator</td>
      <td>1-52</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg026.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Bis accusatus sive tribunalia</td>
      <td>1-35</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg027.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De Sacrificiis</td>
      <td>1-15</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg028.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Adversus indoctum et libros multos ementem</td>
      <td>1-30</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg029.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Somnium sive vita Luciani</td>
      <td>1-18</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg030.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De parasito sive artem esse parasiticam</td>
      <td>1-61</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg031.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Philopseudes sive incredulus</td>
      <td>1-40</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg032.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Dearum judicium</td>
      <td>1-16</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg033.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De mercede</td>
      <td>1-42</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg034.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Anacharsis</td>
      <td>1-40</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg035.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Necyomantia</td>
      <td>1-22</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg036.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De luctu</td>
      <td>1-24</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg037.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Rhetorum praeceptor</td>
      <td>1-26</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg038.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Alexander</td>
      <td>1-61</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg039.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Imagines</td>
      <td>1-23</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg040.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Pro imaginibus</td>
      <td>1-29</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg041.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De Syria dea</td>
      <td>1-60</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg042.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De Morte Peregrini</td>
      <td>1-45</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg043.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Fugitivi</td>
      <td>1-33</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg044.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Toxaris vel amicitia</td>
      <td>1-63</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg045.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De saltatione</td>
      <td>1-85</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg046.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Lexiphanes</td>
      <td>1-25</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg047.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Eunuchus</td>
      <td>1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg048.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>De astrologia</td>
      <td>1-29</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg049.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Pseudologista</td>
      <td>1-32</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg050.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Deorum concilium</td>
      <td>1-19</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg051.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Tyrannicida</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0062.tlg052.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Abdicatus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg053.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Quomodo historia conscribenda sit</td>
      <td>1-63</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg054.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Dipsades</td>
      <td>1-9</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0062.tlg055.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Saturnalia</td>
      <td>1-39</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg056.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Herodotus</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg057.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Zeuxis</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg058.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Pro lapsu inter salutandum</td>
      <td>1-19</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg059.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Apologia</td>
      <td>1-15</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg060.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Harmonides</td>
      <td>1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg061.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Hesiod</td>
      <td>1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg062.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Scytha</td>
      <td>1-11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg063.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Hermotimus</td>
      <td>1-86</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg064.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Prometheus es in verbis</td>
      <td>1-7</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg065.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Navigium</td>
      <td>1-46</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg066.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Dialogi mortuorum</td>
      <td>1-30_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg067.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Dialogi Marini</td>
      <td>1-15_1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg068.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Dialogi deorum</td>
      <td>1-26_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg069.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Dialogi meretricii</td>
      <td>1-15_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg070.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Soleocista</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0062.tlg071.perseus-grc2</td>
      <td>Lucian of Samosata</td>
      <td>Podagra</td>
      <td>1-334</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0064.tlg001.1st1K-grc1</td>
      <td>Hanno</td>
      <td>Periplus Hannonis</td>
      <td>1-18</td>
      <td>m5_1/m5_2/m4_1/m4_2/m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg0065.tlg001.1st1K-grc1</td>
      <td>Scylax of Caryanda</td>
      <td>Periplus Scylacis</td>
      <td>1-4_1-114</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0066.tlg001.1st1K-grc1</td>
      <td>Heraclides, Criticus</td>
      <td>Descriptio Graeciae</td>
      <td>1-3_1-8</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0067.tlg001.1st1K-grc1</td>
      <td>Agatharchides</td>
      <td>De Rubro Mari</td>
      <td>5-3_23-114_1-</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0068.tlg001.1st1K-grc1</td>
      <td>Pseudo-Scymnus</td>
      <td>Ad Nicomedem regem, vv. 1-980</td>
      <td>1-3_1-980</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0069.tlg001.1st1K-grc1</td>
      <td>Dionysius, Calliphontis</td>
      <td>Descriptio Graeciae</td>
      <td>1-2_1-150</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0070.tlg001.1st1K-grc1</td>
      <td>Isidore, of Charax</td>
      <td>Mansiones Parthicae</td>
      <td>1-3_1-35</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0071.tlg001.1st1K-grc1</td>
      <td>Pseudo-Arrianus</td>
      <td>Anonymi (Arriani, ut fertur) periplus maris Erythraei</td>
      <td>2-66</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0074.tlg001.perseus-grc2</td>
      <td>Arrian</td>
      <td>Ἀλεξάνδρου Ἀνάβασις</td>
      <td>1-7_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0074.tlg002.perseus-grc2</td>
      <td>Arrian</td>
      <td>Indica</td>
      <td>1-43_1-14</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0074.tlg003.perseus-grc2</td>
      <td>Arrian</td>
      <td>Cynegeticus</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0074.tlg004.perseus-grc2</td>
      <td>Arrian</td>
      <td>Periplus Ponti Euxini</td>
      <td>1-25_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0074.tlg005.perseus-grc2</td>
      <td>Arrian</td>
      <td>Tactica</td>
      <td>1-44_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0074.tlg006.perseus-grc2</td>
      <td>Arrian</td>
      <td>Acies Contra Alanos</td>
      <td>1-31</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0074.tlg008.1st1K-grc1</td>
      <td>Arrian</td>
      <td>Epistula ad Lucium Gellium</td>
      <td>1-8</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0075.tlg001.1st1K-grc1</td>
      <td>Pseudo-Arrianus</td>
      <td>Anonymi (Arriani, ut fertur) periplus ponti Euxini</td>
      <td>1-2_1-92</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0077.tlg001.1st1K-grc1</td>
      <td>Stadiasmus Magni Maris</td>
      <td>Stadiasmus Magni Maris</td>
      <td>1-15_1a, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 278, 279, 280, 281, 282, 284, 285, 286, 287, 288, 289, 290, 291, 292, 293, 294, 295, 296, 297, 298, 299, 300, 301, 302, 303, 304, 305, 305a, 306, 307, 308, 309, 310, 311, 312, 313, 314, 315, 316, 317, 318, 319, 320, 321, 322, 323, 324, 325, 326, 327, 328, 329, 330, 331, 332, 333, 334, 335, 336, 337, 338, 339, 340, 341, 342, 343, 344, 345, 346, 347, 348, 349, 350, 351, 352, 353, 354, 355</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg001.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>Antiquitates Romanae</td>
      <td>1-20_1-17_1-2</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg002.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De antiquis oratoribus</td>
      <td>1-4</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg003.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Lysia</td>
      <td>1-34</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg004.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Isocrate</td>
      <td>1-20</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg005.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Isaeo</td>
      <td>1-20</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg006.1st1K-grc1</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Demosthenis dictione</td>
      <td>1-58</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg007.1st1K-grc1</td>
      <td>Dionysius of Halicarnassus</td>
      <td>Libri secundi de antiquis oratoribus reliquiae</td>
      <td>59-59</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg008.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>Ad Ammaeum</td>
      <td>1-12</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg009.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Dinarcho</td>
      <td>1-13</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg010.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Thucydide</td>
      <td>1-55</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg011.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Thucydidis idiomatibus</td>
      <td>1-17</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg012.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De Compositione Verborum</td>
      <td>1-26</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg013.1st1K-grc1</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De compositione verborum (epitome)</td>
      <td>1-26</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg014.1st1K-grc1</td>
      <td>Dionysius of Halicarnassus</td>
      <td>De imitatione (fragmenta)</td>
      <td>26-35_1-1_1-1</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg015.perseus-grc2</td>
      <td>Dionysius of Halicarnassus</td>
      <td>Epistula ad Pompeium Geminum</td>
      <td>1-6_1-11</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0081.tlg016.1st1K-grc1</td>
      <td>Dionysius of Halicarnassus</td>
      <td>Ars Rhetorica</td>
      <td>1-11_1-10</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0082.tlg001.1st1K-grc1</td>
      <td>Apollonius Dyscolus</td>
      <td>De pronominibus</td>
      <td>1-240</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0082.tlg002.1st1K-grc1</td>
      <td>Apollonius Dyscolus</td>
      <td>De adverbiis</td>
      <td>1-147</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0082.tlg003.1st1K-grc1</td>
      <td>Apollonius Dyscolus</td>
      <td>De Conjuctionibus</td>
      <td>479-526</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0082.tlg004.1st1K-grc1</td>
      <td>Apollonius Dyscolus</td>
      <td>De constructione</td>
      <td>1-4_1-77</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0083.tlg003.1st1K-grc1</td>
      <td>Dionysius of Byzantium</td>
      <td>De Bospori Navigatione</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0084.tlg001.1st1K-grc1</td>
      <td>Dionysius Periegetes</td>
      <td>Orbis Descriptio</td>
      <td>1-1186</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0085.tlg001.1st1K-grc1</td>
      <td>Aeschylus</td>
      <td>Supplices</td>
      <td>1-1073</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0085.tlg002.1st1K-grc1</td>
      <td>Aeschylus</td>
      <td>Persians</td>
      <td>1-1076</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0085.tlg003.1st1K-grc1</td>
      <td>Aeschylus</td>
      <td>Prometheus Bound</td>
      <td>1-1093</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0085.tlg004.1st1K-grc1</td>
      <td>Aeschylus</td>
      <td>Seven Against Thebes</td>
      <td>1-1084</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0085.tlg005.1st1K-grc1</td>
      <td>Aeschylus</td>
      <td>Agamemnon</td>
      <td>1-1673</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0085.tlg006.1st1K-grc1</td>
      <td>Aeschylus</td>
      <td>Libation Bearers</td>
      <td>1-1076</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0085.tlg007.1st1K-grc1</td>
      <td>Aeschylus</td>
      <td>Eumenides</td>
      <td>1-1047</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg001.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Analytica priora</td>
      <td>priora, posteriora_1-2_1-19</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg002.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De anima</td>
      <td>1-3_1-13</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg003.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Res Publica Atheniensium</td>
      <td>1-69</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg004.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De audibilibus</td>
      <td>1-74</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg005.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De caelo</td>
      <td>1-4_1-5</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg006.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Categoriae</td>
      <td>1-15</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg007.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De coloribus</td>
      <td>1-6_1-27</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg008.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De divinatione per somnum</td>
      <td>1-2</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg009.perseus-grc2</td>
      <td>Aristotle</td>
      <td>Eudemian Ethics</td>
      <td>1-8_1-3</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg010.perseus-grc2</td>
      <td>Aristotle</td>
      <td>Nicomachean Ethics</td>
      <td>1-10_1-9</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg011.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Epistulae</td>
      <td>1-6</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg012.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De Generatione Animalium</td>
      <td>1-5_1-8</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg013.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De generatione et corruptione</td>
      <td>1-2_1-11</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg014.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Historia animalium</td>
      <td>1-10_1-7</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg015.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De animalium incessu</td>
      <td>1-19</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg016.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De insomniis</td>
      <td>1-3</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg017.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De interpretatione</td>
      <td>1-14</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg018.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De iuventute et senectute, De vita et morte</td>
      <td>1-6</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg019.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De lineis insecabilibus</td>
      <td>1-60</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg020.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De longitudine et brevitate vitae</td>
      <td>1-6</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg021.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De animalium motione</td>
      <td>1-11</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg022.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Magna Moralia</td>
      <td>1-2_1-17_1-2</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg023.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Mechanica</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35_1-5</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg024.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De memoria et reminiscentia</td>
      <td>1-2</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg025.perseus-grc2</td>
      <td>Aristotle</td>
      <td>Metaphysics</td>
      <td>1-14_1-6</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg026.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Meteorologica</td>
      <td>1-4_1-12</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg027.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Mirabilium auscultationes</td>
      <td>1-178_1-1</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg029.perseus-grc2</td>
      <td>Aristotle</td>
      <td>Economics</td>
      <td>1-2_1-2_1-41</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg030.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De partibus animalium</td>
      <td>1-4_1-13_1-1</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg031.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Physica</td>
      <td>1-8_1-10</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg032.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Physiognomonica</td>
      <td>1-6_1-60</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg034.digicorpus-grc2</td>
      <td>Aristotle</td>
      <td>Poetics</td>
      <td>1-26_1-16</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg035.perseus-grc2</td>
      <td>Aristotle</td>
      <td>Politics</td>
      <td>1-8_1252a, 1252b, 1253a, 1253b, 1254a, 1254b, 1255a, 1255b, 1256a, 1256b, 1257a, 1257b, 1258a, 1258b, 1259a, 1259b, 1260a, 1260b, 1261a, 1261b, 1262a, 1262b, 1263a, 1263b, 1264a, 1264b, 1265a, 1265b, 1266a, 1266b, 1267a, 1267b, 1268a, 1268b, 1269a, 1269b, 1270a, 1270b, 1271a, 1271b, 1272a, 1272b, 1273a, 1273b, 1274a, 1274b, 1275a, 1275b, 1276a, 1276b, 1277a, 1277b, 1278a, 1278b, 1279a, 1279b, 1280a, 1280b, 1281a, 1281b, 1282a, 1282b, 1283a, 1283b, 1284a, 1284b, 1285a, 1285b, 1286a, 1286b, 1287a, 1287b, 1288a, 1288b, 1289a, 1289b, 1290a, 1290b, 1291a, 1291b, 1292a, 1292b, 1293a, 1293b, 1294a, 1294b, 1295a, 1295b, 1296a, 1296b, 1297a, 1297b, 1298a, 1298b, 1299a, 1299b, 1300a, 1300b, 1301a, 1301b, 1302a, 1302b, 1303a, 1303b, 1304a, 1304b, 1305a, 1305b, 1306a, 1306b, 1307a, 1307b, 1308a, 1308b, 1309a, 1309b, 1310a, 1310b, 1311a, 1311b, 1312a, 1312b, 1313a, 1313b, 1314a, 1314b, 1315a, 1315b, 1316a, 1316b, 1317a, 1317b, 1318a, 1318b, 1319a, 1319b, 1320a, 1320b, 1321a, 1321b, 1322a, 1322b, 1323a, 1323b, 1324a, 1324b, 1325a, 1325b, 1326a, 1326b, 1327a, 1327b, 1328a, 1328b, 1329a, 1329b, 1330a, 1330b, 1331a, 1331b, 1332a, 1332b, 1333a, 1333b, 1334a, 1334b, 1335a, 1335b, 1336a, 1336b, 1337a, 1337b, 1338a, 1338b, 1339a, 1339b, 1340a, 1340b, 1341a, 1341b, 1342a, 1342b</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg036.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Problemata</td>
      <td>1-38_1-11</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg037.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De respiratione</td>
      <td>1-21</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg038.perseus-grc2</td>
      <td>Aristotle</td>
      <td>Rhetoric</td>
      <td>1-3_1-19_1-6</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg039.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De plantis</td>
      <td>prol, 1, 2_1-10_1-9</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg040.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De sophisticis elenchis</td>
      <td>1-33</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg041.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De sensu et sensibilibus</td>
      <td>1-7_1-28</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg042.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De somno et vigilia</td>
      <td>1-3</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg043.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De spiritu</td>
      <td>1-9</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg044.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Topica</td>
      <td>1-8_1-14</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg045.perseus-grc2</td>
      <td>Aristotle</td>
      <td>On Virtues and Vices</td>
      <td>1249-1249</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0086.tlg046.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De ventorum situ et nominibus</td>
      <td>1-10</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg047.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De Xenophane, de Zenone, de Gorgia</td>
      <td>Xenoph, Zenon, Georg_1-6_1-17</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg048.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Divisiones Aristoteleae</td>
      <td>A, B_1-69_col1, col2, 51</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg052.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>De anima (codicis E fragmenta recensionis a vulgata diversae)</td>
      <td>1-4</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0086.tlg054.1st1K-grc1</td>
      <td>Aristotle</td>
      <td>Physica (textus alter)</td>
      <td>1-3</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg001.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>De prosodia catholica</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg002.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>De enclisi</td>
      <td>1-26</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg004.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ διχρόνων</td>
      <td>1-71</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg005.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ πνευμάτων</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg006.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ Ἀττικῆς προσῳδίας</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg007.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ Ἰλιακῆς προσῳδίας</td>
      <td>1-24_8-793</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg008.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ Ὀδυσσειακῆς προσῳδίας</td>
      <td>1-24_1-417</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg009.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ παθῶν</td>
      <td>1-437</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg009a.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Ἐκ τῶν Ἡρωδιανοῦ ὑπομνημάτων τῶν περὶ παθῶν Διδύμου</td>
      <td>1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg010.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ συντάξεως τῶν στοιχείων</td>
      <td>1-28</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg011.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ ὀρθογραφίας</td>
      <td>1-3_1-24_1-35_1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg012.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ ὀνομάτων</td>
      <td>1-29</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg013.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ κλίσεως ὀνομάτων</td>
      <td>1-2_1-360</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg014.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Εἰς τὸ περὶ γενῶν Ἀπολλωνίου ὑπόμνημα</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg015.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Μονόβιβλον περὶ τοῦ ὕδωρ</td>
      <td>1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg016.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ τοῦ ζώς</td>
      <td>1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg017.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ συζυγιῶν</td>
      <td>1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg018.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Μονόβιβλον περὶ τοῦ μὴ πάντα τὰ ῥήματα κλίνεσθαι εἰς πάντας τοὺς χρόνους</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg019.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ μετοχῶν</td>
      <td>1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg020.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Μονόβιβλον περὶ τοῦ ἦν</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg021.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ ῥημάτων</td>
      <td>1-44_1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg022.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ τῶν εἰς μι</td>
      <td>pro, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg023.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ ἀντωνυμιῶν</td>
      <td>1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg024.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ ἐπιρρημάτων</td>
      <td>1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg025.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>De figuris</td>
      <td>1-0</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg026.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ παρωνύμων</td>
      <td>1-2_1-602</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg027.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ ῥηματικῶν ὀνομάτων</td>
      <td>1-78</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg028.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ μονοσυλλάβων</td>
      <td>1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg029.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ γάμου καὶ συμβιώσεως</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg030.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Συμπόσιον</td>
      <td>1-17</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg031.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Προτάσεις</td>
      <td>1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg032.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Εἰς τὴν Ἀπολλωνίου εἰσαγωγήν</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0087.tlg033.1st1K-grc1</td>
      <td>Aelius Herodianus</td>
      <td>Περὶ μονήρους λέξεως</td>
      <td>prologue, 1, 2_1-87</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0088.tlg001.1st1K-grc1</td>
      <td>Aristoxenus</td>
      <td>Ἁρμονικὰ στοιχεῖα</td>
      <td>1-2_1-74</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0090.tlg001.opp-grc1</td>
      <td>Agathemerus</td>
      <td>Geographiae informatio</td>
      <td>1-5_1-26</td>
      <td>p1_2/p2_1/p2_2</td>
    </tr>
    <tr>
      <td>tlg0092.tlg001.1st1K-grc1</td>
      <td>Anonymi Geographiae Expositio Compendiaria</td>
      <td>Geographiae expositio compendiaria</td>
      <td>1-15_1-3</td>
      <td>p1_2/p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg0093.ogl001.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De odoribus</td>
      <td>1-14_1-69</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.ogl002.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De signis tempestatum</td>
      <td>1-4_1-57</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg001.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>Enquiry into Plants</td>
      <td>1-9_1-20_1-6</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg002.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De causis plantarum</td>
      <td>1-6_1-20_1-4</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg003.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De sensu et sensibilibus</td>
      <td>1-1_1-16</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg004.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De lapidibus</td>
      <td>2-2_1-9</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg005.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De igne</td>
      <td>1-13_1-76</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg006.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>Metaphysica</td>
      <td>1-34</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg009.perseus-grc2</td>
      <td>Theophrastus</td>
      <td>Characters</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30_1-20</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x01.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Odoribus</td>
      <td>1-14_1-71</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x02.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Ventis</td>
      <td>1-10_1-62</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x03.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Signis Tempestatum</td>
      <td>1-4_1-57</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x04.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Lassitudine</td>
      <td>1-1_1-18</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x05.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Vertigine</td>
      <td>1-13</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x06.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Sudore</td>
      <td>1-40</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x07.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Animi Defectione</td>
      <td>1-7</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x08.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>De Nervorum Resolutione</td>
      <td>1-1</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0093.tlg010x09.1st1K-grc1</td>
      <td>Theophrastus</td>
      <td>Fragmenta varia</td>
      <td>13-190_1-1</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0094.tlg001.1st1K-grc1</td>
      <td>Pseudo-Plutarch</td>
      <td>De Fluviis</td>
      <td>1-25_1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0094.tlg002.perseus-grc2</td>
      <td>Pseudo-Plutarch</td>
      <td>De musica</td>
      <td>1-44</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0094.tlg003.perseus-grc2</td>
      <td>Pseudo-Plutarch</td>
      <td>Placita Philosophorum</td>
      <td>1-5_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, intro, 31, 32</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0096.tlg002.1st1K-grc1</td>
      <td>Aesop</td>
      <td>Fabulae</td>
      <td>1-426</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg0097.tlg001.1st1K-grc1</td>
      <td>Diogenianus of Heraclea</td>
      <td>Paroemiae (epitome operis sub nomine Diogeniani) (e cod. Mazarinco)</td>
      <td>pref, 1, 2, 3, 4, 5, 6, 7, 8_a, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 77a, 77b, 83a, 83b, 82a, 82b, 95a, 95b, 36a, 36b, 67a, 67b, 70a, 70b, 97a, 97b</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0098.tlg001.1st1K-grc1</td>
      <td>Zenobius Sophista</td>
      <td>Epitome collectionum Lucilli Tarrhaei et Didymi</td>
      <td>1-6_1-52</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0099.tlg001.perseus-grc2</td>
      <td>Strabo</td>
      <td>Geography</td>
      <td>1-17_1-3_1-25</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0099.tlg004.1st1K-grc1</td>
      <td>Strabo</td>
      <td>Geographiae Chrestomathia</td>
      <td>1-17_1-67</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0199.tlg001.perseus-grc2</td>
      <td>Bacchylides</td>
      <td>Epinicians</td>
      <td>1-14b_1-10</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0199.tlg002.perseus-grc2</td>
      <td>Bacchylides</td>
      <td>Dithyrambs</td>
      <td>15-20_1-11</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0233.tlg001.1st1K-grc1</td>
      <td>Hipponax</td>
      <td>Fragmentum (128)</td>
      <td>frag128, similes, testimonium, variants, commentary</td>
      <td>m6_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg001.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 1</td>
      <td>1-8</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg002.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 2</td>
      <td>9-17</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg003.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 3</td>
      <td>17-28</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg004.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 4</td>
      <td>28-31</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg005.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 5</td>
      <td>31-36</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg006.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 6</td>
      <td>36-40</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg007.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 7</td>
      <td>41-46</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg008.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 8</td>
      <td>47-56</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg009.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 9</td>
      <td>56-67</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg010.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 10</td>
      <td>68-75</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg011.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 11</td>
      <td>75-80</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg012.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 12</td>
      <td>80-90</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg013.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 13</td>
      <td>91-197</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg014.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 14</td>
      <td>197-228</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg015.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 15</td>
      <td>229-235</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg016.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 16</td>
      <td>236-247</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg017.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 17</td>
      <td>247-251</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg018.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 18</td>
      <td>252-256</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg019.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 19</td>
      <td>256-260</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg020.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 20</td>
      <td>260-263</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg021.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 21</td>
      <td>263-269</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg022.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 22</td>
      <td>269-273</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg023.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 23</td>
      <td>273-290</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg024.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 24</td>
      <td>291-309</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg025.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 25</td>
      <td>309-320</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg026.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 26</td>
      <td>321-346</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg027.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 27</td>
      <td>347-361</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg028.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 28</td>
      <td>362-362</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg029.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 29</td>
      <td>363-375</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg030.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 30</td>
      <td>376-391</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg031.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 31</td>
      <td>391-399</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg032.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 32</td>
      <td>399-406</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg033.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 33</td>
      <td>407-426</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg034.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 34</td>
      <td>427-447</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg035.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 35</td>
      <td>448-457</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg036.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 36</td>
      <td>457-465</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg037.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 37</td>
      <td>465-476</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg038.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 38</td>
      <td>477-490</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg039.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 39</td>
      <td>490-504</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg040.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 40</td>
      <td>504-512</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg041.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 41</td>
      <td>512-516</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg042.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 42</td>
      <td>517-538</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg043.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 43</td>
      <td>539-557</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg044.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 44</td>
      <td>557-572</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg045.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 45</td>
      <td>1-115</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg046.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 46</td>
      <td>116-315</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg047.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 47</td>
      <td>315-330</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg048.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 48</td>
      <td>331-364</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg049.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 49</td>
      <td>365-401</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg050.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 50</td>
      <td>401-416</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg051.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 51</td>
      <td>416-424</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg052.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 52</td>
      <td>425-437</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg053.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 53</td>
      <td>1-33</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg054.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 54</td>
      <td>2-188</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg055.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Orationes 55</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0284.tlg056.perseus-grc2</td>
      <td>Aristides, Aelius</td>
      <td>Ars Rhetorica</td>
      <td>1-2_Arg, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14_1-1_1-29</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0317.tlg001.1st1K-grc1</td>
      <td>Acta Joannis</td>
      <td>Acta Joannis</td>
      <td>1-115</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0317.tlg002.1st1K-grc1</td>
      <td>Acta Joannis</td>
      <td>Acta Joannis (recensio)</td>
      <td>2-111</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0319.tlg004.1st1K-grc1</td>
      <td>Critias</td>
      <td>Fragmenta</td>
      <td>1-75</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0341.tlg002.perseus-grc2</td>
      <td>Lycophron</td>
      <td>Alexandra</td>
      <td>1-1474</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0357.tlg001.1st1K-grc1</td>
      <td>Didymus Alexandrinus</td>
      <td>Mensurae marmorum ac lignorum</td>
      <td>1-43</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0358.tlg001.1st1K-grc1</td>
      <td>Nicomachus of Gerasa</td>
      <td>Introductio arithmetica</td>
      <td>1-2_1-29</td>
      <td>p1_2/p2_1</td>
    </tr>
    <tr>
      <td>tlg0358.tlg002.1st1K-grc1</td>
      <td>Nicomachus of Gerasa</td>
      <td>Harmonicum enchiridion</td>
      <td>toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12</td>
      <td>p1_2/p2_1</td>
    </tr>
    <tr>
      <td>tlg0358.tlg004.1st1K-grc1</td>
      <td>Nicomachus of Gerasa</td>
      <td>Excerpta</td>
      <td>1-10</td>
      <td>p1_2/p2_1</td>
    </tr>
    <tr>
      <td>tlg0358.tlg005.1st1K-grc1</td>
      <td>Nicomachus of Gerasa</td>
      <td>Problemata arithmetica</td>
      <td>1-5</td>
      <td>p1_2/p2_1</td>
    </tr>
    <tr>
      <td>tlg0361.tlg001.1st1K-grc1</td>
      <td>Cleonides</td>
      <td>Introductio Harmonica</td>
      <td>1-14</td>
      <td>m1_1/m1_2</td>
    </tr>
    <tr>
      <td>tlg0362.tlg001.1st1K-grc1</td>
      <td>Carmina Delphis Inventa</td>
      <td>Carmina Delphis Inventa</td>
      <td>pr, 2, 3, 4</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg0363.tlg001.1st1K-grc1</td>
      <td>Claudius Ptolemaeus</td>
      <td>Syntaxis mathematica</td>
      <td>1-13_toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0363.tlg007.1st1K-grc1</td>
      <td>Claudius Ptolemaeus</td>
      <td>Apotelesmatica (= Tetrabiblos)</td>
      <td>1-4_1-10_1-27</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0363.tlg011.1st1K-grc1</td>
      <td>Claudius Ptolemaeus</td>
      <td>Musica</td>
      <td>1-27</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0385.tlg001.perseus-grc2</td>
      <td>Cassius Dio Cocceianus</td>
      <td>Historia Romana</td>
      <td>36-55_18-9_1-4</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0509.tlg001.1st1K-grc1</td>
      <td>Myia</td>
      <td>Epistula ad Phyllidem</td>
      <td>1-4</td>
      <td>m3_1/m3_2/m2_1</td>
    </tr>
    <tr>
      <td>tlg0521.tlg008.1st1K-grc1</td>
      <td>Epicharmus</td>
      <td>Fragmenta</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 50a, 51, 52, 52a, 53, 54, 55, 56, 57, 58, 58a, 59, 60, 61, 62, 63, 64, 65</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0525.tlg001.perseus-grc2</td>
      <td>Pausanias</td>
      <td>Description of Greece</td>
      <td>1-10_1-38_1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0526.tlg001.perseus-grc2</td>
      <td>Flavius Josephus</td>
      <td>Jewish Antiquities</td>
      <td>1-20_arg, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 278, 279, 280, 281, 282, 283, 284, 285, 286, 287, 288, 289, 290, 291, 292, 293, 294, 295, 296, 297, 298, 299, 300, 301, 302, 303, 304, 305, 306, 307, 308, 309, 310, 311, 312, 313, 314, 315, 316, 317, 318, 319, 320, 321, 322, 323, 324, 325, 326, 327, 328, 329, 330, 331, 332, 333, 334, 335, 336, 337, 338, 339, 340, 341, 342, 343, 344, 345, 346, 347, 348, 349, 350, 351, 352, 353, 354, 355, 356, 357, 358, 359, 360, 361, 362, 363, 364, 365, 366, 367, 368, 369, 370, 371, 372, 373, 374, 375, 376, 377, 378, 379, 380, 381, 382, 383, 384, 385, 386, 387, 388, 389, 390, 391, 392, 393, 394, 395, 396, 397, 398, 399, 400, 401, 402, 403, 404, 405, 406, 407, 408, 409, 410, 411, 412, 413, 414, 415, 416, 417, 418, 419, 420, 421, 422, 423, 424, 425, 426, 427, 428, 429, 430, 431, 432, 433, 434, 435, 436, 437, 438, 439, 440, 441, 442, 443, 444, 445, 446, 447, 448, 449, 450, 451, 452, 453, 454, 455, 456, 457, 458, 459, 460, 461, 462, 463, 464, 465, 466, 467, 468, 469, 470, 471, 472, 473, 474, 475, 476, 477, 478, 479, 480, 481, 482, 483, 484, 485, 486, 487, 488, 489, 490, 491</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0526.tlg002.perseus-grc2</td>
      <td>Flavius Josephus</td>
      <td>Life of Josephus</td>
      <td>1-430</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0526.tlg003.perseus-grc2</td>
      <td>Flavius Josephus</td>
      <td>Against Apion</td>
      <td>1-2_1-296</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0526.tlg004.perseus-grc2</td>
      <td>Flavius Josephus</td>
      <td>The Jewish War</td>
      <td>1-7_1-455</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0527.tlg001.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Genesis</td>
      <td>1-50_1-26</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg002.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Exodus</td>
      <td>1-40_1-32</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg003.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Leviticus</td>
      <td>1-27_1-34</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg004.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Numbers</td>
      <td>1-36_1-13</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg005.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Deuteronomium</td>
      <td>1-34_1-12</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg006.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Josue Cod. Vaticanus + Cod. Alexandrinus)</td>
      <td>1-24_1-33b</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg008.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Judices (Cod. Alexandrinus)</td>
      <td>1-21_1-25</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg010.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Ruth</td>
      <td>1-4_1-22</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg011.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Regnorum I (Samuelis I In Textu Masoretico)</td>
      <td>1-31_1-13</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg012.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Regnorum II (Samuelis II In Textu Masoretico)</td>
      <td>1-24_1-25</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg013.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Regnorum III (Regum I In Textu Masoretico)</td>
      <td>1-22_1-54</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg014.opp-grc2</td>
      <td>Septuaginta</td>
      <td>Regnorum IV (Regum II In Textu Masoretico)</td>
      <td>1-25_1-30</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg015.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Paralipomenon I sive Chronicon I</td>
      <td>1-29_1-30</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg016.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Paralipomenon II sive Chronicon II</td>
      <td>1-36_1-23</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg017.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Esdras i (liber apocryphus)</td>
      <td>1-9_1-55</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg018.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Esdras ii (Ezra et Nehemias in textu Masoretico)</td>
      <td>1-23_1-31</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg019.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Esther</td>
      <td>prologue, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10_1-11</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg020.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Judith</td>
      <td>1-16_1-25</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg021.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Tobias (Cod. Vaticanus + Cod. Alexandrinus)</td>
      <td>1-14_1-15</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg023.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Machabaeorum i</td>
      <td>1-16_1-24</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg024.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Machabaeorum ii</td>
      <td>1-15_1-39</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg025.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Machabaeorum iii</td>
      <td>1-7_1-23</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg026.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Machabaeorum iv</td>
      <td>1-18_1-24</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg027.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Psalmi</td>
      <td>1-151_1-7</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg028.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Odae</td>
      <td>1-13_1-79</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg029.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Proverbia</td>
      <td>1-29_1-49</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg031.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Canticum</td>
      <td>1-8_1-14</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg032.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Job</td>
      <td>1-42_1-17e</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg033.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Sapientia Salomonis</td>
      <td>1-20_1-22</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg034.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Ecclesiasticus sive Siracides (Sapientia Jesu filii Sirach)</td>
      <td>1-51_1-30</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg035.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Psalmi Salomonis</td>
      <td>1-18_1-14</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg036.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Osee</td>
      <td>1-14_1-10</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg037.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Amos</td>
      <td>1-9_1-15</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg038.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Michaeas</td>
      <td>1-7_1-20</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg039.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Joel</td>
      <td>1-3_1-21</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg040.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Abdias</td>
      <td>1-1_1-21</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg041.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Jonas</td>
      <td>1-4_1-11</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg042.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Nahum</td>
      <td>1-3_1-19</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg043.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Habacuc</td>
      <td>1-3_1-19</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg044.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Sophonias</td>
      <td>1-3_1-20</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg045.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Aggaeus</td>
      <td>1-2_1-23</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg046.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Zacharias</td>
      <td>1-14_1-21</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg047.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Malachias</td>
      <td>1-4_1-6</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg048.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Isaias</td>
      <td>1-66_1-24</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg049.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Jeremias</td>
      <td>1-52_1-34</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg050.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Baruch</td>
      <td>1-5_1-9</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg051.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Threni seu Lamentationes</td>
      <td>1-5_1-22</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg052.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Epistula Jeremiae</td>
      <td>1-72</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg053.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Ezechiel</td>
      <td>1-48_1-35</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg054.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Susanna (translatio Graeca)</td>
      <td>1-1_1-62b</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg055.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Susanna (Theodotionis versio)</td>
      <td>1-1_1-64</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg056.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Daniel (translatio Graeca)</td>
      <td>1-12_1-13</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg057.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Daniel (Theodotionis versio)</td>
      <td>1-12_1-4</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg058.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Bel et Draco (translatio Graeca)</td>
      <td>1-1_1-42</td>
      <td>m2_1m2_1</td>
    </tr>
    <tr>
      <td>tlg0527.tlg059.1st1K-grc1</td>
      <td>Septuaginta</td>
      <td>Bel et Draco (Theodotionis versio)</td>
      <td>1-1_1-36</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg0529.tlg002.1st1K-grc1</td>
      <td>Arius Didymus</td>
      <td>Liber de philosophorum sectis (epitome ap. Stobaeum)</td>
      <td>1-3_1-43</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0530.tlg005.1st1K-grc1</td>
      <td>Pseudo-Galen</td>
      <td>De fasciis</td>
      <td>1-114</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0530.tlg006.1st1K-grc1</td>
      <td>Pseudo-Galen</td>
      <td>Ad Gaurum quomodo animetur fetus</td>
      <td>1-18</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0530.tlg012.1st1K-grc1</td>
      <td>Pseudo-Galen</td>
      <td>Introductio seu medicus</td>
      <td>1-20</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0530.tlg029.1st1K-grc1</td>
      <td>Pseudo-Galen</td>
      <td>De remediis parabilibus</td>
      <td>1-3_preface, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 278, 279, 280, 281, 282, 283, 284, 285, 286, 287, 288, 289, 290, 291, 292, 293, 294, 295, 296, 297, 298, 299, 300, 301, 302, 303, 304, 305, 306, 307, 308, 309, 310, 311, 312, 313, 314, 315</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0530.tlg032.1st1K-grc1</td>
      <td>Pseudo-Galen</td>
      <td>De theriaca ad Pamphilianum</td>
      <td>1-1</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0530.tlg043.1st1K-grc1</td>
      <td>Pseudo-Galen</td>
      <td>De optima secta ad Thrasybulum</td>
      <td>1-51</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0532.tlg001.perseus-grc2</td>
      <td>Achilles Tatius</td>
      <td>Leucippe and Clitophon</td>
      <td>1-8_1-19_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0533.tlg003.perseus-grc2</td>
      <td>Callimachus</td>
      <td>Epigrams</td>
      <td>1-63_1-6</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg004.perseus-grc2</td>
      <td>Callimachus</td>
      <td>Epigrams and Fragments</td>
      <td>1-64_1-6</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg006.1st1K-grc1</td>
      <td>Callimachus</td>
      <td>Aetia</td>
      <td>0, 1, 2, 3, 4, 5_1-7</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg007.1st1K-grc1</td>
      <td>Callimachus</td>
      <td>Iambi</td>
      <td>1-21_2v, 2r, 3v, 3r, 4v, 4r, 5v, 5r, 6v, 6r, 1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg009.1st1K-grc1</td>
      <td>Callimachus</td>
      <td>Hecala</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35_1-1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg015.perseus-grc3</td>
      <td>Callimachus</td>
      <td>Hymn to Zeus</td>
      <td>1-96</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg016.perseus-grc3</td>
      <td>Callimachus</td>
      <td>Hymn to Apollo</td>
      <td>1-113</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg017.perseus-grc3</td>
      <td>Callimachus</td>
      <td>Hymn to Artemis</td>
      <td>1-268</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg018.perseus-grc3</td>
      <td>Callimachus</td>
      <td>Hymn to Delos</td>
      <td>1-326</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg019.perseus-grc3</td>
      <td>Callimachus</td>
      <td>Hymn to Athena</td>
      <td>1-142</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0533.tlg020.perseus-grc3</td>
      <td>Callimachus</td>
      <td>Hymn to Demeter</td>
      <td>1-138</td>
      <td>m4_1/m4_2/m3_1</td>
    </tr>
    <tr>
      <td>tlg0535.tlg001.perseus-grc2</td>
      <td>Demades</td>
      <td>On the Twelve Years</td>
      <td>1-65</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0537.tlg010.1st1K-grc1</td>
      <td>Epicurus</td>
      <td>Epistula ad Herodotum</td>
      <td>35-83</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0537.tlg011.1st1K-grc1</td>
      <td>Epicurus</td>
      <td>Epistula ad Pythoclem</td>
      <td>84-116</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0537.tlg012.1st1K-grc1</td>
      <td>Epicurus</td>
      <td>Epistula ad Menoeceum</td>
      <td>122-135</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0537.tlg013.1st1K-grc1</td>
      <td>Epicurus</td>
      <td>Ratae Sententiae</td>
      <td>139-154</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0537.tlg014.1st1K-grc1</td>
      <td>Epicurus</td>
      <td>Gnomologium Vaticanum Epicureum</td>
      <td>1-81</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg001.perseus-grc2</td>
      <td>Lysias</td>
      <td>On the Murder of Eratosthenes</td>
      <td>1-50</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0540.tlg002.perseus-grc2</td>
      <td>Lysias</td>
      <td>Funeral Oration</td>
      <td>1-81</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg003.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Simon</td>
      <td>1-48</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg004.perseus-grc2</td>
      <td>Lysias</td>
      <td>On A Wound By Premeditation</td>
      <td>1-20</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg005.perseus-grc2</td>
      <td>Lysias</td>
      <td>For Callias</td>
      <td>1-5</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg006.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Andocides</td>
      <td>1-55</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg007.perseus-grc2</td>
      <td>Lysias</td>
      <td>On the Olive Stump</td>
      <td>1-43</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg008.perseus-grc2</td>
      <td>Lysias</td>
      <td>Accusation of Calumny</td>
      <td>1-20</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg009.perseus-grc2</td>
      <td>Lysias</td>
      <td>For The Soldier</td>
      <td>1-22</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg010.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Theomnestus 1</td>
      <td>1-32</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg011.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Theomnestus 2</td>
      <td>1-12</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg012.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Eratosthenes</td>
      <td>1-100</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0540.tlg013.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Agoratus</td>
      <td>1-97</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg014.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Alcibiades 1</td>
      <td>1-47</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg015.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Alcibiades 2</td>
      <td>1-12</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg016.perseus-grc2</td>
      <td>Lysias</td>
      <td>In Defense of Mantitheus</td>
      <td>1-21</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg017.perseus-grc2</td>
      <td>Lysias</td>
      <td>On The Property Of Eraton</td>
      <td>1-10</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg018.perseus-grc2</td>
      <td>Lysias</td>
      <td>On the Confiscation of the Property Of The Brother Of Nicias</td>
      <td>1-27</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg019.perseus-grc2</td>
      <td>Lysias</td>
      <td>On the Property of Aristophanes</td>
      <td>1-64</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg020.perseus-grc2</td>
      <td>Lysias</td>
      <td>For Polystratus</td>
      <td>1-36</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0540.tlg021.perseus-grc2</td>
      <td>Lysias</td>
      <td>Defense Against A Charge Of Taking Bribes</td>
      <td>1-25</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0540.tlg022.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against The Corn-Dealers</td>
      <td>1-22</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg023.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Pancleon</td>
      <td>1-16</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg024.perseus-grc2</td>
      <td>Lysias</td>
      <td>On The Refusal Of A Pension</td>
      <td>1-27</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0540.tlg025.perseus-grc2</td>
      <td>Lysias</td>
      <td>Defense Against a Charge of Subverting the Democracy</td>
      <td>1-35</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0540.tlg026.perseus-grc2</td>
      <td>Lysias</td>
      <td>On the Scrutiny of Evandros</td>
      <td>1-24</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg027.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Epicrates and his Fellow-envoys</td>
      <td>1-16</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg028.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Ergocles</td>
      <td>1-17</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg029.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Philocrates</td>
      <td>1-14</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg030.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Nicomachus</td>
      <td>1-35</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg031.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Philon</td>
      <td>1-34</td>
      <td>m5_2/m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg032.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against Diogeiton</td>
      <td>1-29</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg033.perseus-grc2</td>
      <td>Lysias</td>
      <td>Olympic Oration</td>
      <td>1-9</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0540.tlg034.perseus-grc2</td>
      <td>Lysias</td>
      <td>Against The Subversion of the Ancestral Constitution</td>
      <td>1-11</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0541.tlg042.1st1K-grc1</td>
      <td>Menander</td>
      <td>Sententiae (corresponds to version Men Ar I) (Greek)</td>
      <td>1-24_1-342</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0542.tlg001.1st1K-grc1</td>
      <td>Julius Pollux</td>
      <td>Onomasticon</td>
      <td>2-2_157-158</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0543.tlg001.perseus-grc2</td>
      <td>Polybius</td>
      <td>Histories</td>
      <td>1-39_1-8_1-8</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg0544.tlg001.1st1K-grc1</td>
      <td>Sextus Empiricus</td>
      <td>Pyrrhoniae Hypotyposes</td>
      <td>1-3_toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 0_toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 278, 279, 280, 281, endnote</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0544.tlg002.1st1K-grc1</td>
      <td>Sextus Empiricus</td>
      <td>Adversus Mathematicos</td>
      <td>1-11_1-257</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0545.tlg001.perseus-grc2</td>
      <td>Aelian</td>
      <td>De Natura Animalium</td>
      <td>1-17_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, epilogos</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0545.tlg002.perseus-grc2</td>
      <td>Aelian</td>
      <td>Varia Historia</td>
      <td>1-14_1-48</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0545.tlg003.perseus-grc2</td>
      <td>Aelian</td>
      <td>Epistulae Rusticae</td>
      <td>1-20</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0545.tlg004.1st1K-grc1</td>
      <td>Aelian</td>
      <td>Fragmenta</td>
      <td>1-353</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0548.tlg001.perseus-grc2</td>
      <td>Apollodorus</td>
      <td>Library</td>
      <td>1-3_1-16_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0548.tlg002.perseus-grc2</td>
      <td>Apollodorus</td>
      <td>Epitome</td>
      <td>1-7_1-40</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0550.tlg001.1st1K-grc1</td>
      <td>Apollonius of Perga</td>
      <td>Conica</td>
      <td>1-57</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg002.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Kings</td>
      <td/>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg003.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Italy</td>
      <td>I, II, III, IV, V, Vb, VI, VII, VIII, IX</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg004.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Samnite History</td>
      <td>I, II, III, IV, V, VI, VII, VIII, IX, X, XI, XII</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg005.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Gallic History</td>
      <td>I, II, III, IV, V, VI, VII, VIII, IX, X, XI, XII, XIII, XIV, XV, XVI, XVII, XVIII, XIX, XX, XXI</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg006.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Sicily and the Other Islands</td>
      <td>I, II, III, IV, V, VI, VII</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg007.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Wars in Spain</td>
      <td>1-16_1-102</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg008.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Hannibalic War</td>
      <td>1-9_1-61</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg009.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Punic Wars</td>
      <td>1-20_1-136</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg010.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Numidian Affairs</td>
      <td>I, II, III, IV, V</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg011.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Macedonian Affairs</td>
      <td>I, II, III, IV, V, VI, VII, VIII, IX, X, XI, XII, XIII, XIV, XV, XVI, XVII, XVIII, XIX</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg012.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Illyrian Wars</td>
      <td>1-5_1-30</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg013.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Syrian Wars</td>
      <td>1-11_1-70</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg014.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Mithridatic Wars</td>
      <td>1-17_1-121</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0551.tlg017.perseus-grc2</td>
      <td>Appianus of Alexandria</td>
      <td>Civil Wars</td>
      <td>1-5_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21_1-145</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0552.tlg001.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>De sphaera et cylindro</td>
      <td>1-2_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg0552.tlg002.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Dimensio circuli</td>
      <td>1-3</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg0552.tlg003.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>De conoidibus et sphaeroidibus</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 30, 31, 32</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg004.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>De lineis spiralibus</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg0552.tlg005.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>De planorum aequilibriis</td>
      <td>1-2_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg006.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Arenarius</td>
      <td>1-4</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg007.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Quadratura parabolae</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg008.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>De corporibus fluitantibus</td>
      <td>1-2_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg009.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Stomachion</td>
      <td>1-1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg010.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Ad Eratosthenem methodus</td>
      <td>pr1, pr2, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg011.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Liber assumptorum</td>
      <td>1-15</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg012.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Problema bovinum</td>
      <td>1-2</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0552.tlg013.1st1K-grc1</td>
      <td>Archimedes</td>
      <td>Fragmenta</td>
      <td>1-2_1-1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0553.tlg001.1st1K-grc1</td>
      <td>Artemidorus</td>
      <td>Ονειροκριτικά</td>
      <td>1-5_prooimion, 1, 2, 3, 4, 5, 6, 7, 9, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 8, 10, 28, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0554.tlg001.perseus-grc1</td>
      <td>Chariton of Aphrodisias</td>
      <td>De Chaerea et Callirhoe</td>
      <td>1-8_1-8_1-16</td>
      <td>p1_2/p2_1</td>
    </tr>
    <tr>
      <td>tlg0555.tlg001.1st1K-grc1</td>
      <td>Clement of Alexandria</td>
      <td>Protrepticus</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0555.tlg002.1st1K-grc1</td>
      <td>Clement of Alexandria</td>
      <td>Paedagogus</td>
      <td>1-3_argument, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0555.tlg004.1st1K-grc1</td>
      <td>Clement of Alexandria</td>
      <td>Stromateis</td>
      <td>7-8_1-9</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0555.tlg005.1st1K-grc1</td>
      <td>Clement of Alexandria</td>
      <td>Eclogae propheticae</td>
      <td>1-65</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0555.tlg006.1st1K-grc1</td>
      <td>Clement of Alexandria</td>
      <td>Quis dives salvetur</td>
      <td>1-42</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0555.tlg007.1st1K-grc1</td>
      <td>Clement of Alexandria</td>
      <td>Excerpta ex Theodoto</td>
      <td>1-86</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0555.tlg008.perseus-grc2</td>
      <td>Clement of Alexandria</td>
      <td>Exhortation to Endurance or To the Newly Baptized (Fragment 44)</td>
      <td>1-6</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0556.tlg001.perseus-grc2</td>
      <td>Asclepiodotus</td>
      <td>Tactica</td>
      <td>argument, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12_chap, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22_heads</td>
      <td>m1_1/m1_2</td>
    </tr>
    <tr>
      <td>tlg0557.tlg001.perseus-grc2</td>
      <td>Epictetus</td>
      <td>Discourses</td>
      <td>0, 1, 2, 3, 4_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30_1-24</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0557.tlg002.perseus-grc2</td>
      <td>Epictetus</td>
      <td>The Handbook</td>
      <td>1-53_1-4</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0557.tlg003.perseus-grc2</td>
      <td>Epictetus</td>
      <td>Fragments</td>
      <td>1-36</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0557.tlg004.1st1K-grc1</td>
      <td>Epictetus</td>
      <td>Gnomologium Epicteteum (e Stobaei libris 1-2)</td>
      <td>1-8</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0557.tlg005.1st1K-grc1</td>
      <td>Epictetus</td>
      <td>Gnomologium Epicteteum (e Stobaei libris 3‑4)</td>
      <td>1-67</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg001.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Pneumatica</td>
      <td>1-2_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg002.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>De automatis</td>
      <td>1-2_1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg004.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Mechanicorum fragmenta</td>
      <td>1-3_1-2</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg005.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Catoptrica</td>
      <td>1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg006.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Metrica</td>
      <td>1-3_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 17, 18, 19, 20, 21, 23, 24, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 16, 22</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg007.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Dioptra</td>
      <td>1-38</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg010.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Stereometrica</td>
      <td>1-2_1-69_1-5</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg011.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>De mensuris</td>
      <td>1-61_1-13</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg012.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Belopoeica</td>
      <td>71-119</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg014.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Fragmenta Heroniana</td>
      <td>4-18_1-27</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg015.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Geodaesia [Sp.]</td>
      <td>1-12_1-2</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0559.tlg016.1st1K-grc1</td>
      <td>Hero of Alexandria</td>
      <td>Liber geeponicus [Sp.]</td>
      <td>1-205</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0560.tlg001.perseus-grc2</td>
      <td>Longinus</td>
      <td>On the Sublime</td>
      <td>1-44_1-12</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0561.tlg001.perseus-grc2</td>
      <td>Longus</td>
      <td>Daphnis and Chloe</td>
      <td>1-4_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40_1-3</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg0562.tlg001.perseus-grc2</td>
      <td>Marcus Aurelius</td>
      <td>Ad Se Ipsum</td>
      <td>1-12_1-36_1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0563.tlg001.1st1K-grc1</td>
      <td>Maximus of Tyre</td>
      <td>Dialexeis</td>
      <td>1-41_1-5_a, b, c, d, e, f, g, h, i, k, l, m, 1, 10, 100, n, o, p, q, j</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0564.tlg001.1st1K-grc1</td>
      <td>Rufus of Ephesus</td>
      <td>De renum et vesicae affectionibus</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15_1-12</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0565.tlg001.1st1K-grc1</td>
      <td>Soranus</td>
      <td>Gynaeciorum Libri IV</td>
      <td>1-4_pref, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0565.tlg002.1st1K-grc1</td>
      <td>Soranus</td>
      <td>De signis Fracturarum</td>
      <td>1-24</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0565.tlg003.1st1K-grc1</td>
      <td>Soranus</td>
      <td>De Fasciis</td>
      <td>1-60</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0565.tlg004.1st1K-grc1</td>
      <td>Soranus</td>
      <td>Vita Hippocratis</td>
      <td>1-1</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg0572.tlg001.1st1K-grc1</td>
      <td>Gaius Romanus</td>
      <td>Fragmenta</td>
      <td>1-2_1-3</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0575.tlg001.1st1K-grc1</td>
      <td>Moschion Gnomologus</td>
      <td>Sententiae</td>
      <td>1-25</td>
      <td>p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg0575.tlg002.1st1K-grc1</td>
      <td>Moschion Gnomologus</td>
      <td>Hypothecae</td>
      <td>1-18</td>
      <td>p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg0579.tlg010.1st1K-grc1</td>
      <td>Orphica</td>
      <td>Fragmenta</td>
      <td>1-22</td>
      <td>m6_1/m6_2/m5_1</td>
    </tr>
    <tr>
      <td>tlg0580.tlg001.1st1K-grc1</td>
      <td>Paradoxographus Florentinus</td>
      <td>Mirabilia de aquis</td>
      <td>1-43</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg0591.1st1K001.1st1K-grc1</td>
      <td>Antisthenes</td>
      <td>Ajax</td>
      <td>1-9</td>
      <td>m5_2/m4_1</td>
    </tr>
    <tr>
      <td>tlg0591.1st1K002.1st1K-grc1</td>
      <td>Antisthenes</td>
      <td>Odysseus</td>
      <td>1-14</td>
      <td>m5_2/m4_1</td>
    </tr>
    <tr>
      <td>tlg0592.tlg001.1st1K-grc1</td>
      <td>Hermogenes</td>
      <td>Progymnasmata [Dub.]</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0592.tlg002.1st1K-grc1</td>
      <td>Hermogenes</td>
      <td>Περὶ στάσεων</td>
      <td>1-12_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0592.tlg003.1st1K-grc1</td>
      <td>Hermogenes</td>
      <td>Περὶ εὑρέσεως [Sp.]</td>
      <td>1-4_1-14</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0592.tlg004.1st1K-grc1</td>
      <td>Hermogenes</td>
      <td>Περὶ ἰδεῶν λόγου</td>
      <td>1-2_1-12_1-11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0592.tlg005.1st1K-grc1</td>
      <td>Hermogenes</td>
      <td>Περὶ μεθόδου δεινότητος [Sp.]</td>
      <td>1-37</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0593.1st1K001.1st1K-grc1</td>
      <td>Gorgias of Leontini</td>
      <td>Encomium of Helen</td>
      <td>1-21</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0593.1st1K002.1st1K-grc1</td>
      <td>Gorgias of Leontini</td>
      <td>Defense of Palamedes</td>
      <td>1-37</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0606.tlg001.1st1K-grc1</td>
      <td>Rufus Soph.</td>
      <td>Ars rhetorica</td>
      <td>pr, 1, 2, 3, 4_1-41</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0607.tlg001.1st1K-grc1</td>
      <td>Aelius Theon</td>
      <td>Προγυμνάσματα</td>
      <td>1-5</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0609.tlg001.1st1K-grc1</td>
      <td>Tryphon I Grammaticus</td>
      <td>De tropis</td>
      <td>p, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg0610.perseus002.perseus-grc1</td>
      <td>Alcidamas</td>
      <td>Peri Sophiston</td>
      <td>1-35</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0610.tlg001.1st1K-grc1</td>
      <td>Alcidamas</td>
      <td>Odysseus</td>
      <td>1-2_1-34</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0612.tlg001.perseus-grc2</td>
      <td>Dio Chrysostom</td>
      <td>Orationes</td>
      <td>1-30_1-46</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0613.tlg001.perseus-grc2</td>
      <td>Demetrius of Phaleron</td>
      <td>Libro de Elocutione</td>
      <td>1-5_1-304</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0614.tlg001.1st1K-grc1</td>
      <td>Babrius</td>
      <td>Fabulae Aesopeae</td>
      <td>1-1_2-2_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0615.tlg001.1st1K-grc1</td>
      <td>Aspasius</td>
      <td>In Ethica Nichomachea Commentaria</td>
      <td>1-6</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0616.tlg001.1st1K-grc1</td>
      <td>Polyaenus Macedo</td>
      <td>Strategemata</td>
      <td>1-8_pref, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 51, 50, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0616.tlg002.1st1K-grc1</td>
      <td>Polyaenus Macedo</td>
      <td>Excerpta Polyaeni</td>
      <td>toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0618.tlg001.1st1K-grc1</td>
      <td>Antigoni Epistula</td>
      <td>Epistula</td>
      <td>1-1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0620.tlg002.1st1K-grc1</td>
      <td>Archytas of Tarentum</td>
      <td>Fragmenta</td>
      <td>1-9</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0623.tlg001.1st1K-grc1</td>
      <td>Cratetis Epistulae</td>
      <td>Epistulae</td>
      <td>1-36_1-1</td>
      <td>m1_1/m1_2</td>
    </tr>
    <tr>
      <td>tlg0626.tlg002.1st1K-grc1</td>
      <td>Heraclitus of Ephesus</td>
      <td>Fragmenta</td>
      <td>1-139</td>
      <td>m6_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg001.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De prisca medicina</td>
      <td>1-24</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg002.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De aere, aquis, locis</td>
      <td>1-24</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg003.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Prognosticon</td>
      <td>1-25</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg004.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De diaeta in morbis acutis</td>
      <td>1-18</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg005.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De diaeta acutorum (spurium)</td>
      <td>1-39</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg006.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Epidemiarum</td>
      <td>1-6_13-8_1-32</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg007.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De capitis vulneribus</td>
      <td>1-21</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg008.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De officina medici</td>
      <td>1-25</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg009.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De fracturis</td>
      <td>1-48</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg010.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De articulis</td>
      <td>1-87</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg011.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Vectiarius</td>
      <td>1-42</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg012.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Aphorismi</td>
      <td>1-7_1-87</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg013.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Iusiurandum</td>
      <td>1-1</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg014.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Lex</td>
      <td>1-5</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg015.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De humoribus</td>
      <td>1-20</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg016.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Prorrheticon I</td>
      <td>1-2_1-43</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg017.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Coa praesagia</td>
      <td>1-35</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg018.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De arte</td>
      <td>1-13</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg019.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De natura hominis</td>
      <td>1-15</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg020.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De salubri diaeta</td>
      <td>1-9</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg021.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De flatibus</td>
      <td>1-15</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg022.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De liquidorum usu</td>
      <td>1-7</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg023.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De morbis i-iii</td>
      <td>1-4</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg024a.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De genitura</td>
      <td>1-11</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg024b.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De natura pueri</td>
      <td>12-31</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg025.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De affectionibus</td>
      <td>1-61</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg026.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De locis in homine</td>
      <td>1-47</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg027.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De morbo sacro</td>
      <td>1-18</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg028.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De ulceribus</td>
      <td>1-27</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg029.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De haemorrhoidibus</td>
      <td>1-9</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg030.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De fistulis</td>
      <td>1-10</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg031.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De diaeta</td>
      <td>1-4_1-93</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg032.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De affectionibus interioribus</td>
      <td>1-54</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg033.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De natura muliebri</td>
      <td>1-109</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg035.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De octimestri partu</td>
      <td>10-13</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg036.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De muliebribus</td>
      <td>1-3_1-249</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg037.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De virginum morbis</td>
      <td>1-1</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg038.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De superfoetatione</td>
      <td>1-43</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg039.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De exsectione foetus</td>
      <td>1-5</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg040.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De anatomia</td>
      <td>1-1</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg041.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De dentitione</td>
      <td>1-32</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg042.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De glandulis</td>
      <td>1-17</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg043.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De carnibus</td>
      <td>1-19</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg045.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De corde</td>
      <td>1-12</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg0627.tlg046.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De alimento</td>
      <td>1-55</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg047.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De visu</td>
      <td>1-9</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg048.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De natura ossium</td>
      <td>1-19</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg049.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De medico</td>
      <td>1-14</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg050.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De habitu decenti</td>
      <td>1-18</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg051.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Praeceptiones</td>
      <td>1-14</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg052.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De crisibus</td>
      <td>1-64</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg053.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>De diebus criticis</td>
      <td>1-11</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0627.tlg055.1st1K-grc1</td>
      <td>Hippocrates</td>
      <td>Epistulae, Decretum, Orationes</td>
      <td>1-27</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0628.tlg001.1st1K-grc1</td>
      <td>Musonius Rufus</td>
      <td>Dissertationum a Lucio digestarum reliquiae</td>
      <td>1-21</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0628.tlg002.1st1K-grc1</td>
      <td>Musonius Rufus</td>
      <td>Fragmenta minora</td>
      <td>22-53</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0628.tlg003.1st1K-grc1</td>
      <td>Musonius Rufus</td>
      <td>Epistulae spuriae</td>
      <td>1-5_1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0629.tlg001.1st1K-grc1</td>
      <td>Periander</td>
      <td>Epistulae</td>
      <td>1-2</td>
      <td>m7_2</td>
    </tr>
    <tr>
      <td>tlg0632.tlg002.1st1K-grc1</td>
      <td>Pythagoras</td>
      <td>Epistulae</td>
      <td>1-2</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg0633.tlg001.1st1K-grc1</td>
      <td>Lysis</td>
      <td>Epistula ad Hipparchum</td>
      <td>1-6</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0634.tlg001.1st1K-grc1</td>
      <td>Xenocrates of Chalcedon</td>
      <td>Fragmenta</td>
      <td>1-78</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg0636.tlg001.1st1K-grc1</td>
      <td>Socrates Epistulae</td>
      <td>Epistulae</td>
      <td>1-7b_1-1</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0637.tlg001.1st1K-grc1</td>
      <td>Socraticorum Epistulae</td>
      <td>Epistulae</td>
      <td>8-37_1-1</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg0638.tlg001.perseus-grc2</td>
      <td>Philostratus the Athenian</td>
      <td>Life of Apollonius of Tyana</td>
      <td>1-8_1-31</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0638.tlg003.perseus-grc2</td>
      <td>Philostratus the Athenian</td>
      <td>Lives of the Sophists</td>
      <td>praef, 1, 2_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0638.tlg004.perseus-grc2</td>
      <td>Philostratus the Athenian</td>
      <td>Heroicus</td>
      <td>660-753</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0638.tlg005.perseus-grc2</td>
      <td>Philostratus the Athenian</td>
      <td>Nero</td>
      <td>work</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0638.tlg006.perseus-grc2</td>
      <td>Philostratus the Athenian</td>
      <td>Epistulae et dialexeis</td>
      <td>1-2_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0639.tlg001.1st1K-grc1</td>
      <td>Menecrates Medicus</td>
      <td>Epistula</td>
      <td>1-1</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg0640.tlg001.1st1K-grc1</td>
      <td>Alciphron</td>
      <td>Epistulae</td>
      <td>1-4_1-19</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0641.tlg001.perseus-grc2</td>
      <td>Xenophon of Ephesus</td>
      <td>Ephesiaca</td>
      <td>1-5_1-15_1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0643.opp003.1st1K-grc1</td>
      <td>Anonymus Londinensis</td>
      <td>Iatrica Fragmenta Reliqua</td>
      <td>1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0643.tlg001.1st1K-grc1</td>
      <td>Anonymus Londinensis</td>
      <td>Iatrica</td>
      <td>1-39_1-32</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0643.tlg002.1st1K-grc1</td>
      <td>Anonymus Londinensis</td>
      <td>Anonymus Londinensis Fragmenta</td>
      <td>1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0644.tlg001.1st1K-grc1</td>
      <td>Aristophanes of Byzantium</td>
      <td>Historiae Animalium Epitome</td>
      <td>1-2_1-625</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg0645.tlg001.1st1K-grc1</td>
      <td>Justin Martyr</td>
      <td>Apologia I</td>
      <td>1-68</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0645.tlg002.perseus-grc2</td>
      <td>Justin Martyr</td>
      <td>Apologia secunda</td>
      <td>1-15</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0645.tlg003.perseus-grc2</td>
      <td>Justin Martyr</td>
      <td>Dialogue with Trypho</td>
      <td>1-142_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0646.tlg004.1st1K-grc1</td>
      <td>Pseudo-Justinus Martyr</td>
      <td>Epistula ad Diognetum</td>
      <td>1-12_1-9</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0647.tlg001.perseus-grc2</td>
      <td>Tryphiodorus</td>
      <td>The Taking of Ilios</td>
      <td>1-691</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg0648.tlg001.perseus-grc2</td>
      <td>Onasander</td>
      <td>Strategicus</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42_1-26</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0649.tlg002.1st1K-grc1</td>
      <td>Lesbonax (Rhetorician)</td>
      <td>Protrepticus A</td>
      <td>1-20</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0649.tlg003.1st1K-grc1</td>
      <td>Lesbonax (Rhetorician)</td>
      <td>Protrepticus B</td>
      <td>1-14</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0652.tlg001.perseus-grc2</td>
      <td>Philostratus Minor</td>
      <td>Imagines</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0653.tlg001.perseus-grc2</td>
      <td>Aratus Solensis</td>
      <td>Phaenomena</td>
      <td>1-1154</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg0655.tlg001.perseus-grc2</td>
      <td>Parthenius of Nicaea</td>
      <td>Narrationes Amatoriae</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36_contents, dedication, 1, 2, 3, 4, 5, 6, 7, 8</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0656.tlg001.1st1K-grc1</td>
      <td>Dioscurides Pedianus</td>
      <td>De materia medica</td>
      <td>1-5_preface, 1, 2, 4, 7, 8, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 25, 26, 28, 30, 32, 33, 39, 40, 42, 43, 45, 47, 48, 52, 54, 55, 56, 58, 59, 61, 64, 66, 9, 24, 49, 70, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 85, 86, 101, 102, 104, 105, 3, 5, 6, 21, 22, 23, 27, 31, 34, 35, 36, 38, 44, 46, 51, 53, 60, 62, 63, 67, 68, 73a, 84, 88, 89, 98, 109, 111, 112, 113, 121, 126, 128, 132, 134, 136, 137, 140, 143, 146, 150, 152, 154, 156, 158, 41, 65, 69, 93, 96, 103, 87, 94, 95, 97, 99, 106, 107, 108, 114, 115, 118, 120, 123, 124, 125, 127, 153, 155, 159, 160, 162_1-2</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0656.tlg002.1st1K-grc1</td>
      <td>Dioscurides Pedianus</td>
      <td>Euporista vel De simplicibus medicinis</td>
      <td>1-2_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, arg_1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0657.tlg001.1st1K-grc1</td>
      <td>Crateuas</td>
      <td>Fragmenta</td>
      <td>1-1_1-10</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg0658.tlg001.perseus-grc1</td>
      <td>Heliodorus of Emesa</td>
      <td>Aethiopica</td>
      <td>1-10_1-41</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg0666.tlg001.1st1K-grc1</td>
      <td>Adrianus of Tyre</td>
      <td>Declamatio</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0671.tlg001.1st1K-grc1</td>
      <td>Philumenus</td>
      <td>De venenatis animalibus eorumque remediis</td>
      <td>1-37_1-4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0676.tlg001.1st1K-grc1</td>
      <td>Aglaias, Byzantius</td>
      <td>Adversus suffusiones incipientes</td>
      <td>1-28</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0693.tlg001.1st1K-grc1</td>
      <td>Albinus</td>
      <td>Epitome doctrinae Platonicae sive Διδασκαλικός</td>
      <td>1-36</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0693.tlg002.1st1K-grc1</td>
      <td>Albinus</td>
      <td>Introductio in Platonem</td>
      <td>1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0708.tlg001.1st1K-grc1</td>
      <td>Ammonius Grammaticus</td>
      <td>περὶ ὁμοίων καὶ διαφόρων λέξεων</td>
      <td>1-24_1-525</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg0719.tlg001.perseus-grc2</td>
      <td>Aretaeus of Cappadocia</td>
      <td>De causis et signis acutorum morborum libri duo</td>
      <td>1-2_5-12</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0719.tlg002.perseus-grc2</td>
      <td>Aretaeus of Cappadocia</td>
      <td>De causis et signis diuturnorum morborum libri duo</td>
      <td>1-2_1-13</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg0719.tlg003.perseus-grc2</td>
      <td>Aretaeus of Cappadocia</td>
      <td>De curatione acutorum morborum libri duo</td>
      <td>1-2_1-11</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0719.tlg004.perseus-grc2</td>
      <td>Aretaeus of Cappadocia</td>
      <td>De curatione diuturnorum morborum libri duo</td>
      <td>1-2_1-7</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg0731.tlg001.1st1K-grc1</td>
      <td>Adamantius Judaeus</td>
      <td>Physiognomonica</td>
      <td>1-2_1-61</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg0731.tlg003.1st1K-grc1</td>
      <td>Adamantius Judaeus</td>
      <td>Physiognomonica (epitome Matritensis)</td>
      <td>1-2_1-44</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg001.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>De mixtione</td>
      <td>1-16</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg003.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>De febribus [Sp.]</td>
      <td>1-31_1-5</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg004.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>In Aristotelis Metaphysica Commentaria</td>
      <td>1-14</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg005.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>In Aristotelis Analyticorum Priorum Librum I Commentarium</td>
      <td>introduction, 24a10, 24a11, 24a16, 24a22, 24b12, 24b16, 24b18, 24b22, 24b26, 25a1, 25a2, 24a4, 25a5, 25a14, 25a27, 25a29, 25a32, 25a37, 25b14, 25b25, 25b32, 25b37, 25b40, 26a2, 26a9, 26a13, 26a14, 26a17, 26a20, 26a21, 26a23, 26a30, 26a33, 26a36, 26a39, 26b21a, 26b26a, 26b28a, 26b30a, 26b21b, 26b26b, 26b28b, 26b30b, 26b34, 26b36, 26b37, 27a1, 27a3, 27a5, 27a9, 27a14, 27a15, 27a18, 27a26, 27a32, 27a36, 27b1, 27b4, 27b6, 27b9, 27b14, 27b28, 27b36, 28a6, 28a10, 28a12, 28a13, 28a16, 28a18, 28a26, 28a30, 28a33, 28a36, 28b5, 28b12, 28b15, 28b22, 28b31, 28b36, 28b38, 29a2, 29a6, 29a11, 29a13, 29a19, 29a27, 29a30, 29b1, 29b19, 29b26, 29b27, 29b28, 29b29, 29b30, 29b33, 30a2, 30a9, 30a15, 30a17, 30a23, 30a27, 30a28, 30a32, 30a33, 30b7, 30b9, 30b14, 30b17, 30b18, 30b24, 30b31, 31a1, 31a5, 31a10, 31a18, 31a34, 31b33, 32a6, 32a8, 32a9, 32a12, 32a15, 32a16, 32a18, 32a21, 32a28, 32a29, 32a36, 32b4, 32b8, 32b23, 32b25, 32b29, 32b32, 32b38, 35a5, 33a21, 33b3, 33b8, 33b25, 33b33, 34a2, 34a5, 34a7, 34a10, 34a12, 34a16, 34a25, 34a34, 34b2, 34b7, 34b17, 34b19, 34b27, 34b39, 35a3, 35a20, 35a25, 35b8, 35b11, 35b20, 35b23, 36a2, 30a7, 36a17, 36a25, 36b15, 36b19, 36b24, 36b26, 36b33, 36b35, 36b38, 37a9, 37a17, 37a20, 37a26, 37a32, 37a38, 37b19, 37b29, 38a13, 38a16, 38a25, 38b3, 38b24, 38b31, 38b38, 39a4, 39a14, 39a28, 39b7, 40a4, 40b15, 40b17, 40b20, 40b23, 40b30, 41a26, 41a37, 41b6, 41b14, 41b23, 41b27, 41b31, 41b32, 41b33, 41b36, 41b38, 42a1, 42a4, 42a6, 42a8, 42a24, 42a35, 42a37, 42b1, 42b5, 42b24, 42b27, 43a8, 43a14, 43a16, 43a20, 43a33, 43b1, 43b11, 43b22, 43b29, 43b32, 43b36, 43b39, 43b43, 44a2, 44a9, 44a12, 44a28, 44a30, 44a38, 44b3a, 44b3b, 44b6, 44b19, 44b25, 44b38, 45a4, 45a9, 45a17, 45a20, 45a23, 45a28, 45b1, 45b8, 45b12, 45b15, 45b19, 45b22, 45b25, 45b28, 45b31, 45b35, 45b36, 46a3, 46a10, 46a16, 46a31, 46a34, 46a39, 46b22, 46b24, 46b26, 46b28, 46b38, 46b40, 47a10, 47a13, 47a22a, 47a22b, 47a28, 47a40, 47b9, 47b15, 47b40, 48a15, 48a18, 48a29, 48a31, 48a40, 48b2, 48b10, 48b13, 48b27, 48b33, 49a6, 49a11, 49a27, 49b1, 49b3, 49b10, 49b14, 49b20, 49b22, 49b25, 49b27, 49b30, 49b32, 49b37, 50a1, 50a5, 50a8, 50a11, 50a16, 50a32, 50a37, 50a39, 50b5, 50b21, 50b30, 50b33, 51a1, 51a18, 51a22, 51a26, 51a34, 51b5, 51b25, 51b28, 51b32, 51b36, 51b39, 52a12, 52a15, 52a18, 52a24, 52a34, 52a37, 52a39, 52b4, 52b12, 52b14</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg006.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>In Aristotelis Topicorum Libros Octo Commentaria</td>
      <td>1-8</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg007.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>In Librum De Sensu Commentarium</td>
      <td>1-2</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg008.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>In Aristotelis Meteorologicorum Libros Commentaria</td>
      <td>1-4</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg010.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>De anima</td>
      <td>1-1_1-31</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg011.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>De anima libri mantissa</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24_1-112</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg012.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>Quaestiones</td>
      <td>1-3_1-15_1-1</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg013.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>Ἠθικὰ προβλήματα [Sp.]</td>
      <td>TOC, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlg014.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>De fato</td>
      <td>1-39</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0732.tlgX01.1st1K-grc1</td>
      <td>Alexander of Aphrodisias</td>
      <td>In Aristotelis Sophisticos Elenchos Commentarius [Sp.]</td>
      <td>introduction, 165a1, 165a17, 165a19, 165a24a, 165a24b, 165a34, 165a38, 165b12, 165b23, 165b27, 165b30, 165b38, 166a6, 166a14, 166a23, 166a33, 166b1, 166b10, 166b21, 166b28, 166b37, 167a21, 167a36, 167b1, 167b21, 167b38, 168a23, 168a34, 168b11, 168b27, 169a6, 169a18, 169a22, 169a33, 169b3, 169b18, 169b30, 169b37, 170a5, 170a8, 170a12, 170a20, 170a30, 170a34, 170b12, 170b20, 170b35, 171a1, 171a12, 171a17, 171a18, 171a28, 171a34, 171b3, 171b6, 171b7, 171b18, 171b34, 172a9, 172a18, 172a21, 172a23, 172a27, 172a36, 172b5, 172b9, 172b22, 172b29, 172b36, 173a7, 173a19, 173a32, 173b1, 173b12, 173b17, 173b26, 173b36, 174a5, 174a12, 174a18, 174a23, 174a33, 174a40, 174b8, 174b12, 174b19, 174b23, 174b28, 174b33, 174b38, 175a2, 175a17, 175a20, 175a26, 175a31, 175a40, 175b8, 175b15, 175b21, 175b28, 175b39, 176a3, 176a13, 176a27, 176a33, 176a38, 176b8, 176b11, 176b14, 176b20, 176b29, 177a6, 177a9, 177a16, 177a18, 117a20, 177a33, 177b12, 177b20, 177b22, 177b36, 178a4, 178a29, 178a37, 178b8, 178b18, 178b24, 178b33, 178b36, 179a14, 179a26, 179b11, 179b24, 179b38, 180a10, 180a18, 180a23, 180a32, 180b2, 180b17, 180b34, 181a1, 181a15, 181a22, 181a31, 181a36, 181b6, 181b16, 181b25, 181b35, 182a7, 182a13, 182a21, 182a37, 182b6, 182b13, 182b17, 182b32, 182b33, 182b37, 183a3, 183a7, 183a37, 183b34, 184a2</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg0733.tlg001.1st1K-grc1</td>
      <td>Cassius Iatrosophista</td>
      <td>Quaestiones medicae et problemata physica</td>
      <td>1-84</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg0751.tlg005.1st1K-grc1</td>
      <td>Pseudo-Hippocrates</td>
      <td>Ἑρμηνεία περὶ ἐνεργῶν λίθων</td>
      <td>1-41</td>
      <td>m5_1/m5_2/m4_1</td>
    </tr>
    <tr>
      <td>tlg0751.tlg034.1st1K-grc1</td>
      <td>Pseudo-Hippocrates</td>
      <td>De septimestri partu</td>
      <td>1-9</td>
      <td>m5_1/m5_2/m4_1</td>
    </tr>
    <tr>
      <td>tlg1118.tlg003.1st1K-grc1</td>
      <td>Pseudo-Dioscorides</td>
      <td>De lapidibus</td>
      <td>1-1_1-37</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg1126.tlg003.1st1K-grc1</td>
      <td>Anubion, Poeta Astrologus</td>
      <td>Fragmenta</td>
      <td>1-1</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1129.tlg001.1st1K-grc1</td>
      <td>Anonymi de Barbarismo et Soloecismo</td>
      <td>De barbarismo et soloecismo</td>
      <td>1-4</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg1131.tlg001.1st1K-grc1</td>
      <td>Anonymus Ad Avircium Marcellum contra Cataphrygas</td>
      <td>Ad Avircium Marcellum contra Cataphrygas</td>
      <td>1-3_1-3</td>
      <td>p3_1/p3_2/p4_1/p4_2/p5_1/p5_2/p6_1</td>
    </tr>
    <tr>
      <td>tlg1134.tlg001.1st1K-grc1</td>
      <td>Anonymous Iamblichi</td>
      <td>Fragmenta</td>
      <td>1-7_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16</td>
      <td>m5_2/m4_1</td>
    </tr>
    <tr>
      <td>tlg1146.tlg001.1st1K-grc1</td>
      <td>Antipater Tarsensis</td>
      <td>Testimonia et Fragmenta</td>
      <td>1-67</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg1147.tlg003.1st1K-grc1</td>
      <td>Antiphon of Athens</td>
      <td>Fragmenta</td>
      <td>1-118</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg1181.tlg001.1st1K-grc1</td>
      <td>Aristarchus of Samos</td>
      <td>De magnitudinibus et distantiis solis et lunae</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1188.tlg002.1st1K-grc1</td>
      <td>Aristocles of Messene</td>
      <td>Fragmenta</td>
      <td>1-7</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1193.tlg001.1st1K-grc1</td>
      <td>Ariston of Chios</td>
      <td>Testimonia et Fragmenta</td>
      <td>333-403</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1194.tlg001.1st1K-grc1</td>
      <td>Aristonicus of Alexandria</td>
      <td>De signis Odysseae</td>
      <td>1-24_2-425</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg1205.tlg001.perseus-grc1</td>
      <td>Athenagoras</td>
      <td>Legatio sive Supplicatio pro Christianis</td>
      <td>opener, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1205.tlg002.perseus-grc1</td>
      <td>Athenagoras</td>
      <td>De Resurrectione</td>
      <td>1-25</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1210.tlg001.1st1K-grc1</td>
      <td>Autolycus</td>
      <td>De Sphaera Quae Movetur</td>
      <td>definitiones, propositiones_1-11</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg1210.tlg002.1st1K-grc1</td>
      <td>Autolycus</td>
      <td>De Ortibus et Occasibus</td>
      <td>1-2_definitiones, propositiones_1-18</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg1216.tlg001.opp-grc1</td>
      <td>Barnabae epistula</td>
      <td>Barnabae epistula</td>
      <td>1-21_1-9</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1220.tlg001.1st1K-grc1</td>
      <td>Batrachomyomachia</td>
      <td>Batrachomyomachia</td>
      <td>1-303</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg1247.tlg001.1st1K-grc1</td>
      <td>Cebes</td>
      <td>Cebetis tabula</td>
      <td>1-41_1-4</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1252.tlg002.1st1K-grc1</td>
      <td>Certamen Homeri et Hesiodi</td>
      <td>Certamen Homeri et Hesiodi</td>
      <td>1-1</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1264.tlg001.1st1K-grc1</td>
      <td>Chrysippus</td>
      <td>Fragmenta Logica et Physica</td>
      <td>1-1216</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1264.tlg002.1st1K-grc1</td>
      <td>Chrysippus</td>
      <td>Fragmenta Moralia</td>
      <td>1-768</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1264.tlg003.1st1K-grc1</td>
      <td>Chrysippus</td>
      <td>Fragmenta quae ad explicationem carminum Homericorum pertinent</td>
      <td>769-777</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1264.tlg004.1st1K-grc1</td>
      <td>Chrysippus</td>
      <td>Fragmenta ad singulos libros relata</td>
      <td>1-66</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1269.tlg002.1st1K-grc1</td>
      <td>Cleanthes</td>
      <td>Testimonia et Fragmenta</td>
      <td>463-619</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1271.tlg001.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Epistula I ad Corinthios</td>
      <td>preface, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65_1-2</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg002.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Epistula II ad Corinthios</td>
      <td>1-20_1-5</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg003.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Epistula Petri ad Jacobum [Sp.]</td>
      <td>1-3</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg004.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Contestatio [Sp.]</td>
      <td>1-5</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg005.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Epistula Clementis ad Jacobum [Sp.]</td>
      <td>1-20</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg006.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Homiliae [Sp.]</td>
      <td>1-19_1-14</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg010.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Epistulae de virginitate [Sp.]</td>
      <td>1-2_2-13_1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg011.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Pseudo‑Clementina (epitome altera auctore Symeone Metaphrasta) [Sp.]</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1271.tlg012.1st1K-grc1</td>
      <td>Clemens Romanus (Clement of Rome)</td>
      <td>Pseudo‑Clementina (epitome de gestis Petri praemetaphrastica) [Sp.]</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1272.tlg001.1st1K-grc1</td>
      <td>Cleomedes</td>
      <td>De motu circulari corporum caelestium</td>
      <td>1-2_1-7_2-4</td>
      <td>m1_1/m1_2/p1_2/p2_1/p2_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg001.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Poimandres</td>
      <td>1-29x</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg002.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Dialogus (sine titulo)</td>
      <td>1-17b</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg003.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Hieros logos</td>
      <td>1a, 1b, 2a, 2b, 3a, 3b, 4</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg004.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Πρὸς Τάτ ὁ κρατήρ ἡ μονάς</td>
      <td>1a, 1b, 2, 3, 4, 5, 6a, 6b, 7, 8a, 8b, 9, 10, 11a, 11b</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg005.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Πρὸς Τὰτ υἱόν ὅτι ἀφανὴς θεὸς φανερώτατός ἐστιν</td>
      <td>1a, 1b, 2, 3, 4, 5, 6, 7, 8, 9, 10a, 10b, 11</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg006.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Ὅτι ἐν μόνῳ τῷ θεῷ τὸ ἀγαθόν ἐστιν, ἀλλαχόθι δὲ οὐδαμοῦ</td>
      <td>1a, 1b, 2a, 2b, 3a, 3b, 4a, 4b, 5, 6</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg007.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Ὅτι μέγιστον κακὸν ἐν ἀνθρώποις ἡ περὶ τοῦ θεοῦ ἀγνωσία</td>
      <td>1a, 1b, 2a, 2b, 3</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg008.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Ὅτι οὐδὲν τῶν ὄντων ἀπόλλυται, ἀλλὰ τὰς μεταβολὰς ἀπωλείας καὶ θανάτους πλανώμενοι λέγουσιν</td>
      <td>1a, 1b, 2, 3, 4, 5</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg009.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Περὶ νοήσεως καὶ αἰσθήσεως. [ὅτι ἐν μόνῳ τῷ θεῷ τὸ καλὸν καὶ ἀγαθόν ἐστιν, ἀλλαχόθι δὲ οὐδαμοῦ]</td>
      <td>1a, 1b, 1c, 2, 3, 4a, 4b, 5, 6, 7, 8, 9, 10</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg010.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Κλείς</td>
      <td>1a, 1b, 2, 3, 4a, 4b, 5, 6, 7, 8a, 8b, 9, 10a, 10b, 11, 12, 13, 14a, 14b, 15a, 15b, 16, 17, 18, 19a, 19b, 20, 21, 22a, 22b, 23, 24a, 24b, 25</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg011.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Νοῦ πρὸς Ἑρμῆν</td>
      <td>1a, 1b, 2, 3, 4a, 4b, 5, 6a, 1ax, 1bx, 6b, 7, 8a, 8b, 9, 10, 11, 14bx, 12a, 12b, 13a, 13b, 17cx, 14a, 14b, 14c, 15a, 15b, 16a, 16b, 17a, 17b, 17c, 18, 19, 20a, 20b, 21a, 21b, 22a, 22b</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg012.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Περὶ νοῦ κοινοῦ πρὸς Τάτ</td>
      <td>1-23b</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg013.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Πρὸς τὸν υἱὸν Τὰτ ἐν ὄρει λόγος ἀπόκρυφος περὶ παλιγγενεσίας καὶ σιγῆς ἐπαγγελίας</td>
      <td>1-13bx</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg014.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Ἀσκληπιῷ εὖ φρονεῖν</td>
      <td>1-10</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg016.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Ὅροι Ἀσκληπιοῦ πρὸς Ἄμμωνα βασιλέα</td>
      <td>1a, 1b, 2, 3, 4, 5, 6, 7, 8, 9, 10a, 10b, 11, 12, 13, 14, 15, 16, 17, 18, 19</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg017.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Dialogus (sine titulo)</td>
      <td>1-1</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg018.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Περὶ τῆς ὑπὸ τοῦ πάθους τοῦ σώματος ἐμποδιζομένης ψυχῆς</td>
      <td>1-16</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1286.tlg020.1st1K-grc1</td>
      <td>Hermetica</td>
      <td>Fragmenta</td>
      <td>1-29_1-1</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg1287.tlg001.1st1K-grc1</td>
      <td>Crantor</td>
      <td>Fragmenta</td>
      <td>1-16</td>
      <td>m5_2/m4_1</td>
    </tr>
    <tr>
      <td>tlg1304.tlg002.1st1K-grc1</td>
      <td>Democritus</td>
      <td>Fragmenta</td>
      <td>0a, 0b, 0c, 1, 1a, 1b, 2, 2a, 2b, 2c, 3, 4, 4a, 4b, 4c, 5, 5a, 5b, 5c, 5d, 5e, 5f, 5g, 5h, 5i, 6, 7, 8, 8a, 8b, 9, 10, 10a, 10b, 11, 11a, 11b, 11c, 11d, 11e, 11f, 11g, 11h, 11i, 11k, 11l, 11m, 11n, 11o, 11p, 11q, 11r, 12, 13, 14, 14a, 14b, 14c, 15, 15a, 15b, 15c, 16, 16a, 17, 18, 18a, 18b, 19, 20, 20a, 21, 22, 23, 24, 25, 25a, 25b, 26, 26a, 26b, 26c, 26d, 26e, 26f, 27, 28, 28a, 28b, 28c, 29, 29a, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 53a, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 107a, 108, 109, 110, 111, 112, 113, 114, 115, 115a, 116, 117, 118, 119, 120, 121, 122, 122a, 123, 124, 125, 126, 127, 128, 129, 129a, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 144a, 145, 146, 147, 148, 149, 150, 151, 152, 152a, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 278, 279, 280, 281, 282, 283, 284, 285, 286, 287, 288, 289, 290, 291, 292, 293, 294, 295, 296, 297, 298, 298a, 298b, 299, 299a, 299b, 299c, 299d, 299e, 299f, 299g, 299h, 300, 301, 302, 302a, 303, 304, 305, 306, 307, 308</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg1309.tlg001.1st1K-grc1</td>
      <td>Dialexeis</td>
      <td>Fragmenta</td>
      <td>1-9_1-6</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg1311.tlg001.1st1K-grc1</td>
      <td>Anonymous</td>
      <td>Didache XII Apostolorum</td>
      <td>1-16_1-8</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1319.tlg002.1st1K-grc1</td>
      <td>Diogenes of Apollonia</td>
      <td>Fragmenta</td>
      <td>1-10</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg1320.tlg001.1st1K-grc1</td>
      <td>Diogenes Babylonius</td>
      <td>Testimonia et Fragmenta</td>
      <td>1-126</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg1325.tlg001.1st1K-grc1</td>
      <td>Diogenes Sinopensis Epistulae</td>
      <td>Epistulae</td>
      <td>1-51_1-1</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg1329.tlg001.1st1K-grc1</td>
      <td>Dionysius Corinthius</td>
      <td>Fragmenta</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1337.tlg003.1st1K-grc1</td>
      <td>Dorotheus of Sidon</td>
      <td>Fragmenta alia antiqua</td>
      <td>1-25</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1347.tlg004.1st1K-grc1</td>
      <td>Epimenides</td>
      <td>Fragmenta</td>
      <td>1-26</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg1367.tlg001.1st1K-grc1</td>
      <td>Euripides Epistulae</td>
      <td>Epistulae</td>
      <td>1-5_1-6</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg1383.tlg001.1st1K-grc1</td>
      <td>Geminus</td>
      <td>Elementa astronomia</td>
      <td>1-18_1-19</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg1389.tlg001.perseus-grc2</td>
      <td>Harpocration</td>
      <td>Lexicon in decem oratores Atticos</td>
      <td>a, b, g, d, e, z, h, q, i, k, l, m, n, c, o, p, r, s, t, u, f, y_habaris, abios, abrokomas, agatharchos, agathes, agasikles, agoi, agelaion, agenes, agesilaos, aglauros, hagneuete, agnias, agnous, agnomonos, agoras, agoranomoi, agorasai, agrafiou, agrious, agrule, aguias, agurrios, agonian, agoniontes, adeetos, adelfizein, ademonouses, adefagous, adiastaton, adikiou, adokimastos, adrasteian, adunatoi, aei, aidris, aeilogia, aeiesuo, aerkton, aetos, azenieus, azeteton, atheoretos, athenodoros, athmoneus, aigeion, aigeidai, aigidas, aigilieus, aidesasthai, aithalides, aithiopion, aikias, ainious, aixonesin, akademeia, akamantis, akare, akinakes, ake, akmazeis, akritos, akroasthai, akte, aktia, alabastothekai, halaieus, alastor, alexandros, halipedon, halimousioi, halirrothios, alketas, alkibiades, alkimachos, alkmaionidai, alogian, halogoi, halonnesos, alope, halourgopolike, haloa, alopeke, alopekonnesos, amadokos, amazoneion, hamaxanteia, amblothridion, ambrakia, hamippoi, ammonis, amorges, amorgos, amfignoein, amfideai, amfidromia, amfiktuones, amfipolis, amfisbetein, amfissa, amfoteropaoun, hamosgepos, anaballei, anagein, anageis, anaginoskomenos, anagkaion, anagurasios, anadikasasthai, anathesthai, anairetheis, anainesthai, anakaiasin, anakalupteria, anakeion, anakrisis, anaktes, anaxagoras, anaxibios, anapodizomena, anaseisas, anasuntaxas, anati, anaflustioi, anaforan, andera, andokidou, andrapodokapelos, andrapodistes, andreia, androlepsia, andron, anelousa, anemutas, anepopteutos, aneskeuasanuo, aneton, anechaitise, anekei, antheia, anthemokritos, anthemous, anthesterion, anthene, anthupomosan, anidrutos, anoikos, antepitithesin, antiatais, antibabthentos, antigenidas, antigrafeus, antigrafe, antithesis, antikura, antiochis, antifon, antipatros, antissa, antrones, antomosia, anorthiazon, axioi, axiochos, axoni, aopta, apage, apagoreuein, apathe, aparithmon, apartilogia, apatouria, apeipein, apergasamenos, apeschoinismenos, apeaoemenos, apecheia, apillein, apistein, aplas, apobates, apografe, apodektai, apodidomenoi, apoikia, apoikodomeis, apokeruttontes, apokrisis, apolachein, apoleloipotes, apolexis, apomatton, apollon, apomisthoi, apo, aponome, apopefasmenon, apopompas, aporrexantes, aporreta, aporotatos, aposaxanta, apostasiou, apostesamenon, apostoleis, apostrofen, apotaxis, apotimetai, apotafos, apoteichisai, apoteteichismenos, apofasis, apoforan, apopsefizontai, aprobouleuton, aproskleton, aprostasiou, aproton, arafenios, argas, argoura, arguriotheke, arguritis, argurokopeion, arginousai, arguropous, argaios, ariobarzanes, ardettos, arete, arthmios, aristeus, aristtlla, aristion, arkteusai, arktouros, arkuoros, harmostai, arreforein, artemisia, artemision, arubbas, archairesiazein, archaios, arche, archen, archidameios, asemanta, aspasia, astathmetotaton, astikton, astrabe, astunomos, asunthetotaton, atarneus, atechnos, atimetos, atimos, atta, attes, attikois, aifentes, auleios, aulia, aulizomenoi, auuodikein, autokleides, au, autolekuthoi, auuolukos, automachein, autochthones, afairesis, afareus, afanes, afeis, af, aforme, afosio, afrodision, afuas, acharistein, balbisin, barathron, basanos, basilike, basileios, baskainei, basanisas, batalos, baubous, bebaioseos, besaies, biaion, blimazein, blisai, boedromia, bothunos, boleones, bombulios, boulaia, bouleia, bouleuseos, boutades, boutes, boufonia, boucheta, boones, brutidai, bomolocheuesthai, galepsos, gamelia, ganos, geisipous, gennetai, gerarai, geraneia, gerra, geofanion, gepedon, glaukos, glukera, gnosis, gorgura, grammateus, grafeus, grafein, grafe, grupanion, grullos, gulios, gulippos, gulon, goniasmos, daidalou, daeira, damon, daochos, dareikos, dateisthai, datos, deeseis, deigma, deipnoforos, deiradiotes, deinoi, dekazon, deka, dekadarchia, dekateuein, dekateutas, dekatelogous, dekeleikos, delfinion, derkulidas, dermatikon, dermestes, deusopoios, demainetos, deliastai, demarchos, demokoinos, demopoietos, demosios, demotele, demoteuomenos, demofanes, diagoreuon, diagramma, diagrafe, diagrapsasthai, diadoseis, diakechremenon, diastasis, diagrapsantos, diathesis, dialexis, dia, diacheirotonia, diamemetremene, diametron, diaskeuasasthai, diaseistous, diapsefisis, diamarturia, diaitetai, diasuesai, didaskalos, diegguesin, diekodonise, di, diespeusamen, dieskarifesamethl, dieteinanto, diellaxen, dierxa, diipoleia, dikaiogenes, dikaiopolis, dikaiosis, dike, dioikiein, diopeuon, diotimos, diofantos, dioaugion, diomosia, dokimastheis, doriskos, dosis, drakontides, drakon, drggilon, dromokerukes, drumos, drus, dusanios, dusaules, dusopoumai, dorieus, doroxenia, doron, ean, hebdomeuomenou, eggutheke, hedoliasai, ethnos, eiloteuein, eisaggelia, eis, eisepodizon, eisfresein, ekalistroun, hekates, hekatombaion, hekatomnos, hekatompedon, ekdeia, ekdexamenos, ekdikasasthai, ekdosis, ekkleteuein, eklogeis, eklozete, ekmarturia, ek, ekplintheusas, ekpolemosai, ekfulloforesli, elaious, elateia, elafrotatous, eleokopon, eleutherios, eleusinia, helikteres, helixos, hellanodikai, hellenotamiai, embeblemena, hembios, embrachu, emmenoi, empodon, empousa, henai, endeixis, endekazontas, en, enepiskemma, eneskeuasmenen, enetimato, hene, enthrupua, enneakrounon, ennea, ensemainomenos, exagistos, exaireseos, exarasasthai, exegguesis, exenize, exepremnizon, exetazesthai, exegetes, exekestos, exorchesamenos, exoules, exomosia, epaggelia, epaktos, epaktrokeles, epallaxeis, epanafora, epairomenos, epedikase, mnemati, epeskepsato, epibates, epibaetas, epiboion, epibole, epignomonas, epigrafeas, epiguion, epidekaton, epipempton, epi, epidiatithesthai, epidietes, epidikos, epithetous, epikekeruchenai, epikerukeia, epikrates, epilachon, epimeletes, epimenia, epiorkesanta, epiplon, episemainesthai, episitia, episkopos, epistates, epistathmos, epiteleoun, epitimetas, epiteichisma, epitrepein, epitritais, epichares, epicheirotonia, epipsefizon, epogdoon, epobelia, eponia, eponumoi, epopteukoton, eranizontes, erga, ergiske, ergokles, ergofilos, herkeios, herma, hermai, hermos, hermes, hermias, eroiadai, eruthraioi, erchiathen, espathato, estiator, eschara, eschatia, hetaireia, eteobouuadai, heterofthalmos, euagoras, euaion, euandria, euboulos, eudikos, euenos, eueniotata, euthias, euthunoi, euthuoron, eumenides, euneidai, euxitheos, euoi, euofthalmos, eurubaton, eurumedon, eurusakeion, eusumbolos, eufraios, euonumeis, efesis, efektos, efetai, ef, eforia, eformein, echinos, heolokrasia, zeira, zeuxis, zelotupoun, zetetes, hegemonia, hegemon, hegesippos, heduleion, eetioneia, ekroteriasmenoi, heliaia, helikia, hemiekton, hemioliasmos, epeiron, herakleia, heraion, eria, esmen, eitemenen, hefaistia, eion, thargelia, themenos, themisteuein, themison, theogeiton, theognis, theoinion, theokrines, therapnai, therman, thermopulai, thersandros, thesthli, thesmos, thesmothetai, thetes, thettalos, theudosian, theorika, theoris, themakeus, theramenes, theseion, thetes2, thiasos, thibron, tholos, thorai, thorikos, thripedeston, thronion, thumaitadai, thurgonidai, thustion, idian, idrieus, hierax, hiera, hieromenia, hieromnemones, hierofantes, hieronumos, ithufalloi, ikarieus, hiketeria, ionios, ipnos, hipparchos, hippas, hippia, hippodameia, isa, isai, isaios, ismenias, isolaites, isoteles, ischandros, itelios, ion, kabule, kadiskos, kadmeia, katharsion, kathelon, kathekonta, kathetos, kai, gnomes, kainos, kakotechnion, kakos, kakoseos, kalaureia, kaneforoi, karkinos, karpou, karuanda, katabole, katadedesthai, kata, katadikasamenos, katagein, katastasis, katatome, katapaex, katachusmata, katacheirotonia, katapseudomarturesamenos, kateleusan, katoikodomesen, kebrena, kegchreon, keioi, keiriades, kekropis, keleontes, kerameis, kerameikos, kerkidas, kerkouros, kerkops, keineas, kersobleptes, kestrinoi, kefalos, kefalethen, kedonides, kekis, kepos, kerukeia, kerukes, kettoi, kefisieus, kefisodoros, kefisodotos, kigklis, kinados, kinesias, kirraion, kisthene, kittoforos, klimazei, klerouchoi, klesis, kleteres, kobaleia, koinon, koinonikon, koironidai, kolluteus, kolonetas, komistika, kommata, kordakismos, koroplathos, korsiai, kotulaion, kotus, krauallidai, krastis, krithoten, krioeus, krobulos, ktesiou, ktesifon, kudathenaieus, kudantides, kutherios, kuthnioi, kukloi, kumbion, kunnidai, kunosarges, kuprothemis, kupassis, kurbeis, kureion, kurebion, kuria, kursilon, kodeia, kolias, lagiska, lampadion, lampas, lamptreis, larkos, laruggizein, lebadeia, lembos, leschai, leukas, leuke, leukonoieus, leuktra, lechaion, leokoreion, lexiarchikon, lexis, lete, lithos, liknoforos, lipara, logismos, logistai, logopoios, logou, loidias, loutroforos, lousieus, lukeion, lukiourgkis, lukourgos, luslndros, lusimachos, maimakterion, makrokefaloi, malkiomen, malthe, mantineon, margites, maroneia, massalia, masteira, masteres, matruleion, mausolos, machatas, medimnos, methone, meion, meiagogesai, melanippeion, melanopos, meline, melite, mende, menelaos, mesegguema, metageitnion, metalleis, metapurgion, metoikion, metoionisasthai, metronomoi, metaulos, mekuberna, melobios, meuroion, mikon, molpis, moirokles, moirologchesai, mounuchia, mountchion, mousaios, moran, mulothros, murioi, murtanon, murtis, muson, nais, nannion, naukleros, naukrarika, nautodikai, neales, nebrizon, neelata, nemeas, nemeseia, neon, neoria, neosi, nikaia, nikanor, nike, notheia, nomofulakes, notion, numfaion, xenizein, xenikon, xeniteuomenous, xeraloifein, xupetaiones, xustis, obolostatoi, hodos, othneios, oiethen, oikeos, oikema, oikiskoi, oineis, oinoe, oion, oios, oisume, hoti, oligoresete, holoschoinoi, homereuontas, homeridai, homoerkes, homose, homou, onetor, onomazon, oxuthumia, opisthodomos, orgas, orgeonas, orgeon, orika, orignethenai, orkane, ornitheutes, horos, oron, orrodein, orugma, hosion, oschoforoi, ouk, ousias, ofrunion, ocheion, pagasai, paianieis, palinairetos, palinskion, palimbolon, palleneus, palamnaios, pambotades, pandaisia, pandemos, pandia, pandosia, pandionis, panathenaia, panaktos, pandrosos, paragrafe, paraggelia, parakaesis, paralos, parabuston, parapeptokos, parakataboae, parabaloito, paredros, pareiai, parresias, parakrouetai, paraskenia, parasemos, parastasis, parafruktorein, paregguesen, parelthein, parousia, parrasios, pasinos, pasion, pataikion, pediaka, pedaritos, pezetairoi, pelanos, pentakosiomedimnon, pepirethos, peison, penestai, pentekontarchos, pentekoste, peplos, pergasethen, periandros, peri, perithoidai, perilaos, periodos, perioikion, peripolos, peristatoi, peristasin, peristoichizetai, peristoichoi, pefasmenes, peforiosthai, pegai, pelex, pinakia, pittheus, pleisteriasantes, plerotes, plintheion, paunteria, plotheus, podostrabe, podokakke, politeia, polemarchos, poliochos, pompeias, pompeia, porios, porthmos, polugnotos, polustratos, poseideon, potamos, proballomenous, probolas, probouleuma, probolion, proboloi, proedroi, proerosia, prothesmias, proklesis, prokonia, prometretas, pronaia, propempta, propepokotes, propulaia, prosepoiesato, prosklesis, prospaltioi, prostates, prostasia, pros, prostimemata, prostropaion, proteleia, profereis, prosfora, procheirotonia, proschaireteria, prutaneia, prutaneias, prutanepsonta, prutaneis, ptoiodoros, puanopsia, ppsgela, ptomata, puelida, puthaea, pukni, puaai, purilampes, purra, poletai, polas, polosi, pomala, hraisas, hrenaia, hretorike, hrinon, hrodogotne, hrodonia, hrothion, hroptron, hruta, saboi, seirina, semnai, serreion, sesemasmenoi, seuthes, sekos, seraggion, semeia, sthenelos, sigeion, simos, simulos, simon, sinope, sipua, siteresion, sitos, sitofulakes, skambonidai, skafeforoi, skafion, skeuopoiounta, skenites, skenen, skepsis, skiathos, skiapodes, skiron, skirafia, skuthikai, smikuthion, soloi, spartolos, spermologos, stasiotes, stafuloboleion, stefaneforos, stefanon, steirieus, strateia, strategoi, strabax, strepsa, streptous, strombichides, strouthes, strofades, strume, sturax, stroter, suaas, sulloges, sumbola, summoria, suggrafeis, sundikoi, sunegoroi, sugkletos, suntaxis, sunteleis, sunteleia, sfettos, sfodrias, taureas, tamiai, tamunai, ta, tetartemorion, tetrakosioi, tetrarchia, tetrupemene, tetufomai, telefanes, tenos, tetes, tilfossaion, timema, titakidai, topeion, torone, tous, tragikos, trapezoforos, triakas, triboneuomenoi, trigonon, trierarchema, trikaranon, trikefalos, triptera, tritemorion, triton, tritopatores, tritomenis, trittus, turmeidai, turtaios, huakinthides, hubadai, hugieia, hupagousin, huperbolos, huperemeroi, hupo, hupokudeis, hupologon, huponomeuontes, hupostesas, hupofonia, hupomosia, husiai, falaggia, faleron, fanias, fanostrate, farmakos, farmakonta, fasis, faskolon, faullos, fellea, fegaieusi, felomata, fegousion, fthoen, filammon, filepsios, filiskos, filosofein, filotesia, fimoi, fluea, forbanteion, forine, frateres, frearrios, froudos, fruktoron, frunondas, frunon, fularchos, fule, charaka, chalkeia, charikles, chernibon, chilioi, chiliothenta, chilon, chledos, choes, cholargeus, cholleidai, chrestai, chrusis, chrusochoein, chutroi, pseudeggrafe, pseudokleteia, psithuristes</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1390.tlg004.1st1K-grc1</td>
      <td>Hecataeus of Abderita</td>
      <td>Fragmenta</td>
      <td>1-17</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg1402.tlg001.1st1K-grc1</td>
      <td>Hephaestion</td>
      <td>Enchridion de Metris</td>
      <td>1-16_1-6</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1402.tlg002.1st1K-grc1</td>
      <td>Hephaestion</td>
      <td>Introductio metrica</td>
      <td>1-12</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1402.tlg003.1st1K-grc1</td>
      <td>Hephaestion</td>
      <td>De poematis</td>
      <td>1-8_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1402.tlg004.1st1K-grc1</td>
      <td>Hephaestion</td>
      <td>De Signis</td>
      <td>1-11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1402.tlg005.1st1K-grc1</td>
      <td>Hephaestion</td>
      <td>Fragmenta</td>
      <td>1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1409.opp003.1st1K-grc1</td>
      <td>Heraclides Ponticus</td>
      <td>Epitoma to Res Publica Atheniensium</td>
      <td>preface, 1, 2, 3, 4, 5, 6, 7, 8</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg1414.tlg001.1st1K-grc1</td>
      <td>Heraclitus</td>
      <td>Allegoriae (= Quaestiones Homericae)</td>
      <td>1-75</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg1416.tlg007.1st1K-grc1</td>
      <td>Philo of Byblos</td>
      <td>De diversis verborum significationibus (= Περὶ διαφόρους σημασίας κατ’ ἀλφάβητον) (epitome operis Herennii Philonis)</td>
      <td>Α, Β, Γ, Δ, Ε, Ζ, Η, Θ, Ι, Κ, Λ, Μ, Ν, Ο, Π, Ρ, Σ, Τ, Υ, Φ_1-107</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1419.tlg001.1st1K-grc1</td>
      <td>Hermas</td>
      <td>The Shepherd of Hermas</td>
      <td>1-27_1-4_1-5</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1431.tlg003.1st1K-grc1</td>
      <td>Hipparchus</td>
      <td>In Arati et Eudoxi phaenomena commentariorum libri iii</td>
      <td>1-3_1-5_1-23</td>
      <td>m2_2</td>
    </tr>
    <tr>
      <td>tlg1434.tlg004.1st1K-grc1</td>
      <td>Hippias of Elis</td>
      <td>Fragmenta</td>
      <td>1-21</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg1441.tlg001.1st1K-grc1</td>
      <td>Iamblichus (Scr. Erot.)</td>
      <td>Babyloniaca</td>
      <td>1-4</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg1443.tlg001.1st1K-grc1</td>
      <td>Ignatius of Antioch</td>
      <td>Epistulae vii genuinae</td>
      <td>1-7_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1443.tlg002.1st1K-grc1</td>
      <td>Ignatius of Antioch</td>
      <td>Epistulae interpolatae et epistulae suppositiciae (recensio longior) [Sp.]</td>
      <td>13-12_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21_1-3</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1447.tlg001.1st1K-grc1</td>
      <td>Irenaeus, Saint, Bishop of Lyon</td>
      <td>Libros quinque adversus haereses</td>
      <td>1-46_1-3</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1447.tlg009.1st1K-grc1</td>
      <td>Irenaeus, Saint, Bishop of Lyon</td>
      <td>Fragmenta Synodicae Epistulae.</td>
      <td>1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1463.tlg001.1st1K-grc1</td>
      <td>Liber Enoch</td>
      <td>Apocalypsis Enochi</td>
      <td>1-89_1-5</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg1482.tlg001.1st1K-grc1</td>
      <td>Cyranides</td>
      <td>Cyranides</td>
      <td>1-4_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 12x, 10x_1-4</td>
      <td>p1_2/p2_1/p2_2</td>
    </tr>
    <tr>
      <td>tlg1484.tlg001.1st1K-grc1</td>
      <td>Martyrium Polycarpi</td>
      <td>Martyrium Polycarpi</td>
      <td>1-epilogus_1-alius</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1486.tlg001.1st1K-grc1</td>
      <td>Matron of Pitana</td>
      <td>Convivium Atticum</td>
      <td>1-122</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg1486.tlg002.1st1K-grc1</td>
      <td>Matron of Pitana</td>
      <td>Fragmenta</td>
      <td>urn:cts:greekLit:tlg1486.tlg002.1st1K-grc1_1-6_1-6</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg1487.tlg001.1st1K-grc1</td>
      <td>Maximus, Astrologus</td>
      <td>Περὶ καταρχῶν</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1487.tlg002.1st1K-grc1</td>
      <td>Maximus, Astrologus</td>
      <td>Περὶ καταρχῶν (epitome)</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1542.tlg001.1st1K-grc1</td>
      <td>Numenius of Apamea</td>
      <td>Fragmenta</td>
      <td>1-22</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1548.tlg001.1st1K-grc1</td>
      <td>Oenomaus of Gadara</td>
      <td>Fragmenta</td>
      <td>1-14</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1551.tlg001.1st1K-grc1</td>
      <td>Oracula Sibyllina</td>
      <td>Oracula</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 11, 12, 13, 14</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg1551.tlg002.1st1K-grc1</td>
      <td>Oracula Sibyllina</td>
      <td>Fragmenta</td>
      <td>1-8</td>
      <td>p2_2/p3_1</td>
    </tr>
    <tr>
      <td>tlg1553.tlg001.1st1K-grc1</td>
      <td>Palaiphatos</td>
      <td>De Incredibilibus</td>
      <td>prologue, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52</td>
      <td>m4_2</td>
    </tr>
    <tr>
      <td>tlg1562.tlg002.1st1K-grc1</td>
      <td>Parmenides</td>
      <td>Fragmenta</td>
      <td>1-25</td>
      <td>m6_2/m5_1</td>
    </tr>
    <tr>
      <td>tlg1595.tlg221.1st1K-grc1</td>
      <td>Philodemus</td>
      <td>De Musica Librorum Quae Exstant</td>
      <td>urn:cts:greekLit:tlg1595.tlg221.1st1K-grc1_1-4_1-38</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg1595.tlg370.1st1K-grc1</td>
      <td>Philodemus</td>
      <td>Volumina Rhetorica</td>
      <td>1-2_4a, 2a, 3a, 1, 2b, 3b, 4b, 5, 6, 7, 2, 3, 4, 8, 9, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 9a, 10a, 11a, 12a, 13a, 14a, 15a, 16a, 17a, 18a, 19a, 20a, 21a, 22a, 32a</td>
      <td>m1_1</td>
    </tr>
    <tr>
      <td>tlg1596.tlg002.1st1K-grc1</td>
      <td>Philolaus of Croton</td>
      <td>Fragmenta</td>
      <td>1-23</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg1600.tlg001.perseus-grc2</td>
      <td>Philostratus Sophista</td>
      <td>Imagines</td>
      <td>1-2_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1602.tlg001.1st1K-grc1</td>
      <td>Philoxenus of Alexandria</td>
      <td>Fragmenta</td>
      <td>1-12</td>
      <td>m1_1/m1_2</td>
    </tr>
    <tr>
      <td>tlg1617.tlg001.1st1K-grc1</td>
      <td>Marcus Antonius Polemon</td>
      <td>Declamationes</td>
      <td>1-2_1-65</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1622.tlg001.1st1K-grc1</td>
      <td>Polycarp</td>
      <td>Epistula ad Philippenses</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14_sal, 1, 2, 3, 4</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1626.tlg001.1st1K-grc1</td>
      <td>Polycrates Ephesius</td>
      <td>Fragmentum Synodicae Epistulae</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1634.tlg002.1st1K-grc1</td>
      <td>Prodicus</td>
      <td>Fragmenta</td>
      <td>1-11</td>
      <td>m5_1</td>
    </tr>
    <tr>
      <td>tlg1664.tlg001.1st1K-grc1</td>
      <td>Seniores Alexandrini</td>
      <td>Fragmenta</td>
      <td>1-11</td>
      <td>p4_2/p5_1/p5_2/p6_1/p6_2</td>
    </tr>
    <tr>
      <td>tlg1665.tlg001.1st1K-grc1</td>
      <td>Seniores Apud Irenaeum</td>
      <td>Reliquiae plurium anonymorum</td>
      <td>Monitum, 1, 2, 3, 6, 7, 8, 9, 10, 11</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1669.tlg004.1st1K-grc1</td>
      <td>Serapion Astrologus</td>
      <td>Fragmenta</td>
      <td>156v_225-231</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1681.tlg001.1st1K-grc1</td>
      <td>Solonis Epistulae</td>
      <td>Epistulae</td>
      <td>1-4</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg1692.tlg005.1st1K-grc1</td>
      <td>Speusippus</td>
      <td>Fragmenta</td>
      <td>1-230</td>
      <td>m4_1</td>
    </tr>
    <tr>
      <td>tlg1699.tlg001.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ τοῦ δοκεῖν καὶ τοῦ εἶναι</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1699.tlg002.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ αὐταρκείας</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1699.tlg003.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ φυγῆς</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1699.tlg004.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ συγκρίσεως πενίας καὶ πλούτου</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1699.tlg005.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ συγκρίσεως πενίας καὶ πλούτου</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1699.tlg006.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ τοῦ μὴ εἶναι τέλος ἡδονήν</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1699.tlg007.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ περιστάσεων</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1699.tlg008.1st1K-grc1</td>
      <td>Teles Megarenesis</td>
      <td>Περὶ ἀπαθείας</td>
      <td>1-1</td>
      <td>m3_2</td>
    </tr>
    <tr>
      <td>tlg1701.tlg001.1st1K-grc1</td>
      <td>Testamentum Abrahae</td>
      <td>Testamentum Abrahae (recensio A)</td>
      <td>1-20</td>
      <td>p1_2/p2_1/p2_2</td>
    </tr>
    <tr>
      <td>tlg1701.tlg002.1st1K-grc1</td>
      <td>Testamentum Abrahae</td>
      <td>Testamentum Abrahae (recensio B)</td>
      <td>1-14</td>
      <td>p1_2/p2_1/p2_2</td>
    </tr>
    <tr>
      <td>tlg1705.tlg001.1st1K-grc1</td>
      <td>Thales</td>
      <td>Epistulae</td>
      <td>1-2</td>
      <td>m6_1</td>
    </tr>
    <tr>
      <td>tlg1719.tlg001.1st1K-grc1</td>
      <td>Theodosius of Bithynia</td>
      <td>Sphaerica</td>
      <td>1-3_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23_1-1</td>
      <td>m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg1724.tlg001.1st1K-grc1</td>
      <td>Theon Smyrnaeus</td>
      <td>De utilitate mathematicae</td>
      <td>1-218</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg1725.tlg001.perseus-grc1</td>
      <td>Theophilus</td>
      <td>Ad Autolycum</td>
      <td>1-3_1-30</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1749.tlg001.1st1K-grc1</td>
      <td>Vitae Hesiodi Particula</td>
      <td>Vitae Hesiodi Particula</td>
      <td>1-1</td>
      <td>m8_2</td>
    </tr>
    <tr>
      <td>tlg1750.tlg001.1st1K-grc1</td>
      <td>Vitae Prophetarum</td>
      <td>De prophetarum vita et obitu (Dorothei recensio)</td>
      <td>1-23</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg1750.tlg002.1st1K-grc1</td>
      <td>Vitae Prophetarum</td>
      <td>De prophetarum vita et obitu (recensio anonyma)</td>
      <td>1-23</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg1750.tlg003.1st1K-grc1</td>
      <td>Vitae Prophetarum</td>
      <td>De prophetarum vita et obitu (recensio scholiis Hesychii aliorumque patrum in prophetas adjecta)</td>
      <td>1-13</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg1750.tlg004.1st1K-grc1</td>
      <td>Vitae Prophetarum</td>
      <td>Index apostolorum discipulorumque Domini</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 68a, 68b, A1, A2, A3, A4, A4a, A5, A6, A7, A8, A9, A10, A11, A12</td>
      <td>p1_1</td>
    </tr>
    <tr>
      <td>tlg1763.tlg001.1st1K-grc1</td>
      <td>Tryphon II Grammaticus</td>
      <td>De tropis (olim sub auctore Gregorio Corintho)</td>
      <td>p, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg1764.tlg001.1st1K-grc1</td>
      <td>Vettius Valens</td>
      <td>Anthologiarum libri</td>
      <td>1-9_1-19_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1765.tlg003.1st1K-grc1</td>
      <td>Vitae Aesopi</td>
      <td>Vita Aesopi Pl vel Accursiana (sub auctore Maximo Planude) (recensio 1)</td>
      <td>prologue, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33</td>
      <td>m1_1/m1_2</td>
    </tr>
    <tr>
      <td>tlg1765.tlg004.1st1K-grc1</td>
      <td>Vitae Aesopi</td>
      <td>Vita Aesopi (fort. auctore Aphthonio)</td>
      <td>1-1</td>
      <td>m1_1/m1_2</td>
    </tr>
    <tr>
      <td>tlg1765.tlg005.1st1K-grc1</td>
      <td>Vitae Aesopi</td>
      <td>Βιβλίον μυθικὸν τοῦ Αἰσώπου</td>
      <td>5-5</td>
      <td>m1_1/m1_2</td>
    </tr>
    <tr>
      <td>tlg1766.tlg001.perseus-grc1</td>
      <td>Tatianus</td>
      <td>Oratio ad Graecos</td>
      <td>1-42</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg1799.tlg001.perseus-grc2</td>
      <td>Euclid</td>
      <td>Elementa</td>
      <td>1-13_Def, Post, CN, Prop, Def1, Prop1, Def2, Prop2, Def3, Prop3_1-18</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg007.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Data</td>
      <td>toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg008.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Data (demonstrationes alterae)</td>
      <td>18-18_1-2</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg009.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Optica</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg010.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Opticorum recensio Theonis</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57_1-2</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg011.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Catoptrica (recensio Theonis?)</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg012.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Phaenomena</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13a, 13b, 14, 15, 16</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg013.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Phaenomena (recensio b)</td>
      <td>1-1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg014.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Phaenomena (demonstrationes alterae recensionis b)</td>
      <td>1-4</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg015.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Sectio canonis [Sp.]</td>
      <td>pr</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg016.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Fragmenta</td>
      <td>1-13_1-1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1799.tlg017.1st1K-grc1</td>
      <td>Euclid</td>
      <td>Epigramma</td>
      <td>1-1</td>
      <td>m3_1</td>
    </tr>
    <tr>
      <td>tlg1801.tlg001.1st1K-grc1</td>
      <td>Parodica Anonyma</td>
      <td>Incertorum fragmenta</td>
      <td>urn:cts:greekLit:tlg1801.tlg001.1st1K-grc1_1-9_1-23</td>
      <td>m11_1/m11_2/m10_1/m10_2/m9_1/m9_2/m8_1/m8_2/m7_1/m7_2/m6_1</td>
    </tr>
    <tr>
      <td>tlg1802.tlg001.1st1K-grc1</td>
      <td>Versus heroici</td>
      <td>Versus heroici</td>
      <td>1-end</td>
      <td>m9_1/m9_2/m8_1</td>
    </tr>
    <tr>
      <td>tlg1803.tlg001.1st1K-grc1</td>
      <td>Bruti Epistulae</td>
      <td>Epistulae</td>
      <td>1-70</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg001.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Vitae Herodotea</td>
      <td>1-38</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg002.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Plutarchi vita</td>
      <td>1-2_1-3</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg003.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Vita Proculea (e Chrestomathia)</td>
      <td>1-1</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg004.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Vita quarta</td>
      <td>1-1</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg005.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Vita quinta</td>
      <td>1-1</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg006.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Vita quinta</td>
      <td>1-1</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg007.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Vita septima</td>
      <td>1-1</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg008.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Tzetzae vita</td>
      <td>1-1</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg009.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Eustathii vita</td>
      <td>2-2</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg1805.tlg010.1st1K-grc1</td>
      <td>Vitae Homeri</td>
      <td>Sudae vita</td>
      <td>1-1</td>
      <td>p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg2000.tlg001.1st1K-grc1</td>
      <td>Plotinus</td>
      <td>Enneades</td>
      <td>1-6_1-9_1-11</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2001.tlg038.1st1K-grc1</td>
      <td>Themistius</td>
      <td>Analyticorum Posteriorum Paraphrasis</td>
      <td>1-addenda</td>
      <td>p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2001.tlg039.1st1K-grc1</td>
      <td>Themistius</td>
      <td>In Aristotelis Physica Paraphrasis</td>
      <td>1-8</td>
      <td>p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2001.tlg040.1st1K-grc1</td>
      <td>Themistius</td>
      <td>In Aristotelis Libros De Anima Paraphrasis</td>
      <td>1-2</td>
      <td>p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2001.tlg041.1st1K-grc1</td>
      <td>Themistius</td>
      <td>(Sophoniae) In Parva Naturalia Commentarium</td>
      <td>1-4</td>
      <td>p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2001.tlg042.1st1K-grc1</td>
      <td>Themistius</td>
      <td>Quae Fertur In Aristotelis Analyticorum Priorum Librum I</td>
      <td>3-8</td>
      <td>p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2003.tlg001.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Panegyric in Honor of the Emperor Constantinus</td>
      <td>1-39</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg002.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Panegyric on the Empress Eusebia</td>
      <td>1-19</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg003.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>The Heroic Deeds of the Emperor Constantius, or on Kingship</td>
      <td>1-39</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg004.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>A Consolation to Himself Upon the Departure of the Excellent Sallust</td>
      <td>1-8</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg005.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Letter to the Senate and the People of Athens</td>
      <td>1-13</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg006.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Letter to Themistius the Philosopher</td>
      <td>1-13</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg007.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>To the Cynic Heracleios</td>
      <td>1-25</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg008.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Hymn to the Mother of the Gods</td>
      <td>1-20</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg009.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>To the Uneducated Cynics</td>
      <td>1-20</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg010.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>The Caesars</td>
      <td>1-38</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg011.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Hymn to King Helios Dedicated to Sallust</td>
      <td>1-44</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg012.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Misopogon</td>
      <td>1-44</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg013.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Epistolae</td>
      <td>frag, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83_89b, 1, 2, 3, 4, 5, 6, 7, 8_1-21</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2003.tlg017.perseus-grc2</td>
      <td>Julian, Emperor of Rome</td>
      <td>Κατὰ Γαλιλαίων</td>
      <td>1-65</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2016.tlg001.1st1K-grc1</td>
      <td>Martyrium Perpetuae et Felcitatis</td>
      <td>Passio Perpetuae et Felicitatis</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg001.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Praeparatio Evangelica</td>
      <td>1-15_1-62_1-18</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg002.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Historia Ecclesiastica</td>
      <td>1-10_toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, prologue, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2018.tlg003.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>De Martyribus Palaestinae (Recensio Brevior)</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13_1-14</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg005.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Demonstratio Evangelica</td>
      <td>1-10_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30_1-112</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg007.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Contra Marcellum</td>
      <td>1-2_Pin, 1, 2, 3, 4_1-31</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg008.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Epistula ad Flacillum</td>
      <td>1-1</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg009.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>De Ecclesiastica Theologia</td>
      <td>1-3_Pin, Pref, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25_1-2</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg010.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>De Theophania (Fragmenta)</td>
      <td>1-17</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg011.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Onomasticon</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2018.tlg020.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Vita Constantini</td>
      <td>1-4_TOC, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74_1-1</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg021.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Constantini imperatoris oratio ad coetum sanctorum</td>
      <td>1-26_1-2</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg022.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>De Laudibus Constantini</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18_1-3</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2018.tlg023.1st1K-grc1</td>
      <td>Eusebius of Caesarea</td>
      <td>Generalis elementaria introductio (= Eclogae propheticae)</td>
      <td>1-4_1-35</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2021.tlg001.1st1K-grc1</td>
      <td>Epiphanius</td>
      <td>Ancoratus</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18_0, arg, 1, 2, 3, 4, 5</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2021.tlg002.1st1K-grc1</td>
      <td>Epiphanius</td>
      <td>Panarion (Adversus Haereses)</td>
      <td>praef1a, praef1b, praef2, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 20a, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64_1-72_1-9</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2021.tlg003.1st1K-grc1</td>
      <td>Epiphanius</td>
      <td>Anacephalaeosis [Sp.]</td>
      <td>1-63_1-1</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2022.tlg003.1st1K-grc1</td>
      <td>Gregory of Nazianzus</td>
      <td>Christus Patiens [Dub.] (Fort. Auctore Constantino Manasse)</td>
      <td>pr, 1_1-2610</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2022.tlg007.1st1K-grc1</td>
      <td>Gregory of Nazianzus</td>
      <td>Adversus Eunomianos (Orat. 27)</td>
      <td>1-9</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2022.tlg008.1st1K-grc1</td>
      <td>Gregory of Nazianzus</td>
      <td>De Theologia (Orat. 28)</td>
      <td>1-31</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2022.tlg009.1st1K-grc1</td>
      <td>Gregory of Nazianzus</td>
      <td>De Filio (Orat. 29)</td>
      <td>1-21</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2022.tlg010.1st1K-grc1</td>
      <td>Gregory of Nazianzus</td>
      <td>De Filio (Orat. 30)</td>
      <td>1-21</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2022.tlg011.1st1K-grc1</td>
      <td>Gregory of Nazianzus</td>
      <td>De Spiritu Sancto (Orat. 31)</td>
      <td>1-33</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2022.tlg060.1st1K-grc1</td>
      <td>Gregory of Nazianzus</td>
      <td>Carmina moralia</td>
      <td>1-24</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2023.tlg001.1st1K-grc1</td>
      <td>Iamblichus</td>
      <td>De Vita Pythagorica</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36_1-267</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2023.tlg002.1st1K-grc1</td>
      <td>Iamblichus</td>
      <td>Protrepticus</td>
      <td>21-21_praef, toc, 1, 2, 3, 25a, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25b, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2023.tlg003.1st1K-grc1</td>
      <td>Iamblichus</td>
      <td>De communi mathematica scientia</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2023.tlg004.1st1K-grc1</td>
      <td>Iamblichus</td>
      <td>In Nicomachi Arithmeticam Introductionem</td>
      <td>1-176</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2023.tlg006.1st1K-grc1</td>
      <td>Iamblichus</td>
      <td>De Mysteriis</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10_1-8</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2027.tlg001.1st1K-grc1</td>
      <td>Valerius Apsines</td>
      <td>Ars rhetorica</td>
      <td>1-12_1-44</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2027.tlg002.1st1K-grc1</td>
      <td>Valerius Apsines</td>
      <td>Περὶ τῶν ἐσχηματισμένων προβλημάτων</td>
      <td>2-6</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2029.tlg001.1st1K-grc1</td>
      <td>Anonymi summaria ratio geographiae in sphaera intelligendae</td>
      <td>Anonymi summaria ratio geographiae in sphaera intelligendae</td>
      <td>1-3_1-16</td>
      <td>p1_2/p2_1/p2_2/p3_1/p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2032.tlg001.1st1K-grc1</td>
      <td>Pappus Alexandrinus</td>
      <td>Synagoge</td>
      <td>1-4_1-105</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2034.tlg002.1st1K-grc1</td>
      <td>Porphyrius</td>
      <td>Vita Pythagorae</td>
      <td>1-60</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2034.tlg003.1st1K-grc1</td>
      <td>Porphyrius</td>
      <td>De abstinentia</td>
      <td>1-4_1-22</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2034.tlg005.1st1K-grc1</td>
      <td>Porphyrius</td>
      <td>Ad Marcellam</td>
      <td>1-35</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2034.tlg006.opp-grc1</td>
      <td>Porphyrius</td>
      <td>Isagoge Sive Quinque Voces</td>
      <td>1-1</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2034.tlg007.opp-grc1</td>
      <td>Porphyrius</td>
      <td>In Aristotelis Categorias Expositio Per Interrogationem Et Responsionem</td>
      <td>3-3</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2034.tlg014.1st1K-grc1</td>
      <td>Porphyrius</td>
      <td>Quaestionum Homericanum ad Iliadem pertinentium reliquiae</td>
      <td>1-24_1-765</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2034.tlg015.1st1K-grc1</td>
      <td>Porphyrius</td>
      <td>Zetemata codicis Vaticani</td>
      <td>1-2_1-3</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2034.tlg027.1st1K-grc1</td>
      <td>Porphyrius</td>
      <td>Historia philosophiae (fragmenta)</td>
      <td>praef, 1, 2, 3, 4_1-19</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2035.tlg002.1st1K-grc1</td>
      <td>Athanasius</td>
      <td>De Incarnatione Verbi</td>
      <td>1-57_1-3</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2035.tlg003.1st1K-grc1</td>
      <td>Athanasius</td>
      <td>De decretis Nicaenae synodi</td>
      <td>1-2_1-3</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2035.tlg117.1st1K-grc1</td>
      <td>Athanasius</td>
      <td>Oratio quarta contra Arianos [Sp.]</td>
      <td>1-36</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2035.tlg130.1st1K-grc1</td>
      <td>Athanasius</td>
      <td>Oratio I contra Arianos</td>
      <td>1-64</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2035.tlg131.1st1K-grc1</td>
      <td>Athanasius</td>
      <td>Oratio II contra Arianos</td>
      <td>1-82</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2035.tlg132.1st1K-grc1</td>
      <td>Athanasius</td>
      <td>Oratio III contra Arianos</td>
      <td>1-67</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2036.tlg001.1st1K-grc1</td>
      <td>Dexippus</td>
      <td>In Aristotelis Categorias Commentarium</td>
      <td>1-3</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2038.tlg001.1st1K-grc1</td>
      <td>Acta Thomae</td>
      <td>Acta Thomae</td>
      <td>1-170</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2039.tlg003.1st1K-grc1</td>
      <td>Diophantus Alexandrinus</td>
      <td>Fragmentum [Sp.] (e cod. Paris. suppl. gr. 387, fol. 181r)</td>
      <td>1-2</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2039.tlg004.1st1K-grc1</td>
      <td>Diophantus Alexandrinus</td>
      <td>Fragmentum [Sp.] (e cod. Paris. 453)</td>
      <td>1-22</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2039.tlg005.1st1K-grc1</td>
      <td>Diophantus Alexandrinus</td>
      <td>Fragmentum [Sp.] (e cod. Paris. gr. 2448)</td>
      <td>1-92</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2040.tlg002.perseus-grc2</td>
      <td>Basil, Saint, Bishop of Caesarea</td>
      <td>De legendis gentilium libris</td>
      <td>1-10_1-8</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2040.tlg004.perseus-grc2</td>
      <td>Basil, Saint, Bishop of Caesarea</td>
      <td>Epistulae</td>
      <td>1-368</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2041.tlg001.1st1K-grc1</td>
      <td>Marcellus of Ankara</td>
      <td>Fragmenta</td>
      <td>1-129</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg001.perseus-grc1</td>
      <td>Origen</td>
      <td>Contra Celsum</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8_1-76</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg005.1st1K-grc1</td>
      <td>Origen</td>
      <td>Commentarii In Evangelium Joannis</td>
      <td>1-32_1-401</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg006.1st1K-grc1</td>
      <td>Origen</td>
      <td>Fragmenta In Evangelium Joannis (In Catenis)</td>
      <td>1-140</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg007.perseus-grc1</td>
      <td>Origen</td>
      <td>Exhortatio ad martyrium</td>
      <td>1-51</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg008.perseus-grc1</td>
      <td>Origen</td>
      <td>De oratione</td>
      <td>1-34_1-1</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg009.opp-grc1</td>
      <td>Origen</td>
      <td>In Jeremiam (Homiliae 1-11)</td>
      <td>1-11_1-5</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg010.opp-grc1</td>
      <td>Origen</td>
      <td>Fragmenta In Jeremiam (In Catenis)</td>
      <td>1-71</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg011.opp-grc1</td>
      <td>Origen</td>
      <td>Fragmenta In Lamentationes (In Catenis de Prophetis)</td>
      <td>1-118</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg012.opp-grc1</td>
      <td>Origen</td>
      <td>Fragmentum In Lamentationes (In Catenis de Octateucho)</td>
      <td>1-1</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg013.opp-grc1</td>
      <td>Origen</td>
      <td>De Engastrimytho (Homilia In I Reg. [I Sam.] 28.3-25)</td>
      <td>1-10</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg014.opp-grc1</td>
      <td>Origen</td>
      <td>Fragmenta in Librum Primum Regnorum (In Catenis de Samuelis et Regnorum)</td>
      <td>1-22</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg015.opp-grc1</td>
      <td>Origen</td>
      <td>Fragmentum In Librum Primum Regnorum (In Catenis de Cantico Canticorum)</td>
      <td>1-1</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg016.opp-grc1</td>
      <td>Origen</td>
      <td>Homiliae In Lucam</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg017.opp-grc1</td>
      <td>Origen</td>
      <td>Fragmenta In Lucam (In Catenis)</td>
      <td>1-153</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg019.1st1K-grc1</td>
      <td>Origen</td>
      <td>Philocalia</td>
      <td>pr, 2_pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27_pr, toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg021.opp-grc1</td>
      <td>Origen</td>
      <td>In Jeremiam (Homiliae 12-20)</td>
      <td>12-20_1-8</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg029.opp-grc1</td>
      <td>Origen</td>
      <td>Commentarium In Evangelium Matthaei (Lib. 10-11)</td>
      <td>10-11_1-19</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg030.opp-grc1</td>
      <td>Origen</td>
      <td>Commentarium In Evangelium Matthaei (Lib. 12-17)</td>
      <td>12-17_1-36</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg044.1st1K-grc1</td>
      <td>Origen</td>
      <td>Fragmenta in Psalmos 1-150 [Dub.]</td>
      <td>1-25_2-11</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2042.tlg045.1st1K-grc1</td>
      <td>Origen</td>
      <td>Epistula ad Africanum</td>
      <td>1-1_1-18</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg048.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Genesim</td>
      <td>praef, 1_1-156</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg050.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Exodum</td>
      <td>1-29</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg051.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Leviticum</td>
      <td>1-23</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg052.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Numeros</td>
      <td>1-35</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg053.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Deuteronomium</td>
      <td>1-39</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg054.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Jesum Nave</td>
      <td>1-16</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg055.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Judices</td>
      <td>1-7</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg057.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Job</td>
      <td>1-42</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg058.1st1K-grc1</td>
      <td>Origen</td>
      <td>Selecta in Psalmos [Dub.]</td>
      <td>pr1, pr2, 1a, 1b, 2, 3, 4, 5, 6, 7, 8, 9, 10a, 10b, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 136, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150_1-10</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg061.1st1K-grc1</td>
      <td>Origen</td>
      <td>Fragmenta ex commentariis in Ezechielem</td>
      <td>30-44_25-1</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg066.1st1K-grc1</td>
      <td>Origen</td>
      <td>Adnotationes in Genesim</td>
      <td>7-46_4-34</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg067.1st1K-grc1</td>
      <td>Origen</td>
      <td>Adnotationes in Exodum</td>
      <td>15-31_25-1</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg068.1st1K-grc1</td>
      <td>Origen</td>
      <td>Adnotationes in Leviticum (fragmenta e catenis)</td>
      <td>4-27_27-16</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg069.1st1K-grc1</td>
      <td>Origen</td>
      <td>Adnotationes in Numeros</td>
      <td>11-24_7-17</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg070.1st1K-grc1</td>
      <td>Origen</td>
      <td>Adnotationes in Deuteronomium (fragmenta e catenis)</td>
      <td>1-33_7-6</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg071.1st1K-grc1</td>
      <td>Origen</td>
      <td>Adnotationes in Jesu filium Nave (fragmenta e catenis)</td>
      <td>3-8_14-26</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg072.1st1K-grc1</td>
      <td>Origen</td>
      <td>Adnotationes in Judices</td>
      <td>15-20_19-21</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg073.1st1K-grc1</td>
      <td>Origen</td>
      <td>Homiliae in Job (fragmenta in catenis, typus II)</td>
      <td>1-42_10-10</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg074.1st1K-grc1</td>
      <td>Origen</td>
      <td>Excerpta in Psalmos [Dub.]</td>
      <td>9-150_8-3</td>
      <td>p3_1p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg075.1st1K-grc1</td>
      <td>Origen</td>
      <td>Expositio in Proverbia (fragmenta e catenis)</td>
      <td>1-31_1-4</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg076.1st1K-grc1</td>
      <td>Origen</td>
      <td>Scholia in Canticum canticorum</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8_1-8</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg077.1st1K-grc1</td>
      <td>Origen</td>
      <td>Scholia in Matthaeum</td>
      <td>1-28_18-18</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg078.1st1K-grc1</td>
      <td>Origen</td>
      <td>Scholia in Lucam (fragmenta e cod. Venet. 28)</td>
      <td>1-2_1-20_1-26</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg079.1st1K-grc1</td>
      <td>Origen</td>
      <td>Commentarii in evangelium Joannis (lib. 19, 20, 28, 32)</td>
      <td>19-32_1-32_1-401</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg084.opp-grc1</td>
      <td>Origen</td>
      <td>Fragmenta In Jeremiam (E Philocalia)</td>
      <td>1-2_1-2</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2042.tlg086.1st1K-grc1</td>
      <td>Origen</td>
      <td>Homiliae in Job (fragmenta in catenis, typus I+II) (e codd. Vat.)</td>
      <td>1-42_2-18</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2045.tlg001.perseus-grc2</td>
      <td>Nonnus of Panopolis</td>
      <td>Dionysiaca</td>
      <td>1-48_0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 140, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 278, 279, 280, 281, 282, 283, 284, 285, 286, 287, 288, 289, 290, 291, 292, 293, 294, 295, 296, 297, 298, 299, 300, 301, 302, 303, 304, 305, 306, 307, 308, 309, 310, 311, 312, 313, 314, 315, 316, 317, 318, 319, 320, 321, 322, 323, 324, 325, 326, 327, 328, 329, 330, 331, 332, 333, 334, 335, 336, 337, 338, 339, 340, 341, 342, 343, 344, 345, 346, 347, 348, 349, 350, 351, 352, 353, 354, 355, 356, 357, 358, 359, 360, 361, 362, 363, 364, 365, 366, 367, 368, 369, 370, 371, 372, 373, 374, 375, 376, 377, 378, 379, 380, 381, 382, 383, 384, 385, 386, 387, 388, 389, 390, 391, 392, 393, 394, 395, 396, 397, 398, 399, 400, 401, 402, 403, 404, 405, 406, 407, 408, 409, 410, 411, 412, 413, 414, 415, 416, 417, 418, 419, 420, 421, 422, 423, 424, 425, 426, 427, 428, 429, 430, 431, 432, 433, 434, 435, 436, 437, 438, 439, 440, 441, 442, 443, 444, 445, 446, 447, 448, 449, 450, 451, 452, 453, 454, 455, 456, 457, 458, 459, 460, 461, 462, 463, 464, 465, 466, 467, 468, 469, 470, 471, 472, 473, 474, 475, 476, 477, 478, 479, 480, 481, 482, 483, 484, 485, 486, 487, 488, 489, 490, 491, 492, 493, 494, 495, 496, 497, 498, 499, 500, 501, 502, 503, 504, 505, 506, 507, 508, 509, 510, 511, 512, 513, 514, 515, 516, 517, 518, 519, 520, 521, 522, 523, 524, 525, 526, 527, 528, 529, 530, 531, 532, 533, 534, 535, 536, 537, 538, 539, 540, 541, 542, 543, 544, 545, 546, 547, 548, 549, 550, 551, 552, 553, 554, 555, 556, 557, 558, 559, 560, 561, 562, 563, 564, 565, 566, 567, 568, 569, 570, 571, 572, 573, 574, 575, 576, 577, 578, 579, 580, 581, 582, 583, 584, 585, 586, 587, 588, 589, 590, 591, 592, 593, 594, 595, 596, 597, 598, 599, 600, 601, 602, 603, 604, 605, 606, 607, 608, 609, 610, 611, 612, 613, 614, 615, 616, 617, 618, 619, 620, 621, 622, 623, 624, 625, 626, 627, 628, 629, 630, 631, 632, 633, 634, 635, 636, 637, 638, 639, 640, 641, 642, 643, 644, 645, 646, 647, 648, 649, 650, 651, 652, 653, 654, 655, 656, 657, 658, 659, 660, 661, 662, 663, 664, 665, 666, 667, 668, 669, 670, 671, 672, 673, 674, 675, 676, 677, 678, 679, 680, 681, 682, 683, 684, 685, 686, 687, 688, 689, 690, 691, 692, 693, 694, 695, 696, 697, 698, 699, 700, 701, 702, 703, 704, 705, 706, 707, 708, 709, 710, 711, 712, 568a, 713, 714, 715, 716, 717, 718, 719, 720, 721, 722, 723, 724, 725, 726, 727, 728, 729, 730, 731, 732, 733, 734, 735, 736, 737, 738, 739, 740, 741, 742, 743, 744, 745, 746, 747, 748, 749, 750, 751, 752, 753, 754, 755, 756, 757, 758, 759, 760, 761, 762, 763, 764, 765, 766, 767, 768, 769, 770, 771, 772, 773, 774, 775, 776, 777, 778, 145a, 779, 780, 781, 782, 783, 784, 785, 786, 787, 788, 789, 790, 791, 792, 793, 794, 795, 796, 797, 798, 799, 800, 801, 802, 803, 804, 805, 806, 807, 808, 809, 810, 811, 812, 813, 814, 815, 816, 817, 818, 819, 820, 821, 822, 823, 824, 825, 826, 827, 828, 829, 830, 831, 832, 833, 834, 835, 836, 837, 838, 839, 840, 841, 842, 843, 844, 845, 846, 847, 848, 849, 850, 851, 852, 853, 854, 855, 856, 857, 858, 859, 860, 861, 862, 863, 864, 865, 866, 867, 868, 869, 870, 871, 872, 873, 874, 875, 876, 877, 878, 879, 880, 881, 882, 883, 884, 885, 886, 887, 888, 889, 890, 891, 892, 893, 894, 895, 896, 897, 898, 899, 900, 901, 902, 903, 904, 905, 906, 907, 908, 910, 911, 912, 913, 914, 915, 916, 917, 918, 919, 920, 921, 922, 923, 924, 925, 926, 927, 928, 929, 930, 931, 932, 933, 934, 935, 936, 937, 938, 939, 940, 941, 942, 943, 944, 945, 946, 947, 948, 949, 950, 951, 952, 953, 954, 955, 956, 957, 958, 959, 960, 961, 962, 963, 964, 965, 966, 967, 968, 969, 970, 971, 972, 973, 974, 975, 976, 977, 978</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg2046.tlg001.perseus-grc2</td>
      <td>Quintus Smyrnaeus</td>
      <td>Fall of Troy</td>
      <td>1-14_1-658</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2048.tlg001.1st1K-grc1</td>
      <td>Sozomenus</td>
      <td>Historia Ecclesiastica</td>
      <td>1-9_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40_1-6</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg2049.tlg001.1st1K-grc1</td>
      <td>Sallustius</td>
      <td>De Deis et Mundo</td>
      <td>1-21</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2050.tlg001.1st1K-grc1</td>
      <td>Eunapius</td>
      <td>Vitae Sophistarum</td>
      <td>1-16</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2057.tlg002.1st1K-grc1</td>
      <td>Socrates Scholasticus</td>
      <td>Ecclesiastical history</td>
      <td>1-7_1-48</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg2058.tlg001.1st1K-grc1</td>
      <td>Philostorgius</td>
      <td>Historia ecclesiastica (fragmenta ap. Photium)</td>
      <td>1-12_1-14</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg2115.tlg060.opp-grc1</td>
      <td>Hippolytus</td>
      <td>Refutatio Omnium Haeresium (= Philosophumena)</td>
      <td>1-10_summary, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55_1-5</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2135.tlg001.1st1K-grc1</td>
      <td>Alypius</td>
      <td>Isagoge musica</td>
      <td>1-4_1-9</td>
      <td>p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2136.tlg001.1st1K-grc1</td>
      <td>Bacchius Geron</td>
      <td>Isagoge artis musicae</td>
      <td>1-101</td>
      <td>p9_2</td>
    </tr>
    <tr>
      <td>tlg2137.tlg001.1st1K-grc1</td>
      <td>Gaudentius</td>
      <td>Harmonica introductio</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23</td>
      <td>p3_2/p4_1/p4_2</td>
    </tr>
    <tr>
      <td>tlg2138.tlg001.1st1K-grc1</td>
      <td>Canticum Euripidis</td>
      <td>Ex Orestis Stasimo I</td>
      <td>1-1</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg2139.tlg001.1st1K-grc1</td>
      <td>Epitaphium Sicili</td>
      <td>Sicili Epitaphium</td>
      <td>1-1</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg2140.tlg001.1st1K-grc1</td>
      <td>Iamblichus Alchemista</td>
      <td>Fragmentum alchemica</td>
      <td>1-10</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2178.tlg001.1st1K-grc1</td>
      <td>Cassius Longinus</td>
      <td>Ars rhetorica</td>
      <td>1-6_1-1</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2178.tlg002.1st1K-grc1</td>
      <td>Cassius Longinus</td>
      <td>Excerpta</td>
      <td>1-24</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2178.tlg004.1st1K-grc1</td>
      <td>Cassius Longinus</td>
      <td>Fragmenta</td>
      <td>1-1_1-2</td>
      <td>p3_1</td>
    </tr>
    <tr>
      <td>tlg2189.tlg003.1st1K-grc1</td>
      <td>Callinicus</td>
      <td>Fragmenta</td>
      <td>1-1</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg001.1st1K-grc1</td>
      <td>Libanius</td>
      <td>Epistulae</td>
      <td>1-839_1-3</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00401.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 1</td>
      <td>1-285</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00402.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 2</td>
      <td>1-73</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00403.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 3</td>
      <td>1-36</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00404.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 4</td>
      <td>1-40</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00405.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 5</td>
      <td>1-53</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00406.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 6</td>
      <td>1-17</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00407.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 7</td>
      <td>1-12</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00408.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 8</td>
      <td>1-15</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00409.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 9</td>
      <td>1-17</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00410.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 10</td>
      <td>1-37</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00411.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 11</td>
      <td>1-271</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00426.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 26</td>
      <td>1-35</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00427.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 27</td>
      <td>1-42</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00428.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 28</td>
      <td>1-26</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00429.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 29</td>
      <td>1-34</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00430.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 30</td>
      <td>1-53</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00431.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 31</td>
      <td>1-44</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00432.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 32</td>
      <td>1-28</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00433.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 33</td>
      <td>1-43</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00434.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 34</td>
      <td>1-31</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00435.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 35</td>
      <td>1-27</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00436.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 36</td>
      <td>1-15</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00437.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 37</td>
      <td>1-22</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00438.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 38</td>
      <td>1-22</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00439.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 39</td>
      <td>1-21</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00440.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 40</td>
      <td>1-27</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00441.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 41</td>
      <td>1-18</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00442.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 42</td>
      <td>1-52</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00443.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 43</td>
      <td>1-18</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00444.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 44</td>
      <td>1-4</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00445.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 45</td>
      <td>1-34</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00446.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 46</td>
      <td>1-44</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00447.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 47</td>
      <td>1-38</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00448.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 48</td>
      <td>1-40</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00449.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 49</td>
      <td>1-31</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00450.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 50</td>
      <td>1-33</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00451.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 51</td>
      <td>1-34</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00452.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 52</td>
      <td>1-49</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00453.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 53</td>
      <td>1-26</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00454.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 54</td>
      <td>1-82</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00455.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 55</td>
      <td>1-36</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00456.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 56</td>
      <td>1-31</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00457.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 57</td>
      <td>1-55</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00458.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 58</td>
      <td>1-35</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00459.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 59</td>
      <td>praef, 2, 3, 4, 6, 7, 9, 11, 13, 15, 16, 18, 19, 20, 21, 24, 25, 27, 28, 29, 31, 34, 36, 37, 38, 39, 40, 41, 42, 44, 45, 47, 49, 51, 52, 54, 57, 58, 60, 61, 63, 64, 65, 67, 68, 69, 70, 71, 72, 74, 75, 77, 78, 79, 81, 82, 84, 85, 86, 87, 88, 90, 91, 92, 93, 95, 96, 97, 98, 101, 102, 104, 105, 106, 107, 108, 109, 111, 112, 113, 114, 117, 119, 122, 125, 127, 128, 129, 130, 132, 133, 134, 136, 138, 139, 141, 145, 146, 147, 148, 149, 152, 154, 155, 156, 158, 162, 163, 164, 165, 167, 169, 170, 171, 172</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00460.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 60</td>
      <td>1-13</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00461.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 61</td>
      <td>1-20</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00462.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 62</td>
      <td>1-72</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00463.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 63</td>
      <td>1-42</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00464.opp-grc1</td>
      <td>Libanius</td>
      <td>Oratio 64</td>
      <td>1-118</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00501.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 1</td>
      <td>1-182</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00502.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 2</td>
      <td>1-36</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00503.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 3</td>
      <td>1-2_1-32</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00504.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 4</td>
      <td>praef, 3, 6, 7, 8, 9, 10, 11, 12, 15, 16, 19, 21, 22, 23, 24, 25, 26, 27, 28, 29, 31, 33, 34, 35, 40, 41, 43, 44, 45, 46, 47, 48, 49, 50, 52, 53, 54, 55, 57, 58, 59, 60, 62, 63, 65, 66, 68, 69, 71, 72, 74, 76, 77, 79, 80, 81, 82, 83, 85</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00505.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 5</td>
      <td>1-97</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00506.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 6</td>
      <td>1-2_1-60</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00507.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 7</td>
      <td>praef, 3, 5, 6, 9, 10, 11, 13, 14, 15, 16, 19, 20, 21, 22, 23</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00508.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 8</td>
      <td>1-31</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00509.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 9</td>
      <td>1-50</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00510.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 10</td>
      <td>1-42</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00511.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 11</td>
      <td>1-33</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00512.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 12</td>
      <td>1-54</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00513.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 13</td>
      <td>1-66</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00514.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 14</td>
      <td>1-39</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00515.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 15</td>
      <td>1-51</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00516.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 16</td>
      <td>1-66</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00517.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 17</td>
      <td>1-85</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00518.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 18</td>
      <td>1-36</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00519.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 19</td>
      <td>1-43</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00520.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 20</td>
      <td>1-33</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00521.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 21</td>
      <td>1-35</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00522.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 22</td>
      <td>1-35</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00523.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 23</td>
      <td>1-90</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00524.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 24</td>
      <td>1-2_1-28</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00525.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 25</td>
      <td>1-2_1-46</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00526.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 26</td>
      <td>1-55</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00527.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 27</td>
      <td>29-27</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00528.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 28</td>
      <td>1-26</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00529.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 29</td>
      <td>1-29</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00530.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 30</td>
      <td>1-69</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00531.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 31</td>
      <td>1-54</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00532.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 32</td>
      <td>1-54</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00533.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 33</td>
      <td>1-55</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00534.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 34</td>
      <td>1-3_1-73</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00535.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 35</td>
      <td>1-37</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00536.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 36</td>
      <td>1-56</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00537.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 37</td>
      <td>1-34</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00538.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 38</td>
      <td>1-47</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00539.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 39</td>
      <td>1-44</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00540.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 40</td>
      <td>1-2_1-84</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00541.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 41</td>
      <td>1-51</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00542.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 42</td>
      <td>1-57</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00543.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 43</td>
      <td>1-2_1-76</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00544.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 44</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00545.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 45</td>
      <td>1-2_1-28</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00546.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 46</td>
      <td>1-2_1-51</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00547.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 47</td>
      <td>1-61</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00548.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 48</td>
      <td>1-73</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00549.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 49</td>
      <td>1-2_1-97</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00550.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 50</td>
      <td>1-54</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg00551.opp-grc1</td>
      <td>Libanius</td>
      <td>Declamatio 51</td>
      <td>1-19</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2200.tlg008.1st1K-grc1</td>
      <td>Libanius</td>
      <td>Characteres Epistolici [Sp.]</td>
      <td>1-84</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2233.tlg001.1st1K-grc1</td>
      <td>Pseudo-Polemon</td>
      <td>Physiognomonica (Epitome Adamantiana)</td>
      <td>1-2_1-82</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg2233.tlg002.1st1K-grc1</td>
      <td>Pseudo-Polemon</td>
      <td>Physiognomonica</td>
      <td>70-86</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg2371.tlg001.1st1K-grc1</td>
      <td>Chronicon Paschale</td>
      <td>Chronicon Paschale</td>
      <td>1-2</td>
      <td>p7_1</td>
    </tr>
    <tr>
      <td>tlg2583.tlg001.1st1K-grc1</td>
      <td>Manetho Astrologus</td>
      <td>Apotelesmatica</td>
      <td>2-6_1-1_1-340</td>
      <td>p1_2</td>
    </tr>
    <tr>
      <td>tlg2586.tlg001.1st1K-grc1</td>
      <td>Menander Rhetor</td>
      <td>Διαίρεσις τῶν ἐπιδεικτικῶν</td>
      <td>1-3_1-2</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2586.tlg002.1st1K-grc1</td>
      <td>Menander Rhetor</td>
      <td>Περὶ ἐπιδεικτικῶν</td>
      <td>1-17_1-8</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2601.tlg001.1st1K-grc1</td>
      <td>Tiberius Rhetor</td>
      <td>De figuris Demosthenicis</td>
      <td>1-48</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2632.tlg001.1st1K-grc1</td>
      <td>Comarius</td>
      <td>De lapide philosophorum</td>
      <td>1-17</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2640.tlg001.1st1K-grc1</td>
      <td>Eusebius Myndius</td>
      <td>Fragmenta</td>
      <td>1-63</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2655.tlg002.1st1K-grc1</td>
      <td>Damigeron</td>
      <td>De lapidibus</td>
      <td>1-2_2-2_30-12_1-2</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg2691.tlg002.1st1K-grc1</td>
      <td>Musaeus, Eleusinius</td>
      <td>Fragmenta</td>
      <td>1-22</td>
      <td>m5_2</td>
    </tr>
    <tr>
      <td>tlg2703.tlg001.1st1K-grc1</td>
      <td>Anna Comnena</td>
      <td>Alexias</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15_1-11</td>
      <td>p12_1</td>
    </tr>
    <tr>
      <td>tlg2733.tlg001.1st1K-grc1</td>
      <td>Evagrius, Scholasticus</td>
      <td>Historia Ecclesiastica</td>
      <td>1-6_, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg2768.tlg001.1st1K-grc1</td>
      <td>Gelasius</td>
      <td>Historia Ecclesiastica</td>
      <td>1-3_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38_1-43</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg2806.tlg001.1st1K-grc1</td>
      <td>Marcus Diaconus</td>
      <td>Vita Porphyrii episcopi Gazensis</td>
      <td>1-3_1-20</td>
      <td>p3_2</td>
    </tr>
    <tr>
      <td>tlg2934.tlg066.perseus-grc2</td>
      <td>John of Damascus, Saint</td>
      <td>Vita Barlaam et Joasaph</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40_1-365</td>
      <td>p7_2</td>
    </tr>
    <tr>
      <td>tlg2948.tlg001.1st1K-grc1</td>
      <td>Acta Philippi</td>
      <td>Acta Philippi</td>
      <td>1-148</td>
      <td>p1_2/p2_1/p2_2</td>
    </tr>
    <tr>
      <td>tlg2949.tlg001.1st1K-grc1</td>
      <td>Acta Barnabae</td>
      <td>Acta Barnabae</td>
      <td>1-26</td>
      <td>p2_2/p3_1/p3_2</td>
    </tr>
    <tr>
      <td>tlg2959.tlg001.opp-grc1</td>
      <td>Methodius</td>
      <td>Symposium Sive Convivium Decem Virginum</td>
      <td>1-11_1-1</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2959.tlg002.opp-grc1</td>
      <td>Methodius</td>
      <td>De Libero Arbitrio</td>
      <td>1-22_1-11</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2959.tlg005.opp-grc1</td>
      <td>Methodius</td>
      <td>De Creatis (Fragmenta Ap. Photium, Bibl. Cod. 235)</td>
      <td>1-12_1-3</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2959.tlg006.opp-grc1</td>
      <td>Methodius</td>
      <td>Adversus Porphyrium (Fragmenta)</td>
      <td>1-5_1-1</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2959.tlg007.opp-grc1</td>
      <td>Methodius</td>
      <td>Fragmenta In Job (In Catenis)</td>
      <td>1-25</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2959.tlg008.opp-grc1</td>
      <td>Methodius</td>
      <td>De Martyribus (Fragmenta)</td>
      <td>1-2</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2959.tlg010.opp-grc1</td>
      <td>Methodius</td>
      <td>Fragmenta Incerta [Sp.]</td>
      <td>1-4</td>
      <td>p3_2/p4_1</td>
    </tr>
    <tr>
      <td>tlg2970.tlg001.1st1K-grc1</td>
      <td>Severus Philosophus</td>
      <td>Περὶ ψυχῆς (fragmentum)</td>
      <td>1-1</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg2972.tlg001.1st1K-grc1</td>
      <td>Anonymi de Terrae Motibus</td>
      <td>Anonymi Dissertatio De Terrae Motibus</td>
      <td>1-36</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg3118.tlg001.1st1K-grc1</td>
      <td>Syntipas</td>
      <td>Ιστορικον Συντιπα του Φιλοσοφου Ωραιοτατον Πανυ</td>
      <td>1-1_1-52</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg3118.tlg002.1st1K-grc1</td>
      <td>Syntipas</td>
      <td>Narrationes de Syntipa</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18</td>
      <td>p2_2</td>
    </tr>
    <tr>
      <td>tlg3129.ogl001.1st1K-grc1</td>
      <td>Theophylactus</td>
      <td>Commentary on St. Cyril In XII Prophetas</td>
      <td>1-1</td>
      <td>p9_1</td>
    </tr>
    <tr>
      <td>tlg3135.tlg001.1st1K-grc1</td>
      <td>Joannes Zonaras</td>
      <td>Epitome Historiarum</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18_1-29</td>
      <td>p11_2</td>
    </tr>
    <tr>
      <td>tlg3135.tlg011.1st1K-grc1</td>
      <td>Joannes Zonaras</td>
      <td>Argumenta</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18_1-29</td>
      <td>p11_2</td>
    </tr>
    <tr>
      <td>tlg3135.tlg012.1st1K-grc1</td>
      <td>Joannes Zonaras</td>
      <td>Chronologia</td>
      <td>1-1</td>
      <td>p11_2</td>
    </tr>
    <tr>
      <td>tlg3156.tlg001.1st1K-grc1</td>
      <td>Anonymi Exegesis in Hesiodi Theogoniam</td>
      <td>Exegesis in Hesiodi theogoniam</td>
      <td>praef, 23, 24, 35, 36, 56, 94, 116, 126, 134, 138, 154, 155, 159, 171, 173, 174, 178, 181, 188, 190, 194, 200, 201, 203, 206, 211, 214, 215, 220, 233, 235, 237, 238, 239, 240, 265, 270, 277, 287, 293, 295a, 304a, 306a, 313, 319a, 295b, 304b, 306b, 319b, 326, 333, 337, 346, 349, 371, 375, 383, 404, 409, 453, 458, 459, 463, 467, 481, 484, 485, 492, 506, 509, 510, 513, 514, 517, 521, 522, 523, 535, 562, 570, 617, 621, 624, 629, 639, 657, 687, 727, 732, 739, 775, 780, 787, 803, 811, 820, 836, 853, 881, 886, 891, 894, 901, 912, 915, 918, 924, 921</td>
      <td>p2_2/p3_1/p3_2/p4_1/p4_2/p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg4003.tlg001.1st1K-grc1</td>
      <td>Marcianus, of Heraclea</td>
      <td>Periplus maris exteri</td>
      <td>1-2_1-14_1-49</td>
      <td>p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg4003.tlg002.1st1K-grc1</td>
      <td>Marcianus, of Heraclea</td>
      <td>Menippi periplus maris interni (epitome Marciani)</td>
      <td>1-1_1-6_1-6</td>
      <td>p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg4003.tlg003.1st1K-grc1</td>
      <td>Marcianus, of Heraclea</td>
      <td>Artemidori Geographia (Epitome Marciani)</td>
      <td>1-3_1-11_1-22</td>
      <td>p5_1/p5_2</td>
    </tr>
    <tr>
      <td>tlg4013.tlg001.1st1K-grc1</td>
      <td>Simplicius</td>
      <td>In Aristotelis Quattuor Libros De Caelo Commentaria</td>
      <td>1-4</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4013.tlg003.1st1K-grc1</td>
      <td>Simplicius</td>
      <td>In Aristotelis Categorias Commentarium</td>
      <td>sigla, preface, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4013.tlg004.1st1K-grc1</td>
      <td>Simplicius</td>
      <td>In Aristotelis Physicorum Libros Commentaria</td>
      <td>1-8</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4013.tlg005.1st1K-grc1</td>
      <td>Simplicius</td>
      <td>In Aristotelis Libros De Anima Commentaria [Sp.?] (fort. auctore Prisciano Lydo)</td>
      <td>1-3</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4015.tlg001.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Aristotelis Categorias Commentarium</td>
      <td>1-1</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4015.tlg002.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Aristotelis Analytica Priora Commentaria</td>
      <td>1-5</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4015.tlg004.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Aristotelis Analytica Posteriora Commentaria</td>
      <td>1-2</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4015.tlg005.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Aristotelis Meteorologicorum Librum Primum Commentarium</td>
      <td>urn:cts:greekLit:tlg4015.tlg005.1st1K-grc1_1-1_introduction, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4015.tlg006.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Aristotelis Libros De Generatione Et Corruptione Commentaria</td>
      <td>1-2</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4015.tlg007.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Libros De Generatione Animalium Commentaria</td>
      <td>1-5</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4015.tlg008.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Aristotelis Libros De Anima Commentaria</td>
      <td>1-3</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4015.tlg009.1st1K-grc1</td>
      <td>John Philoponus</td>
      <td>In Aristotelis Physicorum Libros Commentaria</td>
      <td>1-13</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4016.tlg001.1st1K-grc1</td>
      <td>Ammonius</td>
      <td>In Porphyrii Isagogen Sive Quinque Voces</td>
      <td>urn:cts:greekLit:tlg4016.tlg001.1st1K-grc1_2-2_introduction, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4016.tlg002.1st1K-grc1</td>
      <td>Ammonius</td>
      <td>In Aristotelis Categorias Commentarius</td>
      <td>urn:cts:greekLit:tlg4016.tlg002.1st1K-grc1_1-1_1-11_introduction, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4016.tlg003.1st1K-grc1</td>
      <td>Ammonius</td>
      <td>In Aristotelis Librum De Interpretatione Commentarius</td>
      <td>1-1</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4016.tlg004.1st1K-grc1</td>
      <td>Ammonius</td>
      <td>In Aristotelis Analyticorum Priorum Librum I Commentarium</td>
      <td>1-27</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4016.tlg005.1st1K-grc1</td>
      <td>Ammonius</td>
      <td>In Aristotelis analytica priora [Sp.]</td>
      <td>226r, 226v, 227r, 227v, 228r, 228v, 229r, 229v, 230r, 230v, 231r, 231v, 232r, 232v, 233r, 233v, 234r, 234v, 235r, 235v, 236r, 236v, 237r, 237v, 238r, 238v, 239r, 239v, 240r, 240v, 241r, 241v, 242r, 242v, 243r, 243v, 244r, 244v, 245r, 245v, 246r, 246v, 247r, 247v, 248r, 248v, 249r, 249v, 250r, 250v, 251r, 251v, 252r, 252v, 253r, 253v, 254r, 254v, 255r, 255v, 256r, 256v, 257r, 257v, 258r, 258v, 259r, 259v, 260r, 260v, 261r, 261v</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4017.tlg001.1st1K-grc1</td>
      <td>Syrianus</td>
      <td>In Aristotelis Metaphysica Commentaria</td>
      <td>1-3</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg4018.tlg001.1st1K-grc1</td>
      <td>Asclepius</td>
      <td>In Aristotelis Metaphysicorum Libros A-Z Commentaria</td>
      <td>1-7</td>
      <td>p3_2/p4_1/p4_2/p5_1/p5_2/p6_1/p6_2</td>
    </tr>
    <tr>
      <td>tlg4019.tlg001.1st1K-grc1</td>
      <td>Olympiodorus</td>
      <td>Prolegomena</td>
      <td>1-1</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4019.tlg002.1st1K-grc1</td>
      <td>Olympiodorus</td>
      <td>In Categorias Commentarium</td>
      <td>1-1</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4019.tlg003.1st1K-grc1</td>
      <td>Olympiodorus</td>
      <td>In Aristotelis Meteora Commentaria</td>
      <td>1-4</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4020.tlg001.1st1K-grc1</td>
      <td>Elias Neoplatonicus</td>
      <td>In Porphyrii Isagogen</td>
      <td>1-3</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4020.tlg002.1st1K-grc1</td>
      <td>Elias Neoplatonicus</td>
      <td>Eliae (Olim Davidis) In Aristotelis Categorias Commentarium</td>
      <td>1-2</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4021.tlg001.1st1K-grc1</td>
      <td>David the Invincible</td>
      <td>Prolegomena philosophiae</td>
      <td>1-1</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4021.tlg002.1st1K-grc1</td>
      <td>David the Invincible</td>
      <td>In Porphyrii Isagogen Commentarium</td>
      <td>1-3</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4024.tlg001.1st1K-grc1</td>
      <td>Agathias Scholasticus</td>
      <td>Historiae</td>
      <td>1-5_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4024.tlg002.1st1K-grc2</td>
      <td>Agathias Scholasticus</td>
      <td>Epigrammata</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4026.tlg001.1st1K-grc1</td>
      <td>Anonymi in Aristotelis Artem Rhetoricam</td>
      <td>In Aristotelis artem rhetoricam commentarium</td>
      <td>1-3_2-19</td>
      <td>p7_2/p8_1/p8_2/p9_1/p9_2/p10_1/p10_2/p11_1/p11_2/p12_1/p12_2</td>
    </tr>
    <tr>
      <td>tlg4026.tlg002.1st1K-grc1</td>
      <td>Anonymi in Aristotelis Artem Rhetoricam</td>
      <td>Fragmentum commentarii in Aristotelis rhetorica</td>
      <td>15-16c</td>
      <td>p7_2/p8_1/p8_2/p9_1/p9_2/p10_1/p10_2/p11_1/p11_2/p12_1/p12_2</td>
    </tr>
    <tr>
      <td>tlg4026.tlg003.1st1K-grc1</td>
      <td>Anonymi in Aristotelis Artem Rhetoricam</td>
      <td>Fragmentum paraphrasis in Aristotelis rhetorica</td>
      <td>1-2</td>
      <td>p7_2/p8_1/p8_2/p9_1/p9_2/p10_1/p10_2/p11_1/p11_2/p12_1/p12_2</td>
    </tr>
    <tr>
      <td>tlg4027.tlg001.1st1K-grc1</td>
      <td>Anonymi In Aristotelis Categorias</td>
      <td>Paraphrasis Categoriarum</td>
      <td>urn:cts:greekLit:tlg4027.tlg001.1st1K-grc1, 1_preface, 1, 2, 3, 4, 5, 6, 7, 8</td>
      <td>p7_2/p8_1/p8_2/p9_1/p9_2/p10_1/p10_2/p11_1/p11_2/p12_1/p12_2</td>
    </tr>
    <tr>
      <td>tlg4029.tlg001.perseus-grc2</td>
      <td>Procopius</td>
      <td>De Bellis</td>
      <td>1-8_1-35_1-38</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4029.tlg002.perseus-grc2</td>
      <td>Procopius</td>
      <td>Historia Arcana</td>
      <td>1-30_1-34</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4030.tlg001.1st1K-grc1</td>
      <td>Sophonias</td>
      <td>In Aristotelis Libros De Anima Paraphrasis</td>
      <td>1-3_1-13</td>
      <td>p14_2</td>
    </tr>
    <tr>
      <td>tlg4031.tlg002.1st1K-grc1</td>
      <td>Eustratius</td>
      <td>In Aristotelis Ethica Nicomachea I Commentaria</td>
      <td>1-9</td>
      <td>p11_2</td>
    </tr>
    <tr>
      <td>tlg4033.tlg003.1st1K-grc1</td>
      <td>Anonymi In Aristotelis Ethica Nicomachea</td>
      <td>In Ethica Nicomachea Paraphrasis (Pseudepigraphum Olim A Constantino Palaeocappa confectum et olim sub auctore Heliodoro Prusensi vel Andronico Rhodio vel Olympiodoro)</td>
      <td>1-10</td>
      <td>p7_2/p8_1/p8_2/p9_1/p9_2/p10_1/p10_2/p11_1/p11_2/p12_1/p12_2</td>
    </tr>
    <tr>
      <td>tlg4034.tlg002.1st1K-grc1</td>
      <td>Michael of Ephesus</td>
      <td>In Parva Naturalia Commentaria</td>
      <td>1-6</td>
      <td>p12_2</td>
    </tr>
    <tr>
      <td>tlg4034.tlg003.1st1K-grc1</td>
      <td>Michael of Ephesus</td>
      <td>In Libros De Partibus Animalium Commentaria</td>
      <td>1-4</td>
      <td>p12_2</td>
    </tr>
    <tr>
      <td>tlg4034.tlg004.1st1K-grc1</td>
      <td>Michael of Ephesus</td>
      <td>In libros de animalium motione commentarium</td>
      <td>1-1</td>
      <td>p12_2</td>
    </tr>
    <tr>
      <td>tlg4034.tlg005.1st1K-grc1</td>
      <td>Michael of Ephesus</td>
      <td>In librum de animalium incessu commentarium</td>
      <td>1-1</td>
      <td>p12_2</td>
    </tr>
    <tr>
      <td>tlg4034.tlg006.1st1K-grc1</td>
      <td>Michael of Ephesus</td>
      <td>In Librum Quintum Ethicorum Nicomacheorum Commentarium</td>
      <td>1-1</td>
      <td>p12_2</td>
    </tr>
    <tr>
      <td>tlg4036.tlg001.opp-grc1</td>
      <td>Proclus</td>
      <td>In Platonis Rem Publicam Commentarii</td>
      <td>1-14</td>
      <td>p5_2</td>
    </tr>
    <tr>
      <td>tlg4036.tlg023.cypria-grc1</td>
      <td>Proclus</td>
      <td>Chrestomathy</td>
      <td>1-1</td>
      <td>p5_2</td>
    </tr>
    <tr>
      <td>tlg4037.tlg001.1st1K-grc1</td>
      <td>Anonymi Paradoxographi</td>
      <td>De Incredibilibus (excerpta Vaticana)</td>
      <td>1-23</td>
      <td>m1_1/m1_2/p1_2</td>
    </tr>
    <tr>
      <td>tlg4072.tlg001.1st1K-grc1</td>
      <td>Eutocius</td>
      <td>Commentarii in libros de sphaera et cylindro</td>
      <td>1-49</td>
      <td>p6_1/p6_2</td>
    </tr>
    <tr>
      <td>tlg4072.tlg002.1st1K-grc1</td>
      <td>Eutocius</td>
      <td>Commentarius in dimensionem circuli</td>
      <td>1-3_1-124</td>
      <td>p6_1/p6_2</td>
    </tr>
    <tr>
      <td>tlg4072.tlg003.1st1K-grc1</td>
      <td>Eutocius</td>
      <td>Commentarius in libros de planorum aequilibriis</td>
      <td>1-2_1-11</td>
      <td>p6_1/p6_2</td>
    </tr>
    <tr>
      <td>tlg4075.tlg002.1st1K-grc1</td>
      <td>Marinus, 5th century</td>
      <td>Commentarium in Euclidis data</td>
      <td>1-1</td>
      <td>p5_2</td>
    </tr>
    <tr>
      <td>tlg4081.tlg001.perseus-grc2</td>
      <td>Colluthus of Lycopolis</td>
      <td>The Rape of Helen</td>
      <td>1-394</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4084.tlg001.1st1K-grc1</td>
      <td>Zosimus</td>
      <td>Historia Nova</td>
      <td>1-6_1-13_1-2</td>
      <td>p6_1</td>
    </tr>
    <tr>
      <td>tlg4086.tlg001.1st1K-grc1</td>
      <td>Agathodaemon</td>
      <td>Fragmentum alchemicum</td>
      <td>1-1</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg4086.tlg002.1st1K-grc1</td>
      <td>Agathodaemon</td>
      <td>Ἀγαθοδαίμων εἰς τὸν χρησμὸν Ὀρφέως συναγωγὴ καὶ ὑπόμνημα</td>
      <td>1-8</td>
      <td>p4_1</td>
    </tr>
    <tr>
      <td>tlg4089.tlg003.1st1K-grc1</td>
      <td>Theodoretus</td>
      <td>Historia Ecclesiastica</td>
      <td>1-5_praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg4089.tlg004.1st1K-grc1</td>
      <td>Theodoretus</td>
      <td>Historia Religiosa</td>
      <td>prologos, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg4090.tlg001.1st1K-grc1</td>
      <td>Cyril of Alexandria</td>
      <td>In XII Prophetas</td>
      <td>hosea, joel, amos, obadiah, jonah, micah, nahum, habakkuk, zephaniah, haggai, zechariah, malachi_praefatio, 1, 2, 3, 4, 5, 6, 7_1-45</td>
      <td>p5_1</td>
    </tr>
    <tr>
      <td>tlg4091.tlg001.perseus-grc2</td>
      <td>Callistratus</td>
      <td>Descriptiones</td>
      <td>1-14</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg4102.tlg001.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Matthaeum (Catena Integra) (E Cod. Paris. Coislin. Gr. 23)</td>
      <td>toc, prologue, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg002.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Marcum (Recensio ii) (E Codd. Oxon. Bodl. Laud. 33 + Paris. Coislin. 23 + Paris. gr. 178)</td>
      <td>toc, hypothesis, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg003.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Supplementum et varietas lectionis ad commentarium Chrysostomi in evangelium sancti Matthaei (e cod. Oxon. Bodl. Auct. T.1.4)</td>
      <td>urn:cts:greekLit:tlg4102.tlg003.1st1K-grc1_3-3_5-243_13-4</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg004.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Lucam (Typus B) (e codd. Paris. Coislin. 23 + Oxon. Bodl. Misc. 182)</td>
      <td>toc, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg005.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Joannem (Catena Integra) (e codd. Paris. Coislin. 23 + Oxon. Bodl. Auct. T.1.4)</td>
      <td>toc, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg006.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Supplementum et varietas lectionis ad catenam in evangelium sancti Lucae (e cod. Oxon. Bodl. Laud. 33)</td>
      <td>urn:cts:greekLit:tlg4102.tlg006.1st1K-grc1_2-2_6-174_1-10</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg007.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Supplementum Et Varietas Lectionis Ad Catenam In Evangelium Sancti Joannis (e cod. Bodl. B.)</td>
      <td>urn:cts:greekLit:tlg4102.tlg007.1st1K-grc1_1-1_178-413_9-10</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg008.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Acta (Catena Andreae) (e cod. Oxon. coll. nov. 58)</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg010.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Romanos (Typus Vaticanus) (E Cod. Oxon. Bodl. Auct. E.2.20 [= Misc. 48])</td>
      <td>praef, toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg011.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Romanos (Typus Monacensis) (E Cod. Monac. gr. 412)</td>
      <td>7-16_7-24_verse, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg012.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam I Ad Corinthios (Typus Vaticanus) (e Cod. Paris. gr. 227)</td>
      <td>hyp, toc, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg013.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam II Ad Corinthios (Catena Pseudo-Oecumenii)</td>
      <td>praef, toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, sup1, sup2</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg019.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Galatas (Typus Parisinus) (E Cod. Coislin. 204)</td>
      <td>hyp, toc, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg020.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Ephesios (Typus Parisinus) (E Cod. Coislin. 204)</td>
      <td>hyp, toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg021.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Philippenses (Typus Parisinus) (e cod. Coislin. 204)</td>
      <td>hyp, toc, praef, 1, 2, 3, 4, 5, 6</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg022.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Colossenses (Typus Parisinus) (E Cod. Coislin. 204)</td>
      <td>hyp, toc, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg023.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam I Ad Thessalonicenses (Typus Parisinus)</td>
      <td>hyp, toc, 1, 2, 3, 4, 5, 6</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg024.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam II Ad Thessalonicenses (Typus Parisinus)</td>
      <td>hyp, toc, praef, 1, 2, 3, 4, 5, 6, 19</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg034.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam I Ad Timotheum (E Cod. Paris. Coislin. 204)</td>
      <td>pr, toc, 1, 2, 3, 4, 5, 6, 7, 9, 10, 11, 12, 13, 14, 15</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg035.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam II Ad Timotheum (E Cod. Paris. Coislin. 204)</td>
      <td>hyp, toc, praef, 1, 2, 3, 4, 5, 6, 7, 8, 9</td>
      <td>p6_2p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg036.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Titum (E Cod. Paris. Coislin. 204)</td>
      <td>hyp, toc, praef, 1, 2, 3, 4, 5, 6</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg037.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Philemonem (E Cod. Paris. Coislin. 204)</td>
      <td>hyp, toc, praef, 1, 2</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg038.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Ad Hebraeos (E Cod. Paris. Coislin. 204)</td>
      <td>hyp, toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, sup</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg040.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena In Epistulam Jacobi (Catena Andreae)</td>
      <td>hyp, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg041.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena in epistulam Petri i (catena Andreae) (e cod. Oxon. coll. nov. 58)</td>
      <td>praef, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg042.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena in epistulam Petri ii (catena Andreae) (e cod. Oxon. coll. nov. 58)</td>
      <td>hyp, 1, 2, 3, 4</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg043.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena in epistulam Joannis i (catena Andreae) (e cod. Oxon. coll. nov. 58)</td>
      <td>hyp, 1, 2, 3, 4, 5</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg044.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena in epistulam Joannis ii (catena Andreae) (e cod. Oxon. coll. nov. 58).</td>
      <td>hyp, 1, 2</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg045.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena in epistulam Joannis iii (catena Andreae) (e cod. Oxon. coll. nov. 58)</td>
      <td>hyp, 1, 2, 3</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlg046.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Catena in epistulam Juda (catena Andreae) (e cod. Oxon. coll. nov. 58)</td>
      <td>1-4_1-24</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlgX01.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Prooemium Pseudo-Oecumenii In Apocalypsin Commentarii (E Cod.)</td>
      <td>1-1</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlgX02.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Commentarius In Apocalypsin</td>
      <td>toc, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4102.tlgX03.1st1K-grc1</td>
      <td>Catenae (Novum Testamentum)</td>
      <td>Commentarius In Apocalypsin (Pseudo-Oecumenii) (E Cod. Coislin.)</td>
      <td>1-22_1-20</td>
      <td>p6_2</td>
    </tr>
    <tr>
      <td>tlg4170.tlg001a.1st1K-grc1</td>
      <td>Vitae Pindari et varia de Pindaro</td>
      <td>Vita Ambrosiana</td>
      <td>1-2</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg4170.tlg001b.1st1K-grc1</td>
      <td>Vitae Pindari et varia de Pindaro</td>
      <td>Vita Thomana et hypothesis Olympiorum</td>
      <td>1-1</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg4170.tlg001c.1st1K-grc1</td>
      <td>Vitae Pindari et varia de Pindaro</td>
      <td>Vita metrica</td>
      <td>1-1</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg4170.tlg001d.1st1K-grc1</td>
      <td>Vitae Pindari et varia de Pindaro</td>
      <td>Pentathlon et de novem lyricis</td>
      <td>1-2</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg4174.tlg001.1st1K-grc1</td>
      <td>Paraphrases in Dioynsium Periegetam</td>
      <td>Paraphrases in Dioynsium Periegetam</td>
      <td>1-112</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg4193.tlg012.1st1K-grc1</td>
      <td>Anonymi In Aristotelis Sophisticos Elenchos</td>
      <td>In Aristotelis Sophisticos Elenchos Paraphrasis</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34</td>
      <td>p7_2/p8_1/p8_2/p9_1/p9_2/p10_1/p10_2/p11_1/p11_2/p12_1/p12_2</td>
    </tr>
    <tr>
      <td>tlg5019.tlg001.1st1K-grc1</td>
      <td>Scholia in Dionysium Periegetam</td>
      <td>Scholia in Dionysii Byzantii per Bosporum navigationem (scholia vetera)</td>
      <td>vita, 1, 3, 5, 7, 10, 10a, 11, 11a, 12, 13, 14, 15, 17, 20, 21, 29, 30, 37, 38, 41, 43, 46, 47, 54, 55, 56, 60, 64, 66, 74, 75, 76, 78, 80, 81, 82, 83, 86, 89, 91, 92, 94, 97, 98, 100, 105, 106, 107, 109, 113, 116, 118, 120, 121, 122, 126, 128, 129, 130, 133, 135, 136, 138, 140, 142, 142a, 146, 148, 156, 157, 158, 160, 163, 166, 167, 168, 169, 173, 174, 175, 176, 180, 181, 183, 184, 186, 189, 192, 195, 200, 201, 205, 206, 210, 211, 213, 219, 221, 223, 226, 228, 230, 233, 237, 240, 242, 244, 249, 251, 253, 255, 259, 260, 262, 270, 271, 274, 275, 277, 280, 281, 283, 286, 287, 289, 290, 291, 293, 295, 297, 300, 301, 303, 304, 306, 309, 310, 311, 314, 316, 321, 322, 323, 327, 329, 331, 332, 337, 338, 341, 345, 348, 350, 355, 356, 358, 360, 361, 366, 369, 373, 375, 377, 377a, 381, 384, 386, 388, 389, 391, 399, 401, 406, 409, 411, 412, 414, 415, 416, 420, 425, 427, 431, 437, 441, 449, 450, 453, 454, 456, 458, 461, 465, 476, 482, 483, 484, 493, 496, 497, 498, 500, 504, 505, 506, 509, 510, 517, 520, 522, 523, 524, 525, 530, 533, 534, 536, 545, 560, 568, 576, 579, 582, 586, 592, 593, 594, 607, 609, 620, 626, 629, 651, 666, 672, 681, 685, 687, 699, 700, 714, 718, 724, 740, 745, 752, 772, 774, 775, 782, 791, 805, 820, 822, 825, 827, 850, 852, 870, 875, 907, 909, 910, 911, 912, 916, 923, 926, 946, 970, 988, 995, 1007, 1013, 1052, 1053, 1074, 1082, 1093, 1097, 1098, 1105, 1115, 1125, 1126, 1131, 1151, 1154, 1165</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg5019.tlg002.1st1K-grc1</td>
      <td>Scholia in Dionysium Periegetam</td>
      <td>Scholia in Dionysii Periegetae orbis descriptionem (scholia vetera)</td>
      <td>vita, 1, 2, 3, 4, 5, 6, 7, 8, 10, 11, 12, 13, 14, 15, 17, 18, 19, 20, 22, 23, 29, 32, 33, 38, 39, 43, 46, 47, 51, 54, 55, 56, 65, 67</td>
      <td>p2_1</td>
    </tr>
    <tr>
      <td>tlg5022.tlg002.1st1K-grc1</td>
      <td>Scholia in Euclidem</td>
      <td>Scholia in Euclidis Data</td>
      <td>scholia, appendix_1-15</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg5022.tlg003.1st1K-grc1</td>
      <td>Scholia in Euclidem</td>
      <td>Scholia in Euclidis optica (scholia vetera)</td>
      <td>1-89</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg5022.tlg004.1st1K-grc1</td>
      <td>Scholia in Euclidem</td>
      <td>Scholia in opticorum recensionem Theonis (scholia vetera)</td>
      <td>1-92</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg5022.tlg005.1st1K-grc1</td>
      <td>Scholia in Euclidem</td>
      <td>Scholia in Euclidis catoptrica (scholia vetera)</td>
      <td>1-58</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg5022.tlg006.1st1K-grc1</td>
      <td>Scholia in Euclidem</td>
      <td>Scholia in Euclidis phaenomena</td>
      <td>pr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18_1-130</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg5022.tlg007.1st1K-grc1</td>
      <td>Scholia in Euclidem</td>
      <td>Scholia in Euclidis data et catoptrica</td>
      <td>1-1</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg001.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Scholia in Euripidem (scholia vetera)</td>
      <td>vita, arg, sch, _1-Tr_1-1325</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg010.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Vitae Euripidis</td>
      <td>1-5</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg011.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Scholia in Euripidis Rhesum</td>
      <td>1-2_1-895</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg012.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Scholia in Euripidis Troiades</td>
      <td>1-2_1-1325</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg013.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Scholia in Euripidis Hippolytum</td>
      <td>1-2_1-1464</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg014.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Scholia in Euripidis Hecubam (scholia vetera et scholia recentiora Thomae Magistri, Triclinii, Moschopuli et anonyma)</td>
      <td>1-3_1-1243</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg015.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Scholia in Euripidis Orestem (scholia vetera et scholia recentiora Thomae Magistri, Triclinii, Moschopuli et anonyma)</td>
      <td>arg, sch_1-1691_1-3</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5023.tlg016.1st1K-grc1</td>
      <td>Scholia in Euripidem</td>
      <td>Scholia in Euripidis Phoenissas (scholia vetera et scholia recentiora Thomae Magistri, Triclinii, Moschopuli et anonyma)</td>
      <td>arg, sch_1-1764_1-1</td>
      <td>m1_2</td>
    </tr>
    <tr>
      <td>tlg5026.tlg001.1st1K-grc1</td>
      <td>Scholia in Homerum</td>
      <td>Scholia in Iliadem</td>
      <td>1-6a_1-24_1-61</td>
      <td>m2_2/m1_1/m1_2/p1_2</td>
    </tr>
    <tr>
      <td>tlg5026.tlg007.1st1K-grc1</td>
      <td>Scholia in Homerum</td>
      <td>Scholia in Odysseam</td>
      <td>1-2_epigraph, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24_pr, 1, 2, 3, 4</td>
      <td>m2_2/m1_1/m1_2/p1_2</td>
    </tr>
    <tr>
      <td>tlg5029.tlg001.1st1K-grc1</td>
      <td>Scholia in Lucianum</td>
      <td>Scholia in Lucianum</td>
      <td>epigr, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 77, 78, 79, 80_1-15</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg5031.tlg001.1st1K-grc1</td>
      <td>Scholia in Nicandrum</td>
      <td>Scholia et glossae in Nicandri theriaca (scholia vetera et recentiora)</td>
      <td>0, 1, 2, 3, 5, 6, 7, 8, 9, 11, 13, 15, 18, 20, 22, 23, 24, 25, 27, 28, 29, 30, 32, 33, 35, 37, 39, 40, 41, 42, 43, 44, 45, 50, 52, 53, 57, 59, 60a, 60b, 62, 63, 64, 65a, 65b, 66, 67, 70, 71, 73, 74, 75, 76, 78, 79, 81, 83, 84, 85, 86, 88, 89, 90, 91, 92, 93, 94, 96, 97, 98, 102, 103, 104, 105, 106, 109, 107, 114, 115, 118, 119, 120, 121, 123, 125, 126, 127, 128, 129, 130, 131a, 131b, 132, 134, 135, 137, 139, 141, 143, 145, 147a, 146, 147b, 148, 149, 150, 151, 152, 153, 154, 156, 157, 158, 159, 160, 161, 165, 166, 170, 169, 171, 172, 174, 175, 176, 177, 179a, 180a, 179b, 180c, 183, 184, 187, 188, 189, 190, 192, 194, 195, 196, 199, 200, 201, 202, 203, 206, 208, 209, 212, 213, 214, 215, 219, 220, 223, 224, 226a, 226b, 227, 228, 229, 230, 231, 233, 234, 237, 240, 241a, 241b, 246, 247, 249, 252, 253, 254, 256, 257, 258, 260, 261, 263, 264, 266, 267, 268, 270, 272, 273, 275, 276, 278, 281, 284, 286a, 286b, 288, 289, 290, 291, 292, 293, 294, 295, 296, 297, 300, 302, 303, 306, 307, 308, 309, 310, 312, 313, 316, 317, 320, 322a, 322b, 324, 325, 329, 332, 334, 336, 338, 341, 343, 347, 348, 349, 351, 354, 355, 357, 359, 360, 361, 362a, 362b, 366, 367, 368a, 368b, 371, 372, 373, 374, 375, 376, 377, 380, 382, 383, 386, 387, 389, 393, 394, 396a, 396b, 398, 399, 400, 401, 405, 406, 409, 410, 411, 413, 416, 417, 420, 421, 422, 423, 424, 425, 427, 429, 430, 431, 432, 433, 434, 436, 437, 438, 441, 443, 444, 446, 447, 448, 450, 452, 456, 457, 458, 459, 460, 462, 463, 465, 470, 471, 472, 473, 475, 476, 477, 478, 482, 484a, 484b, 486, 484c, 490, 491, 493, 494, 495, 497, 498, 499, 500, 503, 505, 509a, 513, 509b, 510, 511, 512, 516, 519, 520a, 521, 517, 526, 527, 520b, 533, 534, 535, 536, 537, 538, 539, 541, 543, 5444, 547, 549, 551, 552, 553, 554, 556, 557, 559, 560, 561a, 561b, 564, 565, 566, 567, 568, 569, 571, 574, 575, 576, 577, 578, 579, 581, 582, 583, 584, 585, 586, 590, 591, 593, 594, 595, 596, 597, 600, 601, 603, 604, 605, 606, 607, 610, 612, 613, 614, 615a, 615b, 617, 618, 619, 620, 622, 623, 624, 625, 628a, 628b, 629, 630, 631, 632, 633a, 633b, 634a, 634b, 635, 637, 638, 640, 642, 643, 644, 645, 647, 648, 649, 650, 651, 653, 655, 656, 657, 658, 660, 662, 661, 666, 668, 671, 672a, 669, 672b, 673, 676, 677, 678, 680, 681, 683, 684, 685, 686, 687, 689, 690, 691a, 691b, 692, 694a, 694b, 695, 696, 697, 698, 700, 701, 703, 705, 706, 707, 708, 709, 713, 714, 715, 717, 718, 719, 721, 725, 727, 729, 733, 734, 737, 738, 742, 744, 745, 747, 748, 750, 751, 752, 753, 755, 758, 759, 760, 761, 762, 763, 764, 767, 769, 771, 774, 775, 776, 781, 782, 783, 784, 785, 786, 788, 790, 791, 792, 793, 795, 796, 797, 799, 802, 804, 805, 809, 812, 813, 814, 816, 817, 818, 820, 821, 822, 823, 824, 825, 828, 831, 830, 837, 838, 840, 845, 846, 848, 849, 850, 851, 853, 854, 855, 856, 857, 858, 860, 862, 863, 864, 867, 868, 869a, 869b, 870, 871, 872, 873, 875, 876, 877, 880, 881a, 882, 883, 885a, 885b, 881b, 887, 890, 892a, 892b, 895, 897, 898, 899, 901, 902, 903, 907, 908a, 908b, 909, 911, 912, 915, 916, 918, 920, 921, 923, 925, 928, 932, 933, 934, 936, 937, 938, 941, 945, 947, 950, 951, 953, 955, 957, 958</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg5031.tlg002.1st1K-grc1</td>
      <td>Scholia in Nicandrum</td>
      <td>Scholia et glossae in Nicandri alexipharmaca (scholia vetera et recentiora)</td>
      <td>0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 11, 13, 14, 15, 16, 19, 21, 22, 24, 27, 30, 31, 32, 34, 35, 36, 37, 38, 40, 41, 42, 43, 44, 46, 47, 48, 50, 55, 57, 59, 62, 64, 65, 66, 67, 69, 74, 77, 78, 79, 81, 82, 84, 85, 87, 91, 93, 95, 99, 101, 103, 106, 107, 108, 109, 111, 115, 119, 123, 124, 126, 128, 130, 132, 134, 135, 137, 139, 142, 145, 146, 147, 149, 150, 151, 153, 155, 157, 158, 160, 161, 163, 164, 165, 171, 172, 174, 175, 176, 177, 178, 180, 181, 182, 183, 185, 186, 189, 191, 192, 193, 194, 197, 198, 201, 202, 203, 204, 205, 206, 207, 208, 211, 213, 214, 215, 217, 218, 220, 221, 222, 224, 225, 226, 229, 230, 231, 232, 233, 234, 235, 236, 237, 239, 241, 242, 244, 248, 249, 252, 253, 254, 255, 256, 257, 260, 261, 263, 264, 266, 267, 268, 269, 270, 271, 273, 274, 275, 279, 280, 282, 285, 287, 288, 291, 292, 293, 294, 295, 297, 298, 299, 301, 305, 307, 308, 310, 312, 314, 315, 316, 318, 319, 320, 322, 323, 328, 329, 332, 335, 337, 339, 341, 342, 345, 347, 351, 352, 353, 354, 356, 358, 360, 364, 366, 368, 369, 370, 371, 373, 374, 375, 376, 377, 378, 382, 387, 389, 390, 393, 394, 396, 398, 399, 400, 402, 403, 404, 405, 406, 407, 408, 409, 410, 415, 416, 418, 417, 420, 421, 424, 426, 428, 429, 432, 433, 434, 435, 436, 437, 438, 439, 443, 444, 445, 446, 448, 449, 450, 451, 452, 455, 456, 457, 458, 459, 460, 462, 463, 464, 465, 466, 468, 469, 470, 471, 473, 474, 475, 476, 478, 479, 481, 483, 484, 485, 486, 488, 490, 493, 494, 495, 497, 498, 501, 505, 506, 507, 509, 510, 511, 512, 513, 514, 515, 516, 517, 518, 519, 521, 522, 524, 525, 526, 527, 528, 529, 530, 531, 532, 533, 534, 535, 536, 537, 540, 543, 544, 545, 547, 548, 550, 552, 555, 556, 557, 558, 559, 560, 562, 563, 567, 568, 569, 570, 575, 577, 578, 580, 581, 582, 583, 584, 586, 587, 588, 589, 590, 594, 596, 597, 599, 600, 601, 602, 604, 605, 607, 609, 610, 611, 612, 613, 616, 618, 621, 622, 624, 625, 627, 628, 629</td>
      <td>m2_1</td>
    </tr>
    <tr>
      <td>tlg5034.tlg001a.perseus-grc1</td>
      <td>Scholia in Pindarum</td>
      <td>Scholia in Pindarum Olympian Odes</td>
      <td>1-14_0, 1, 4, 5, 8, 9, 10, 13, 14, 15, 16, 17, 18, 19, 20, 24, 26, 28, 29, 32, 33, 34, 35, 36, 37, 38, 40, 41, 42, 43, 44, 47, 48, 50, 51, 53, 55, 58, 59, 62, 64, 66, 67, 68, 69, 71, 72, 75, 77, 79, 80, 84, 85, 87, 89, 91, 95, 96, 97, 105, 106, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 122, 126, 127, 129, 131, 134, 135, 137, 139, 142, 143, 144, 145, 146, 148, 149, 150, 151, 154, 157, 158, 159, 164, 165, 169, 171, 173, 174, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 3, 7, 11, 12, 21, 22, 23, 25, 27, 31, 39, 45, 52, 56, 60, 61, 65, 70, 73, 76, 78, 81, 82, 90, 92, 93, 98, 99, 100, 101, 102, 104, 107, 108, 121, 123, 124, 128, 130, 132, 138, 140, 147, 152, 153, 160, 161, 162, 163, 166, 168, 175, 176, 177, 178, 6, 30, 46, 54, 74, 57, 86, 88, 103, 120, 141, 156, 167, 170, 49, 63, 83, 172, 94, 2, 125, 133, 136, 155_metr, hyp, insc, a, b, c, d, e, f, g, h, i, x, dX, j, k, xx, X, cc, bb, l, m, n, o, aa, 61, 68, 69</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg5034.tlg001b.perseus-grc1</td>
      <td>Scholia in Pindarum</td>
      <td>Scholia in Pindarum Pythian Odes</td>
      <td>1-12_1-54</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg5034.tlg001c.perseus-grc1</td>
      <td>Scholia in Pindarum</td>
      <td>Scholia in Pindarum Nemean Odes</td>
      <td>1-11_1-62</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg5034.tlg001d.perseus-grc1</td>
      <td>Scholia in Pindarum</td>
      <td>Scholia in Pindarum Isthmian Odes</td>
      <td>1-8_1-133</td>
      <td>m3_1/m3_2/m2_1/m2_2/m1_1</td>
    </tr>
    <tr>
      <td>tlg5037.tlg004.1st1K-grc1</td>
      <td>Scholia in Sophoclem</td>
      <td>Scholia in Sophoclem (scholia vetera)</td>
      <td>1-7_1-1774</td>
      <td>p4_2</td>
    </tr>
    <tr>
      <td>tlg9004.tlg001.opp-grc1</td>
      <td>Anonymi In Aristotelis Librum Alterum Analyticorum Posteriorum</td>
      <td>Anonymi In Analyticorum Posteriorum Librum Alterum Commentarium</td>
      <td>1-150</td>
      <td>p12_1/p12_2</td>
    </tr>
    <tr>
      <td>tlg9006.tlg001.1st1K-grc1</td>
      <td>Gregory II, of Cyprus, Patriarch of Constantinople</td>
      <td>Paroemiae</td>
      <td>1-3b_1-5</td>
      <td>p13_2</td>
    </tr>
    <tr>
      <td>tlg9006.tlg016.1st1K-grc1</td>
      <td>Gregory II, of Cyprus, Patriarch of Constantinople</td>
      <td>Declamatio de Atheniensium defensio (ad Libanii declamationem antilogia)</td>
      <td>1-51</td>
      <td>p13_2</td>
    </tr>
    <tr>
      <td>tlg9007.tlg001.1st1K-grc1</td>
      <td>Appendix Proverbiorum</td>
      <td>Appendix Proverbiorum</td>
      <td>1-5_1-43</td>
      <td>p13_2</td>
    </tr>
    <tr>
      <td>tlg9010.tlg001.1st1K-grc1</td>
      <td>Suda</td>
      <td>Suidae lexicon</td>
      <td>1-4_A, B, Γ, Δ, Aι, E, Κ, Λ, Μ, Ν, Ξ, Ο255, Ω, Π, Ρ, Σ, Τ_1a, 1b, 2, 3, 4, 5, 6, 7, 8, 9, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56, 57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75, 76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94, 95, 96, 97, 98, 99, 100, 101, 102, 103, 104, 105, 106, 107, 108, 109, 110, 111, 112, 113, 114, 115, 116, 117, 118, 119, 120, 121, 122, 123, 124, 125, 126, 127, 128, 129, 130, 131, 132, 133, 134, 135, 136, 137, 138, 139, 141, 142, 143, 144, 145, 146, 147, 148, 149, 150, 151, 152, 153, 154, 155, 156, 157, 158, 159, 160, 161, 162, 163, 164, 165, 166, 167, 168, 169, 170, 171, 172, 173, 174, 175, 176, 177, 178, 179, 180, 181, 182, 183, 184, 185, 186, 187, 188, 189, 190, 191, 192, 193, 194, 195, 196, 197, 198, 199, 200, 201, 202, 203, 204, 205, 206, 207, 208, 209, 210, 211, 212, 213, 214, 215, 216, 217, 218, 219, 220, 221, 222, 223, 224, 225, 226, 227, 228, 229, 230, 231, 232, 233, 234, 235, 236, 237, 238, 239, 240, 241, 242, 243, 244, 245, 246, 247, 248, 249, 250, 251, 252, 253, 254, 255, 256, 257, 258, 259, 260, 261, 262, 263, 264, 265, 266, 267, 268, 269, 270, 271, 272, 273, 274, 275, 276, 277, 278, 279, 280, 281, 282, 283, 284, 285, 286, 287, 288, 289, 290, 291, 292, 293, 294, 295, 296, 297, 298, 299, 300, 301, 302, 303, 304, 305, 306, 307, 308, 309, 310, 311, 312, 313, 314, 315, 316, 317, 318, 319, 320, 321, 322, 323, 324, 325, 326, 327, 328, 329, 330, 331, 332, 333, 334, 335, 336, 337, 338, 339, 340, 341, 342, 343, 344, 345, 346, 347, 348, 349, 350, 351, 352, 353, 354, 355, 356, 357, 358, 359, 360, 361, 362, 363, 364, 365, 366, 367, 368, 369, 370, 371, 372, 373, 374, 375, 376, 377, 378, 379, 380, 381, 382, 383, 384, 385, 386, 387, 388, 389, 390, 391, 392, 393, 394, 395, 396, 397, 398, 399, 400, 401, 402, 403, 404, 405, 406, 407, 408, 409, 410, 411, 412, 413, 414, 415, 416, 417, 418, 419, 420, 421, 422, 423, 424, 425, 426, 427, 428, 429, 430, 431, 432, 433, 434, 435, 436, 437, 438, 439, 440, 441, 442, 443, 444, 445, 446, 447, 448, 449, 450, 451, 452, 453, 454, 455, 456, 457, 458, 459, 460, 461, 462, 463, 464, 465, 466, 467, 468, 469, 470, 471, 472, 473, 474, 475, 476, 477, 478, 479, 480, 481, 482, 483, 484, 485, 486, 487, 488, 489, 490, 491, 492, 493, 494, 495, 496, 497, 498, 499, 500, 501, 502, 503, 504, 505, 506, 507, 508, 509, 510, 511, 512, 513, 514, 515, 516, 517, 518, 519, 520, 521, 522, 523, 524, 525, 526, 527, 528, 529, 530, 531, 532, 533, 534, 535, 536, 537, 538, 539, 540, 541, 542, 543, 544, 545, 546, 547, 548, 549, 550, 551, 552, 553, 554, 555, 556, 557, 558, 559, 560, 561, 562, 563, 564, 565, 566, 567, 568, 569, 570, 571, 572, 573, 574, 575, 576, 577, 578, 579, 580, 581, 582, 583, 584, 585, 586, 587, 588, 589, 590, 591, 592, 593, 594, 595, 596, 597, 598, 599, 600, 601, 602, 603, 604, 605, 606, 607, 608, 609, 610, 611, 612, 613, 614, 615, 616, 617, 618, 619, 620, 621, 622, 623, 624, 625, 626, 627, 628, 629, 630, 631, 632, 633, 634, 635, 636, 637, 638, 639, 640, 641, 642, 643, 644, 645, 646, 647, 648, 649, 650, 651, 652, 653, 654, 655, 656, 657, 658, 659, 660, 661, 662, 663, 664, 665, 666, 667, 668, 669, 670, 671, 672, 673, 674, 675, 676, 677, 678, 679, 680, 681, 682, 683, 684, 685, 686, 687, 688, 689, 690, 691, 692, 693, 694, 695, 696, 697, 698, 699, 700, 701, 702, 703, 704, 705, 706, 707, 708, 709, 710, 711, 712, 713, 714, 715, 716, 717, 718, 719, 720, 721, 722, 723, 724, 725, 726, 727, 728, 729, 730, 731, 732, 733, 734, 735, 736, 737, 738, 739, 740, 741, 742, 743, 744, 745, 746, 747, 748, 749, 750, 751, 752, 753, 754, 755, 756, 757, 758, 759, 760, 761, 762, 763, 764, 765, 766, 767, 768, 769, 770, 771, 772, 773, 774, 775, 776, 777, 778, 779, 780, 781, 782, 783, 784, 785, 786, 787, 788, 789, 790, 791, 792, 793, 794, 795, 796, 797, 798, 799, 800, 801, 802, 803, 804, 805, 806, 807, 808, 809, 810, 811, 812, 813, 814, 815, 816, 817, 818, 819, 820, 821, 822, 823, 824, 825, 826, 827, 828, 829, 830, 831, 832, 833, 834, 835, 836, 837, 838, 839, 840, 841, 842, 843, 844, 845, 846, 847, 848, 849, 850, 851, 852, 853, 854, 855, 856, 857, 858, 859, 860, 861, 862, 863, 864, 865, 866, 867, 868, 869, 870, 871, 872, 873, 874, 875, 876, 877, 878, 879, 880, 881, 882, 883, 884, 885, 886, 887, 888, 889, 890, 891, 892, 893, 894, 895, 896, 897, 898, 899, 900, 901, 902, 903, 904, 905, 906, 907, 908, 909, 910, 911, 912, 913, 914, 915, 916, 917, 918, 919, 920, 921, 922, 923, 924, 925, 926, 927, 928, 929, 930, 931, 932, 933, 934, 935, 936, 937, 938, 939, 940, 941, 942, 943, 944, 945, 946, 947, 948, 949, 950, 951, 952, 953, 954, 955, 956, 957, 958, 959, 960, 961, 962, 963, 964, 965, 966, 967, 968, 969, 970, 971, 972, 973, 974, 975, 976, 977, 978, 979, 980, 981, 982, 983, 984, 985, 986, 987, 988, 989, 990, 991, 992, 993, 994, 995, 996, 997, 998, 999, 1000, 1001, 1002, 1003, 1004, 1005, 1006, 1007, 1008, 1009, 1010, 1011, 1012, 1013, 1014, 1015, 1016, 1017, 1018, 1019, 1020, 1021, 1022, 1023, 1024, 1025, 1026, 1027, 1028, 1029, 1030, 1031, 1032, 1033, 1034, 1035, 1036, 1037, 1038, 1039, 1040, 1041, 1042, 1043, 1044, 1045, 1046, 1047, 1048, 1049, 1050, 1051, 1052, 1053, 1054, 1055, 1056, 1057, 1058, 1059, 1060, 1061, 1062, 1063, 1064, 1065, 1066, 1067, 1068, 1069, 1070, 1071, 1072, 1073, 1074, 1075, 1076, 1077, 1078, 1079, 1080, 1081, 1082, 1083, 1084, 1085, 1086, 1087, 1088, 1089, 1090, 1091, 1092, 1093, 1094, 1095, 1096, 1097, 1098, 1099, 1100, 1101, 1102, 1103, 1104, 1105, 1106, 1107, 1108, 1109, 1110, 1111, 1112, 1113, 1114, 1115, 1116, 1117, 1118, 1119, 1120, 1121, 1122, 1123, 1124, 1125, 1126, 1127, 1128, 1129, 1130, 1131, 1132, 1133, 1134, 1135, 1136, 1137, 1138, 1139, 1140, 1141, 1142, 1143, 1144, 1145, 1146, 1147, 1148, 1149, 1150, 1151, 1152, 1153, 1154, 1155, 1156, 1157, 1158, 1159, 1160, 1161, 1162, 1163, 1164, 1165, 1166, 1167, 1168, 1169, 1170, 1171, 1172, 1173, 1174, 1175, 1176, 1177, 1178, 1179, 1180, 1181, 1182, 1183, 1184, 1185, 1186, 1187, 1188, 1189, 1190, 1191, 1192, 1193, 1194, 1195, 1196, 1197, 1198, 1199, 1200, 1201, 1202, 1203, 1204, 1205, 1206, 1207, 1208, 1209, 1210, 1211, 1212, 1213, 1214, 1215, 1216, 1217, 1218, 1219, 1220, 1221, 1222, 1223, 1224, 1225, 1226, 1227, 1228, 1229, 1230, 1231, 1232, 1233, 1234, 1235, 1236, 1237, 1238, 1239, 1241, 1242, 1243, 1244, 1245, 1246, 1247, 1248, 1249, 1250, 1251, 1252, 1253, 1254, 1255, 1256, 1257, 1258, 1259, 1260, 1261, 1262, 1263, 1264, 1265, 1266, 1267, 1268, 1269, 1270, 1271, 1272, 1273, 1274, 1275, 1276, 1277, 1278, 1279, 1280, 1281, 1282, 1283, 1284, 1285, 1286, 1287, 1288, 1289, 1290, 1291, 1292, 1293, 1294, 1295, 1296, 1297, 1298, 1299, 1300, 1301, 1302, 1303, 1304, 1305, 1306, 1307, 1308, 1309, 1310, 1311, 1312, 1313, 1314, 1315, 1316, 1317, 1318, 1319, 1320, 1321, 1322, 1323, 1324, 1325, 1326, 1327, 1328, 1329, 1330, 1331, 1332, 1333, 1334, 1335, 1336, 1337, 1338, 1339, 1340, 1341, 1342, 1343, 1344, 1345, 1346, 1347, 1348, 1349, 1350, 1351, 1352, 1353, 1354, 1355, 1356, 1357, 1358, 1359, 1360, 1361, 1362, 1363, 1364, 1365, 1366, 1367, 1368, 1369, 1370, 1371, 1372, 1373, 1374, 1375, 1376, 1377, 1378, 1379, 1380, 1381, 1382, 1383, 1384, 1385, 1386, 1387, 1388, 1389, 1390, 1391, 1392, 1393, 1394, 1395, 1396, 1397, 1398, 1399, 1400, 1401, 1402, 1403, 1404, 1405, 1406, 1407, 1408, 1409, 1410, 1411, 1412, 1413, 1414, 1415, 1416, 1417, 1418, 1419, 1420, 1421, 1422, 1423, 1424, 1425, 1426, 1427, 1428, 1429, 1430, 1431, 1432, 1433, 1434, 1435, 1436, 1437, 1438, 1439, 1440, 1441, 1442, 1443, 1444, 1445, 1446, 1447, 1448, 1449, 1450, 1451, 1452, 1453, 1454, 1455, 1456, 1457, 1458, 1459, 1460, 1461, 1462, 1463, 1464, 1465, 1466, 1467, 1468, 1469, 1470, 1471, 1472, 1473, 1474, 1475, 1476, 1477, 1478, 1479, 1480, 1481, 1482, 1483, 1484, 1485, 1486, 1487, 1488, 1489, 1490, 1491, 1492, 1493, 1494, 1495, 1496, 1497, 1498, 1499, 1500, 1501, 1502, 1503, 1504, 1505, 1506, 1507, 1508, 1509, 1510, 1511, 1512, 1513, 1514, 1515, 1516, 1517, 1518, 1519, 1520, 1521, 1522, 1523, 1524, 1525, 1526, 1527, 1528, 1529, 1530, 1531, 1532, 1533, 1534, 1535, 1536, 1537, 1538, 1539, 1540, 1541, 1542, 1543, 1544, 1545, 1546, 1547, 1548, 1549, 1550, 1551, 1552, 1553, 1554, 1555, 1556, 1557, 1558, 1559, 1560, 1561, 1562, 1563, 1564, 1565, 1566, 1567, 1568, 1569, 1570, 140, 1572, 1573, 1574, 1575, 1576, 1577, 1578, 1579, 1580, 1581, 1582, 1583, 1584, 1585, 1586, 1587, 1588, 1589, 1590, 1591, 1592, 1593, 1594, 1595, 1596, 1597, 1598, 1599, 1600, 1601, 1602, 1603, 1604, 1605, 1606, 1607, 1608, 1609, 1610, 1611, 1612, 1613, 1614, 1615, 1616, 1617, 1618, 1619, 1620, 1621, 1622, 1623, 1624, 1625, 1626, 1627, 1628, 1629, 1630, 1631, 1632, 1633, 1634, 1635, 1636, 1637, 1638, 1639, 1640, 1641, 1642, 1643, 1644, 1645, 1646, 1647, 1648, 1649, 1650, 1651, 1652, 1653, 1654, 1655, 1656, 1657, 1658, 1659, 1660, 1661, 1662, 1663, 1664, 1665, 1666, 1667, 1668, 1669, 1670, 1671, 1672, 1673, 1674, 1675, 1676, 1677, 1678, 1679, 1680, 1681, 1682, 1683, 1684, 1685, 1686, 1687, 1688, 1689, 1690, 1691, 1692, 1693, 1694, 1695, 1696, 1697, 1698, 1699, 1700, 1701, 1702, 1703, 1704, 1705, 1706, 1707, 1708, 1709, 1710, 1711, 1712, 1713, 1714, 1715, 1716, 1717, 1718, 1719, 1720, 1721, 1722, 1723, 1724, 1725, 1726, 1727, 1728, 1729, 1730, 1731, 1732, 1733, 1734, 1735, 1736, 1737, 1738, 1739, 1740, 1741, 1742, 1743, 1744, 1745, 1746, 1747, 1748, 1749, 1750, 1751, 1752, 1753, 1754, 1755, 1756, 1757, 1758, 1759, 1760, 1761, 1762, 1763, 1764, 1765, 1766, 1767, 1768, 1769, 1770, 1771, 1772, 1773, 1774, 1775, 1776, 1777, 1778, 1779, 1780, 1781, 1782, 1783, 1784, 1785, 1786, 1787, 1788, 1789, 1790, 1791, 1792, 1793, 1794, 1795, 1796, 1797, 1798, 1799, 1800, 1801, 1802, 1803, 1804, 1805, 1806, 1807, 1808, 1809, 1810, 1811, 1812, 1813, 1814, 1815, 1816, 1817, 1818, 1819, 1820, 1821, 1822, 1823, 1824, 1825, 1826, 1827, 1828, 1829, 1830, 1831, 1832, 1833, 1834, 1835, 1836, 1837, 1838, 1839, 1840, 1841, 1842, 1843, 1844, 1845, 1846, 1847, 1848, 1849, 1850, 1851, 1852, 1853, 1854, 1855, 1856, 1857, 1858, 1859, 1860, 1861, 1862, 1863, 1864, 1865, 1866, 1867, 1868, 1869, 1870, 1871, 1872, 1873, 1874, 1875, 1876, 1877, 1878, 1879, 1880, 1881, 1882, 1883, 1884, 1885, 1886, 1887, 1888, 1889, 1890, 1891, 1892, 1893, 1894, 1895, 1896, 1897, 1898, 1899, 1900, 1901, 1902, 1903, 1904, 1905, 1906, 1907, 1908, 1909, 1910, 1911, 1912, 1913, 1914, 1915, 1916, 1917, 1918, 1919, 1920, 1921, 1922, 1923, 1924, 1925, 1926, 1927, 1928, 1929, 1930, 1931, 1932, 1933, 1934, 1935, 1936, 1937, 1938, 1939, 1940, 1941, 1942, 1943, 1944, 1945, 1946, 1947, 1948, 1949, 1950, 1951, 1952, 1953, 1954, 1955, 1956, 1957, 1958, 1959, 1960, 1961, 1962, 1963, 1964, 1965, 1966, 1967, 1968, 1969, 1970, 1971, 1972, 1973, 1974, 1975, 1976, 1977, 1978, 1979, 1980, 1981, 1982, 1983, 1984, 1985, 1986, 1987, 1988, 1989, 1990, 1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023, 2024, 2025, 2026, 2027, 2028, 2029, 2030, 2031, 2032, 2033, 2034, 2035, 2036, 2037, 2038, 2039, 2040, 2041, 2042, 2043, 2044, 2045, 2046, 2047, 2048, 2049, 2050, 2051, 2052, 2053, 2054, 2055, 2056, 2057, 2058, 2059, 2060, 2061, 2062, 2063, 2064, 2065, 2066, 2067, 2068, 2069, 2070, 2071, 2072, 2073, 2074, 2075, 2076, 2077, 2078, 2079, 2080, 2081, 2082, 2083, 2084, 2085, 2086, 2087, 2088, 2089, 2090, 2091, 2092, 2093, 2094, 2095, 2096, 2097, 2098, 2099, 2100, 2101, 2102, 2103, 2104, 2105, 2106, 2107, 2108, 2109, 2110, 2111, 2112, 2113, 2114, 2115, 2116, 2117, 2118, 2119, 2120, 2121, 2122, 2123, 2124, 2125, 2126, 2127, 2128, 2129, 2130, 2131, 2132, 2133, 2134, 2135, 2136, 2137, 2138, 2139, 2140, 2141, 2142, 2143, 2144, 2145, 2146, 2147, 2148, 2149, 2150, 2151, 2152, 2153, 2154, 2155, 2156, 2157, 2158, 2159, 2160, 2161, 2162, 2163, 2164, 2165, 2166, 2167, 2168, 2169, 2170, 2171, 2172, 2173, 2174, 2175, 2176, 2177, 2178, 2179, 2180, 2181, 2182, 2183, 2184, 2185, 2186, 2187, 2188, 2189, 2190, 2191, 2192, 2193, 2194, 2195, 2196, 2197, 2198, 2199, 2200, 2201, 2202, 2203, 2204, 2205, 2206, 2207, 2208, 2209, 2210, 2211, 2212, 2213, 2214, 2215, 2216, 2217, 2218, 2219, 2220, 2221, 2222, 2223, 2224, 2225, 2226, 2227, 2228, 2229, 2230, 2231, 2232, 2233, 2234, 2235, 2236, 2237, 2238, 2239, 2240, 2241, 2242, 2243, 2244, 2245, 2246, 2247, 2248, 2249, 2250, 2251, 2252, 2253, 2254, 2255, 2256, 2257, 2258, 2259, 2260, 2261, 2262, 2263, 2264, 2265, 2266, 2267, 2268, 2269, 2270, 2271, 2272, 2273, 2274, 2275, 2276, 2277, 2278, 2279, 2280, 2281, 2282, 2283, 2284, 2285, 2286, 2287, 2288, 2289, 2290, 2291, 2292, 2293, 2294, 2295, 2296, 2297, 2298, 2299, 2300, 2301, 2302, 2303, 2304, 2305, 2306, 2307, 2308, 2309, 2310, 2311, 2312, 2313, 2314, 2315, 2316, 2317, 2318, 2319, 2320, 2321, 2322, 2323, 2324, 2325, 2326, 2327, 2328, 2329, 2330, 2331, 2332, 2333, 2334, 2335, 2336, 2337, 2338, 2340, 2341, 2342, 2343, 2344, 2345, 2346, 2347, 2348, 2349, 2350, 2351, 2352, 2353, 2354, 2355, 2356, 2357, 2358, 2359, 2360, 2361, 2362, 2363, 2364, 2365, 2366, 2367, 2368, 2369, 2370, 2371, 2372, 2373, 2374, 2375, 2376, 2377, 2378, 2379, 2380, 2381, 2382, 2383, 2384, 2385, 2386, 2387, 2388, 2389, 2390, 2391, 2392, 2393, 2394, 2395, 2396, 2397, 2398, 2399, 2400, 2401, 2402, 2403, 2404, 2405, 2406, 2407, 2408, 2409, 2410, 2411, 2412, 2413, 2414, 2415, 2416, 2417, 2418, 2419, 2420, 2421, 2422, 2423, 2424, 2425, 2426, 2427, 2428, 2429, 2430, 2431, 2432, 2433, 2434, 2435, 2436, 2437, 2438, 2439, 2440, 2441, 2442, 2443, 2444, 2445, 2446, 2447, 2448, 2449, 2450, 2451, 2452, 2453, 2454, 2455, 2456, 2457, 2458, 2459, 2460, 2461, 2462, 2463, 2464, 2465, 2466, 2467, 2468, 2469, 2470, 2471, 2472, 2473, 2474, 2475, 2476, 2477, 2478, 2479, 2480, 2481, 2482, 2483, 2484, 2485, 2486, 2487, 2488, 2489, 2490, 2491, 2492, 2493, 2494, 2495, 2496, 2497, 2498, 2499, 2500, 2501, 2502, 2503, 2504, 2505, 2506, 2507, 2508, 2509, 2510, 2511, 2512, 2513, 2514, 2515, 2516, 2517, 2518, 2519, 2520, 2521, 2522, 2523, 2524, 2525, 2526, 2527, 2528, 2529, 2530, 2531, 2532, 2533, 2534, 2535, 2536, 2537, 2538, 2539, 2540, 2541, 2542, 2543, 2544, 2545, 2546, 2547, 2548, 2549, 2550, 2551, 2552, 2553, 2554, 2555, 2556, 2557, 2558, 2559, 2560, 2561, 2562, 2563, 2564, 2565, 2566, 2567, 2568, 2569, 2570, 2571, 2572, 2573, 2574, 2575, 2576, 2577, 2578, 2579, 2580, 2581, 2582, 2583, 2584, 2585, 2586, 2587, 2588, 2589, 2590, 2591, 2592, 2593, 2594, 2595, 2596, 2597, 2598, 2599, 2600, 2601, 2602, 2603, 2604, 2605, 2606, 2607, 2608, 2609, 2610, 2611, 2612, 2613, 2614, 2615, 2616, 2617, 2618, 2619, 2620, 2621, 2622, 2623, 2624, 2625, 2626, 2627, 2628, 2629, 2630, 2631, 2632, 2633, 2634, 2635, 2636, 2637, 2638, 2639, 2640, 2641, 2642, 2643, 2644, 2645, 2646, 2647, 2648, 2649, 2650, 2651, 2652, 2653, 2654, 2655, 2656, 2657, 2658, 2659, 2660, 2661, 2662, 2663, 2664, 2665, 2666, 2667, 2668, 2669, 2670, 2671, 2672, 2673, 2674, 2675, 2676, 2677, 2678, 2679, 2680, 2681, 2682, 2683, 2684, 2685, 2686, 2687, 2688, 2689, 2690, 2691, 2692, 2693, 2694, 2695, 2696, 2697, 2698, 2699, 2700, 2701, 2702, 2703, 2704, 2705, 2706, 2707, 2708, 2709, 2710, 2711, 2712, 2713, 2714, 2715, 2716, 2717, 2718, 2719, 2720, 2721, 2722, 2723, 2724, 2725, 2726, 2727, 2728, 2729, 2730, 2731, 2732, 2733, 2734, 2735, 2736, 2737, 2738, 2739, 2740, 2741, 2742, 2743, 2744, 2745, 2746, 2747, 2748, 2749, 2750, 2751, 2752, 2753, 2754, 2755, 2756, 2757, 2758, 2759, 2760, 2761, 2762, 2763, 2764, 2765, 2766, 2767, 2768, 2769, 2770, 2771, 2772, 2773, 2774, 2775, 2776, 2777, 2778, 2779, 2780, 2781, 2782, 2783, 2784, 2785, 2786, 2787, 2788, 2789, 2790, 2791, 2792, 2793, 2794, 2795, 2796, 2797, 2798, 2799, 2800, 2801, 2802, 2803, 2804, 2805, 2806, 2807, 2808, 2809, 2810, 2811, 2812, 2813, 2814, 2815, 2816, 2817, 2818, 2819, 2820, 2821, 2822, 2823, 2824, 2825, 2826, 2827, 2828, 2829, 2830, 2831, 2832, 2833, 2834, 2835, 2836, 2837, 2838, 2839, 2840, 2841, 2842, 2843, 2844, 2845, 2846, 2847, 2848, 2849, 2850, 2851, 2852, 2853, 2854, 2855, 2856, 2857, 2858, 2859, 2860, 2861, 2862, 2863, 2864, 2865, 2866, 2867, 2868, 2869, 2870, 2871, 2872, 2873, 2874, 2875, 2876, 2877, 2878, 2879, 2880, 2881, 2882, 2883, 2884, 2885, 2886, 2887, 2888, 2889, 2890, 2891, 2892, 2893, 2894, 2895, 2896, 2897, 2898, 2899, 2900, 2901, 2902, 2903, 2904, 2905, 2906, 2907, 2908, 2909, 2910, 2911, 2912, 2913, 2914, 2915, 2916, 2917, 2918, 2919, 2920, 2921, 2922, 2923, 2924, 2925, 2926, 2927, 2928, 2929, 2930, 2931, 2932, 2933, 2934, 2935, 2936, 2937, 2938, 2939, 2940, 2941, 2942, 2943, 2944, 2945, 2946, 2947, 2948, 2949, 2950, 2951, 2952, 2953, 2954, 2955, 2956, 2957, 2958, 2959, 2960, 2961, 2962, 2963, 2964, 2965, 2966, 2967, 2968, 2969, 2970, 2971, 2972, 2973, 2974, 2975, 2976, 2977, 2978, 2979, 2980, 2981, 2982, 2983, 2984, 2985, 2986, 2987, 2988, 2989, 2990, 2991, 2992, 2993, 2994, 2995, 2996, 2997, 2998, 2999, 3000, 3001, 3002, 3003, 3004, 3005, 3006, 3007, 3008, 3009, 3010, 3011, 3012, 3013, 3014, 3015, 3016, 3017, 3018, 3019, 3020, 3021, 3022, 3023, 3024, 3025, 3026, 3027, 3028, 3029, 3030, 3031, 3032, 3033, 3034, 3035, 3036, 3037, 3038, 3039, 3040, 3041, 3042, 3043, 3044, 3045, 3046, 3047, 3048, 3049, 3050, 3051, 3052, 3053, 3054, 3055, 3056, 3057, 3058, 3059, 3060, 3061, 3062, 3063, 3064, 3065, 3066, 3067, 3068, 3069, 3070, 3071, 3072, 3073, 3074, 3075, 3076, 3077, 3078, 3079, 3080, 3081, 3082, 3083, 3084, 3085, 3086, 3087, 3088, 3089, 3090, 3091, 3092, 3093, 3094, 3095, 3096, 3097, 3098, 3099, 3100, 3101, 3102, 3103, 3104, 3105, 3106, 3107, 3108, 3109, 3110, 3111, 3112, 3113, 3114, 3115, 3116, 3117, 3118, 3119, 3120, 3121, 3122, 3123, 3124, 3125, 3126, 3127, 3128, 3129, 3130, 3131, 3132, 3133, 3134, 3135, 3136, 3137, 3138, 3139, 3140, 3141, 3142, 3143, 3144, 3145, 3146, 3147, 3148, 3149, 3150, 3151, 3152, 3153, 3154, 3155, 3156, 3157, 3158, 3159, 3160, 3161, 3162, 3163, 3164, 3165, 3166, 3167, 3168, 3169, 3170, 3171, 3172, 3173, 3174, 3175, 3176, 3177, 3178, 3179, 3180, 3181, 3182, 3183, 3184, 3185, 3186, 3187, 3188, 3189, 3190, 3191, 3192, 3193, 3194, 3195, 3196, 3197, 3198, 3199, 3200, 3201, 3202, 3203, 3204, 3205, 3206, 3207, 3208, 3209, 3210, 3211, 3212, 3213, 3214, 3215, 3216, 3217, 3218, 3219, 3220, 3221, 3222, 3223, 3224, 3225, 3226, 3227, 3228, 3229, 3230, 3231, 3232, 3233, 3234, 3235, 3236, 3237, 3238, 3239, 3240, 3241, 3242, 3243, 3244, 3245, 3246, 3247, 3248, 3249, 3250, 3251, 3252, 3253, 3254, 3255, 3256, 3257, 3258, 3259, 3260, 3261, 3262, 3263, 3264, 3265, 3266, 3267, 3268, 3269, 3270, 3271, 3272, 3273, 3274, 3275, 3276, 3277, 3278, 3279, 3280, 3281, 3282, 3283, 3284, 3285, 3286, 3287, 3288, 3289, 3290, 3291, 3292, 3293, 3294, 3295, 3296, 3297, 3298, 3299, 3300, 3301, 3302, 3303, 3304, 3305, 3306, 3307, 3308, 3309, 3310, 3311, 3312, 3313, 3314, 3315, 3316, 3317, 3318, 3319, 3320, 3321, 3322, 3323, 3324, 3325, 3326, 3327, 3328, 3329, 3330, 3331, 3332, 3333, 3334, 3335, 3336, 3337, 3338, 3339, 3340, 3341, 3342, 3343, 3344, 3345, 3346, 3347, 3348, 3349, 3350, 3351, 3352, 3353, 3354, 3355, 3356, 3357, 3358, 3359, 3360, 3361, 3362, 3363, 3364, 3365, 3366, 3367, 3368, 3369, 3370, 3371, 3372, 3373, 3374, 3375, 3376, 3377, 3378, 3379, 3380, 3381, 3382, 3383, 3384, 3385, 3386, 3387, 3388, 3389, 3390, 3391, 3392, 3393, 3394, 3395, 3396, 3397, 3398, 3399, 3400, 3401, 3402, 3403, 3404, 3405, 3406, 3407, 3408, 3409, 3410, 3411, 3412, 3413, 3414, 3415, 3416, 3417, 3418, 3419, 3420, 3421, 3422, 3423, 3424, 3425, 3426, 3427, 3428, 3429, 3430, 3431, 3432, 3433, 3434, 3435, 3436, 3437, 3438, 3439, 3440, 3441, 3442, 3443, 3444, 3445, 3446, 3447, 3448, 3449, 3450, 3451, 3452, 3453, 3454, 3455, 3456, 3457, 3458, 3459, 3460, 3461, 3462, 3463, 3464, 3465, 3466, 3467, 3468, 3469, 3470, 3471, 3472, 3473, 3474, 3475, 3476, 3477, 3478, 3479, 3480, 3481, 3482, 3483, 3484, 3485, 3486, 3487, 3488, 3489, 3490, 3491, 3492, 3493, 3494, 3495, 3496, 3497, 3498, 3499, 3500, 3501, 3502, 3503, 3504, 3505, 3506, 3507, 3508, 3509, 3510, 3511, 3512, 3513, 3514, 3515, 3516, 3517, 3518, 3519, 3520, 3521, 3522, 3523, 3524, 3525, 3526, 3527, 3528, 3529, 3530, 3531, 3532, 3533, 3534, 3535, 3536, 3537, 3538, 3539, 3540, 3541, 3542, 3543, 3544, 3545, 3546, 3547, 3548, 3549, 3550, 3551, 3552, 3553, 3554, 3555, 3556, 3557, 3558, 3559, 3560, 3561, 3562, 3563, 3564, 3565, 3566, 3567, 3568, 3569, 3570, 3571, 3572, 3573, 3574, 3575, 3576, 3577, 3578, 3579, 3580, 3581, 3582, 3583, 3584, 3585, 3586, 3587, 3588, 3589, 3590, 3591, 3592, 3593, 3594, 3595, 3596, 3597, 3598, 3599, 3600, 3601, 3602, 3603, 3604, 3605, 3606, 3607, 3608, 3609, 3610, 3611, 3612, 3613, 3614, 3615, 3616, 3617, 3618, 3619, 3620, 3621, 3622, 3623, 3624, 3625, 3626, 3627, 3628, 3629, 3630, 3631, 3632, 3633, 3634, 3635, 3636, 3637, 3638, 3639, 3640, 3641, 3642, 3643, 3644, 3645, 3646, 3647, 3648, 3649, 3650, 3651, 3652, 3653, 3654, 3655, 3656, 3657, 3658, 3659, 3660, 3661, 3662, 3663, 3664, 3665, 3666, 3667, 3668, 3669, 3670, 3671, 3672, 3673, 3674, 3675, 3676, 3677, 3678, 3679, 3680, 3681, 3682, 3683, 3684, 3685, 3686, 3687, 3688, 3689, 3690, 3691, 3692, 3693, 3694, 3695, 3696, 3697, 3698, 3699, 3700, 3701, 3702, 3703, 3704, 3705, 3706, 3707, 3708, 3709, 3710, 3711, 3712, 3713, 3714, 3715, 3716, 3717, 3718, 3719, 3721, 3722, 3723, 3724, 3725, 3726, 3727, 3728, 3729, 3730, 3731, 3732, 3734, 3735, 3736, 3737, 3738, 3739, 3740, 3741, 3742, 3743, 3744, 3745, 3746, 3747, 3748, 3749, 3750, 3751, 3752, 3753, 3754, 3755, 3756, 3757, 3758, 3759, 3760, 3761, 3762, 3763, 3764, 3765, 3766, 3767, 3768, 3769, 3770, 3771, 3772, 3773, 3774, 3775, 3776, 3777, 3778, 3779, 3780, 3781, 3782, 3783, 3784, 3785, 3786, 3787, 3788, 3789, 3790, 3791, 3792, 3793, 3794, 3795, 3796, 3797, 3798, 3799, 3800, 3801, 3802, 3803, 3804, 3805, 3806, 3807, 3808, 3809, 3810, 3811, 3812, 3813, 3814, 3815, 3816, 3817, 3818, 3819, 3820, 3821, 3822, 3823, 3824, 3825, 3826, 3827, 3828, 3829, 3830, 3831, 3832, 3833, 3834, 3835, 3836, 3837, 3838, 3839, 3840, 3841, 3842, 3843, 3844, 3845, 3846, 3847, 3848, 3849, 3850, 3851, 3852, 3853, 3855, 3856, 3857, 3858, 3859, 3860, 3861, 3862, 3863, 3864, 3865, 3866, 3867, 3868, 3869, 3870, 3871, 3872, 3873, 3874, 3876, 3877, 3878, 3879, 3880, 3881, 3882, 3883, 3884, 3885, 3886, 3887, 3888, 3889, 3890, 3891, 3892, 3893, 3894, 3895, 3896, 3897, 3898, 3899, 3900, 3901, 3902, 3903, 3904, 3905, 3906, 3907, 3908, 3909, 3910, 3911, 3912, 3913, 3914, 3915, 3916, 3917, 3918, 3919, 3920, 3921, 3922, 3923, 3924, 3925, 3926, 3927, 3928, 3929, 3930, 3931, 3932, 3933, 3934, 3935, 3936, 3937, 3938, 3939, 3940, 3941, 3942, 3943, 3944, 3945, 3946, 3947, 3948, 3949, 3950, 3951, 3952, 3953, 3954, 3955, 3956, 3957, 3958, 3959, 3960, 3961, 3962, 3963, 3964, 3965, 3966, 3967, 3968, 3969, 3970, 3971, 3972, 3973, 3974, 3975, 3976, 3977, 3978, 3979, 3980, 3981, 3982, 3983, 3984, 3985, 3986, 3987, 3988, 3989, 3990, 3991, 3992, 3993, 3994, 3995, 3996, 3997, 3998, 3999, 4000, 4001, 4002, 4003, 4004, 4005, 4006, 4007, 4008, 4009, 4010, 4011, 4012, 4013, 4014, 4015, 4016, 4017, 4018, 4019, 4020, 4021, 4022, 4023, 4024, 4025, 4026, 4027, 4028, 4029, 4030, 4031, 4032, 4033, 4034, 4035, 4036, 4037, 4038, 4039, 4040, 4041, 4042, 4043, 4044, 4045, 4046, 4047, 4048, 4049, 4050, 4051, 4052, 4053, 4054, 4055, 4056, 4057, 4058, 4059, 4060, 4061, 4062, 4063, 4064, 4065, 4066, 4067, 4068, 4069, 4070, 4071, 4072, 4073, 4074, 4075, 4076, 4077, 4078, 4079, 4080, 4081, 4082, 4083, 4084, 4085, 4086, 4087, 4088, 4089, 4090, 4091, 4092, 4093, 4094, 4095, 4096, 4097, 4098, 4099, 4100, 4101, 4102, 4103, 4104, 4105, 4106, 4107, 4108, 4109, 4110, 4111, 4112, 4113, 4114, 4115, 4116, 4117, 4118, 4119, 4120, 4121, 4122, 4123, 4124, 4125, 4126, 4127, 4128, 4129, 4130, 4131, 4132, 4133, 4134, 4135, 4136, 4137, 4138, 4139, 4140, 4141, 4142, 4143, 4144, 4145, 4146, 4147, 4148, 4149, 4150, 4151, 4152, 4153, 4154, 4155, 4156, 4157, 4158, 4159, 4160, 4161, 4162, 4163, 4164, 4165, 4166, 4167, 4168, 4169, 4170, 4171, 4172, 4173, 4174, 4175, 4176, 4177, 4178, 4179, 4180, 4181, 4182, 4183, 4184, 4185, 4186, 4187, 4188, 4189, 4190, 4191, 4192, 4193, 4194, 4195, 4196, 4197, 4198, 4199, 4200, 4201, 4202, 4203, 4204, 4205, 4206, 4207, 4208, 4209, 4210, 4211, 4212, 4213, 4214, 4215, 4216, 4217, 4218, 4219, 4220, 4221, 4222, 4223, 4224, 4225, 4226, 4227, 4228, 4229, 4230, 4231, 4232, 4233, 4234, 4235, 4236, 4237, 4238, 4239, 4240, 4241, 4242, 4243, 4244, 4245, 4246, 4247, 4248, 4249, 4250, 4251, 4252, 4253, 4254, 4255, 4256, 4257, 4258, 4259, 4260, 4261, 4262, 4263, 4264, 4265, 4266, 4267, 4268, 4270, 4271, 4272, 4273, 4274, 4275, 4276, 4277, 4278, 4279, 4280, 4281, 4282, 4283, 4284, 4285, 4286, 4287, 4288, 4289, 4290, 4291, 4292, 4293, 4294, 4295, 4296, 4297, 4298, 4299, 4300, 4301, 4302, 4303, 4304, 4305, 4306, 4307, 4308, 4309, 4310, 4311, 4312, 4313, 4314, 4315, 4316, 4317, 4318, 4319, 4320, 4321, 4322, 4323, 4324, 4325, 4326, 4327, 4328, 4329, 4330, 4331, 4332, 4333, 4334, 4335, 4336, 4337, 4338, 4339, 4340, 4341, 4342, 4343, 4344, 4345, 4346, 4347, 4348, 4349, 4350, 4351, 4352, 4353, 4354, 4355, 4356, 4357, 4358, 4359, 4360, 4361, 4362, 4363, 4364, 4366, 4367, 4368, 4369, 4370, 4371, 4372, 4373, 4374, 4375, 4376, 4377, 4378, 4379, 4380, 4381, 4382, 4383, 4384, 4385, 4386, 4388, 4389, 4390, 4391, 4392, 4393, 4394, 4396, 4397, 4398, 4399, 4400, 4401, 4402, 4403, 4404, 4405, 4406, 4407, 4408, 4409, 4410, 4411, 4412, 4413, 4414, 4415, 4416, 4417, 4418, 4419, 4420, 4421, 4422, 4423, 4424, 4425, 4426, 4428, 4429, 4430, 4431, 4432, 4433, 4434, 4435, 4436, 4437, 4438, 4439, 4440, 4441, 4442, 4443, 4444, 4445, 4446, 4447, 4448, 4449, 4450, 4451, 4452, 4453, 4454, 4455, 4456, 4457, 4458, 4459, 4460, 4461, 4462, 4463, 4464, 4465, 4466, 4467, 4468, 4469, 4470, 4471, 4472, 4473, 4474, 4475, 4476, 4477, 4478, 4479, 4480, 4481, 4482, 4483, 4484, 4485, 4486, 4487, 4488, 4489, 4490, 4491, 4492, 4493, 4494, 4495, 4496, 4497, 4498, 4499, 4500, 4501, 4502, 4503, 4504, 4505, 4506, 4507, 4508, 4509, 4510, 4511, 4512, 4513, 4514, 4515, 4516, 4517, 4518, 4519, 4520, 4521, 4522, 4523, 4524, 4525, 4526, 4527, 4528, 4529, 4530, 4531, 4533, 4534, 4535, 4536, 4537, 4538, 4539, 4540, 4541, 4542, 4543, 4544, 4545, 4546, 4547, 4548, 4549, 4550, 4551, 4552, 4553, 4554, 4555, 4556, 4557, 4558, 4559, 4560, 4561, 4562, 4563, 4564, 4565, 4566, 4567, 4568, 4569, 4570, 4571, 4572, 4573, 4574, 4575, 4576, 4577, 4578, 4579, 4580, 4581, 4582, 4583, 4584, 4585, 4586, 4587, 4588, 4589, 4590, 4591, 4592, 4593, 4594, 4595, 4596, 4597, 4598, 4599, 4600, 4601, 4602, 4603, 4604, 4605, 4606, 4607, 4608, 4609, 4610, 4611, 4612, 4613, 4614, 4615, 4616, 4617, 4618, 4619, 4620, 4621, 4622, 4623, 4624, 4625, 4626, 4627, 4628, 4629, 4630, 4631, 4632, 4633, 4634, 4635, 4636, 4637, 4638, 4639, 4640, 4641, 4642, 4643, 4644, 4645, 4646, 4647, 4648, 4649, 4650, 4651, 4652, 4653, 4654, 4655, 4656, 4657, 4658, 4659, 4660, 4661, 4662, 4663, 4664, 4665, 4666, 4667, 4668, 4669, 4670, 4671, 4672, 4673, 4674, 4675, 4676, 4677, 4678, 4679, 4680, 4681, 4682, 4683, 4684, 4685, 4686, 4687, 4688, 4689, 4690, 4691, 4692, 4693, 4694, 4695, 4696, 4697, 4698, 4699, 4700, 4701, 4702, 4703, 4704, 4705, 4706, 4707, 4708, 4709, 4710, 4711, 4712, 4713, 4714, 4715, 4716, 4717, 4718, 4719, 4720, 4721, 4722, 4723, 4724, 4725, 4726, 4727, 4728, 4729, 4730, 4731, 4732, 4733, 4734, 4735, 4736, 4737, 4738, 4739, 4740, 1, 10, 5763, 1240, 1571, 1071b, 11117, 11118, 1970b, 2339, 27454, 433a, 1205Τ, 3077a, 667b</td>
      <td>p10_2</td>
    </tr>
    <tr>
      <td>tlg9019.tlg001.1st1K-grc1</td>
      <td>Stephanus of Alexandria</td>
      <td>In Aristotelis Librum De Interpretatione Commentarium</td>
      <td>1-2</td>
      <td>p7_1</td>
    </tr>
  </tbody>
</table>
