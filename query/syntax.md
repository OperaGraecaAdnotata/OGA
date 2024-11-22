# Syntactic Annotation

The syntax has been annotated following the guidelines:

* https://github.com/PerseusDL/treebank_data/blob/master/v1/greek/docs/guidelines.pdf
* https://github.com/PerseusDL/treebank_data/blob/master/AGDT2/guidelines/Greek_guidelines.md

The list of the syntactic labels is: 
SBJ, AuxY, PRED, ATV, ATR, AuxX, AuxC, AuxZ, OBJ, ADV, APOS, PNOM, COORD, AuxK,
AuxP, AtvV, AuxV, ExD, OCOMP, AuxG, AuxΖ, MWE, AuxR, AuxΚ.

Note that the `_CO` and `_AP` suffixes were deleted
to reduce the number of the labels.
Moreover, the root of a syntactic tree is only one token (therefore,
punctuation marks, as well as other nodes,
which in the original AGDT annotation scheme are
dependents of the root, were made dependents of the first node
that depends on the root,
which usually corresponds to the main verb
of a sentence or a coordinate conjunction).
