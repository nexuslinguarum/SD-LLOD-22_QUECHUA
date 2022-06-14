= Scripts for upload to Qichwa Wikibase =

https://qichwa.wikibase.cloud

== create_lexeme.py ==

This was used in June 2022 for upload of lexemes and POS. Input was 'lemma-upload.csv'.
The mapping of the POS literal values was done according to 'pos-mapping.csv'
Problems:
* if there are several lexemes in the lexemes column separated by semicolon, only the last of these is used for creating the wikibase lexeme. Fix TBD.
