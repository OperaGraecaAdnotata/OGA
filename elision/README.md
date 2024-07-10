# Elision

This folder contains a list of elided words created automatically by searching
the original texts for all graphic words ending with MODIFIER LETTER
APOSTROPHE (U+02BC), i.e., the Unicode codepoint that should always be used
for apostrophe.

Such a list is used to replace, in the original texts, other characters
inconsistently used to mean apostrophe, i.e., APOSTROPHE (U+0027) and RIGHT
SINGLE QUOTATION MARK (U+2019).

Moreover, COMBINING COMMA ABOVE (U+0313) and GREEK KORONIS (U+1FBD) are also
always replaced with MODIFIER LETTER APOSTROPHE (U+02BC).

The Greek in the list is NFC-normalized.

TO DO:
- [ ] the list should be checked in that it has been created automatically.
