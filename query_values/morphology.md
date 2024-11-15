# Morphology

Morphology can be queried using the keys with the possible
values shown in the table below. 

## AQL example query

|query|explanation|
|-----|-----------|
|pos="v" _ident_ tense="p"|search for a token that is a verb and in the present tense

## Possible keys and values

<table>
  <tr>
    <th>key</th>
    <th>value</th>
    <th>explanation</th>
  </tr>
  <tr>
    <td rowspan="10">pos</td>
    <td>n</td>
    <td>noun</td>

  </tr>
  <tr>
    <td>v</td>
    <td>verb</td>

  </tr>
  <tr>
    <td>a</td>
    <td>adjective</td>

  </tr>
  <tr>
    <td>d</td>
    <td>adverb</td>

  </tr>
  <tr>
    <td>l</td>
    <td>article</td>
  </tr>
  <tr>
    <td>g</td>
    <td>particle</td>
  </tr>
  <tr>
    <td>c</td>
    <td>conjunction</td>
  </tr>
  <tr>
    <td>r</td>
    <td>preposition</td>
  </tr>
  <tr>
    <td>p</td>
    <td>pronoun</td>
  </tr>
  <tr>
    <td>m</td>
    <td>numeral</td>
  </tr>

  <tr>
    <td rowspan="3">person</td>
    <td>1</td>
    <td>first</td>

  </tr>
  <tr>
    <td>2</td>
    <td>second</td>

  </tr>
  <tr>
    <td>3</td>
    <td>third</td>

  </tr>

  <tr>
    <td rowspan="3">number</td>
    <td>s</td>
    <td>singular</td>

  </tr>
  <tr>
    <td>p</td>
    <td>plural</td>

  </tr>
  <tr>
    <td>d</td>
    <td>dual</td>

  </tr>

  <tr>
    <td rowspan="7">tense</td>
    <td>p</td>
    <td>present</td>

  </tr>
  <tr>
    <td>i</td>
    <td>imperfect</td>

  </tr>
  <tr>
    <td>r</td>
    <td>perfect</td>
  </tr>
  <tr>
    <td>l</td>
    <td>pluperfect</td>
  </tr>
  <tr>
    <td>t</td>
    <td>future perfect</td>

  </tr>
  <tr>
    <td>f</td>
    <td>future</td>
  </tr>
  <tr>
    <td>a</td>
    <td>aorist</td>
  </tr>


  <tr>
    <td rowspan="6">mood</td>
    <td>i</td>
    <td>indicative</td>
  </tr>
  <tr>
    <td>s</td>
    <td>subjunctive</td>
  </tr>
  <tr>
    <td>o</td>
    <td>optative</td>
  </tr>
  <tr>
    <td>n</td>
    <td>infinitive</td>
  </tr>
  <tr>
    <td>m</td>
    <td>imperative</td>
  </tr>
  <tr>
    <td>p</td>
    <td>participle</td>
  </tr>

  <tr>
    <td rowspan="4">mood</td>
    <td>a</td>
    <td>active</td>
  </tr>
  <tr>
    <td>p</td>
    <td>passive</td>
  </tr>
  <tr>
    <td>m</td>
    <td>middle</td>
  </tr>
  <tr>
    <td>e</td>
    <td>medio-passive</td>
  </tr>

  <tr>
    <td rowspan="3">gender</td>
    <td>m</td>
    <td>masculine</td>
  </tr>
  <tr>
    <td>f</td>
    <td>feminine</td>
  </tr>
  <tr>
    <td>n</td>
    <td>neuter</td>
  </tr>

  <tr>
    <td rowspan="6">case</td>
    <td>n</td>
    <td>nominative</td>
  </tr>
  <tr>
    <td>g</td>
    <td>genitive</td>
  </tr>
  <tr>
    <td>d</td>
    <td>dative</td>
  </tr>
  <tr>
    <td>a</td>
    <td>accusative</td>
  </tr>
  <tr>
    <td>v</td>
    <td>vocative</td>
</tr>
  <tr>
    <td>l</td>
    <td>locative</td>

  </tr>

  <tr>
    <td rowspan="2">degree</td>
    <td>m</td>
    <td>comparative</td>
  </tr>
  <tr>
    <td>f</td>
    <td>superlative</td>

  </tr>

</table>


