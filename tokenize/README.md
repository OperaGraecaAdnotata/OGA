# Tokenize

This folder contains a list of tokens to tokenize and a list of tokens not to
tokenize (the latter being at moment empty), which are used during
tokenization.

The file `texts/to-tokenize.xml` has been mostly created automatically
searching for words containing the coronis, i.e., the Unicode codepoint
COMBINING COMMA ABOVE (U+0313) on a vowel that is not the beginning of a word.
The so-identified words have then been split into two tokens: (i) the first
character and (ii) any other following character.

The file `texts/to-tokenize.xml` also contains words whose analysis has been
added manually: for example, "οὐδὲ" corresponds to "οὐ" and "δὲ".

The Greek in the list is NFC-normalized and the apostrophe letter always
corresponds to MODIFIER LETTER APOSTROPHE (U+02BC).


TO DO:

- [ ] The cases where crasis is not unambigously marked by a coronis (i.e.,
when a rough breathing is on the initial vowel of a word) are more difficult to identify
rule-based, and therefore are at the moment not contained in this list:
they can be added in the future, for example, by looking at those lists
contained in grammars such as
https://archive.org/details/p1ausfhrlichegra01khuoft/page/218/mode/2up .

- [ ] The cases of crasis automatically identified by searching for
the Unicode codepoint COMBINING COMMA ABOVE (U+0313) have to be checked because
errors in the original texts return a few wrong results: this is especially
true when there is no whitespace between two graphic words and the second one
happens to start with a vowel with smooth breathing.
