# Query the Corpus

The annotations in OGA can be queried using the original PAULA XML files 
or ANNIS 4. 
In either case, one must know the labels used to encode annotations
(for example, "v" stands for verbs and "n" for nouns). The files in this
folder document all of them.

# ANNIS 4

Annis query language is documented 
on https://korpling.github.io/ANNIS/4/user-guide/aql/index.html. 
What is important to undestand for querying in ANNIS 4
is that there are two
kinds of annotation which two kinds of syntax correspond to: 
the annotation associated with single tokens (*token-based*) and 
the annotation associated with all tokens of a texts (*text-based*, 
known also as metadata field). For example, the field `author`
is the same for all tokens of a text and therefore is a metadata field. 

In ANNIS 4, metadata fields are introduced by the operator `@*` 
and more metadata fields
are joined by "\_ident\_". On the contrary, 
annotations associated with single tokens are simply
searched using key/value pairs, such as `token="ἀθηναῖος"` or 
`lemma="ἀθηναῖος"` (see query examples below for more clarification).

The following table lists all the possible search keys (to know their possible
values, check the other files in this directory):

|type of annotation|syntax|comment|
|-----|-----|-----|
|token-based|`token="Ἀθηναῖος"`|this is a word form|
|token-based|`lemma="ἀθηναῖος"`|lemmas are lowercased in OGA v0.2.0|
|token-based|`pos="v"`|part of speech|
|token-based|`person="2"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`number="s"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`tense="p"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`mood="i"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`voice="a"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`gender="m"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`case="n"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`degree="m"`|morphological feature; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/morphology.md">values</a>|
|token-based|`cts="1_2"`|CTS structure for passage; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md">values</a>|
|token-based|`ipa01="/an.drá.si/"`| experimental IPA transcription (5th BCE Attic pronunciation)|
|text-based|`@* urn_cts="tlg0010.tlg001.perseus-grc2"`| this identifies an author, work and edition; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md"></a>|
|text-based|`@* urn_cts_author="tlg0010"`| this identifies an author; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md"></a>|
|text-based|`@* urn_cts_work="tlg001"`| this identifies a work; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md"></a>|
|text-based|`@* urn_cts_edition="tlg001"`| this identifies an edition; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md"></a>|
|text-based|`@* author="tlg0010"`| this identifies an author; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md"></a>|
|text-based|`@* title="tlg001"`| this identifies a work; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md"></a>|
|text-based|`@* work_date="tlg001"`| this identifies an edition; see <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/query/cts_work_date.md"></a>|

# ANNIS Query Examples

The following are query examples that can be used as templates:

<table>
  <thead>
    <tr>
      <th>Query</th>
      <th>Explanation</th>
    </tr>
  </thead>
  <tbody>
<tr>
<td><a href="https://annis.varro.informatik.uni-leipzig.de/?id=b30de80b-7d53-41d4-8304-487bf01dffa7#_q=dG9rPSLhvIjPh86xzrnOv-G9tiIgQCogd29ya19kYXRlPS8uKihwMV8xfHAxXzIpLiov&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&">tok="Ἀχαιοὶ" @* work_date=/.*(p1_1|p1_2).*/</a></td>
<td>Search for the word form Ἀχαιοὶ in all texts written in the 1st and 2nd half of the 1st century CE</td>
</tr>

<tr>
<td><a href="https://annis.varro.informatik.uni-leipzig.de/?id=d70ea7e5-fcbd-42fc-9c76-6c2eb45c0c40#_q=cG9zPSJ2IiBfaWRlbnRfIGN0cz0vM18uKi8gQCogYXV0aG9yPSJIb21lciIgX2lkZW50XyB0aXRsZT0iSWxpYWQiCg&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&">pos="v" _ident_ cts=/3_.*/ @* author="Homer" _ident_ title="Iliad"</a></td>
<td>Find all verbs in the 3th Book of Homer's Iliad</td>
</tr>


<tr>
<td><a href="https://annis.varro.informatik.uni-leipzig.de/?id=71be1461-8388-4f80-b602-3e1f4e914678#_q=bGVtbWE9Is-Hz4HPjM69zr_PgiIgQCogYXV0aG9yPS8oTmV3IFRlc3RhbWVudHxTZXB0dWFnaW50YSkv&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&">lemma="χρόνος" @* author=/(New Testament|Septuaginta)/</a></td>
<td>Search for the lemma χρόνος in the New Testament and Septuaginta</td>
</tr>

<tr>
<td><a href="https://annis.varro.informatik.uni-leipzig.de/?id=6f569a32-aa01-4d81-b3f9-72787aa13b07#_q=bGVtbWE9Is-Hz4HPjM69zr_PgiIgQCogYXV0aG9yPSJCaWJsZSI&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&">lemma="χρόνος" @* author="Bible"</a></td>
<td>Same as before but the Bible texts come from a different edition (check <a href="https://github.com/OperaGraecaAdnotata/OGA/blob/main/urn_cts/texts/urn_cts_plus_date_label.xml">the CTS URNs</a>)</td>
</tr>

<tr>
<td><a href="https://annis.varro.informatik.uni-leipzig.de/?id=a0734e4d-4d8b-43e8-9cd5-7ac238863f24#_q=cG9zPSJ2IiBfaWRlbnRfIG1vb2Q9ImkiIC0-ZGVwW2RlcF9mbmM9Ik9CSiJdIHBvcz0ibiIgJiAjMyAuMSwzICMyIEAqIHdvcmtfZGF0ZT0vKG0xXzF8bTFfMikvCg&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&" >pos="v" _ident_ mood="i" ->dep[dep_fnc="OBJ"] pos="n" & #3 .1,3 #2 @* work_date=/.*(m1_1|m1_2).*/</a></td>
<td></td>
</tr>

<tr>
<td><a href="" ></a></td>
<td></td>
</tr>
</tbody>
</table>



[lemma="ἀθηναῖος" @* work_date=/(m5_1|m5_2|m4_1|m4_2)/](https://annis.varro.informatik.uni-leipzig.de/?id=52281da9-9508-4ac2-be14-ce79c5731e2a#_q=bGVtbWE9IuG8gM64zrfOvc6x4b-Wzr_PgiIgQCogd29ya19kYXRlPS8obTVfMXxtNV8yfG00XzF8bTRfMikvCgo&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&)

[lemma="ἀθηναῖος" @* work_date=/(p1_1|p1_2|p2_1|p2_2|p1_1|p1_2)/](https://annis.varro.informatik.uni-leipzig.de/?id=433e2997-85ed-49be-bbe1-858ff27c06d7#_q=bGVtbWE9IuG8gM64zrfOvc6x4b-Wzr_PgiIgQCogd29ya19kYXRlPS8ocDFfMXxwMV8yfHAyXzF8cDJfMnxwMV8xfHAxXzIpLwoK&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&)

[lemma="ἀθηναῖος" @* author="Thucydides"](https://annis.varro.informatik.uni-leipzig.de/?id=79e496e6-79f3-4d6b-bd87-4d8dfc68402f#_q=bGVtbWE9IuG8gM64zrfOvc6x4b-Wzr_PgiIgQCogYXV0aG9yPSJUaHVjeWRpZGVzIgoK&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&)

[pos="v" _ident_ cts=/3_.*/ @* author="Homer" _ident_ title="Iliad"](https://annis.varro.informatik.uni-leipzig.de/?id=d70ea7e5-fcbd-42fc-9c76-6c2eb45c0c40#_q=cG9zPSJ2IiBfaWRlbnRfIGN0cz0vM18uKi8gQCogYXV0aG9yPSJIb21lciIgX2lkZW50XyB0aXRsZT0iSWxpYWQiCg&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&)

[pos="v" _ident_ cts=/3_.*/ @* urn_cts_author="tlg0012" _ident_ urn_cts_work="tlg001"
](https://annis.varro.informatik.uni-leipzig.de/?id=92b6bc7a-2246-4a46-873a-e6fcf21f5d98#_q=cG9zPSJ2IiBfaWRlbnRfIGN0cz0vM18uKi8gQCogdXJuX2N0c19hdXRob3I9InRsZzAwMTIiIF9pZGVudF8gdXJuX2N0c193b3JrPSJ0bGcwMDEiCg&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&)

[pos="v" _ident_ mood="i" ->dep[dep_fnc="OBJ"] pos="n" & #3 .1,3 #2 @* work_date=/(p1_1|p1_2)/
](https://annis.varro.informatik.uni-leipzig.de/?id=fe33e671-1738-4ca0-bf84-d69f58c1a9b7#_q=cG9zPSJ2IiBfaWRlbnRfIG1vb2Q9ImkiIC0-ZGVwW2RlcF9mbmM9Ik9CSiJdIHBvcz0ibiIgJiAjMyAuMSwzICMyIEAqIHdvcmtfZGF0ZT0vKHAxXzF8cDFfMikvCg&ql=aql&_c=b2dhX3YwLjIuMF81LG9nYV92MC4yLjBfMyxvZ2FfdjAuMi4wXzQsb2dhX3YwLjIuMF8xLG9nYV92MC4yLjBfMg&cl=5&cr=5&s=0&l=10&)
