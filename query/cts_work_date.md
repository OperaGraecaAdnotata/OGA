# CTS and Work Date Annotation

The [table](./table_keys_values.md) shows the values for the keys:

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
in the [table](./table_keys_values.md)).

## CTS URN

The metadata concerning CTS URNs (including author names and work titles)
were retrieved automatically from the
texts. This means that their values may contain
inconsistencies and errors, which can also be identified
in the [table](./table_keys_values.md).

The field `cts` refers to a passage inside a work. In the
[table](./table_keys_values.md), the column `cts` tries to provide
a summary of all admissible values: for example, `1-2_1-8` means
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
Euripides' Cyclops has the date `-0411-01/-0405-12`, which was converted
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
