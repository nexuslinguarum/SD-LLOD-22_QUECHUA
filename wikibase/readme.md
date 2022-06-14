# Scripts for upload to Qichwa Wikibase

https://qichwa.wikibase.cloud

** create_lexeme.py

This was used in June 2022 for upload of lexemes and POS. Input was 'lemma-upload.csv'.
The mapping of the POS literal values was done according to 'pos-mapping.csv'
Problems:
+ if there are several lexemes in the lexemes column separated by semicolon, only the last of these is used for creating the wikibase lexeme. Fix TBD.
+ we have ignored "fon." POS ("phoneme"). These have an interim ID. A POS entity for "fon." has been created (Q44).
+ we have ignored lexemes not starting with a alphabet letter (these have no interim ID, see 'datasources/MASTER_runasimi_original_with_id.ods' starting at line 25,204)

** add_sense_description.py

This is used in June 2022 for upload of sense descriptions in DE, EN, ES, for monosemous lexemes. Input was 'sense-description-upload.csv'.
Lexemes with sense descriptions that contain a semicolon IN ALL THREE languages are regarded polysemous and excluded from this run. (If there is no semicolon in one language, that most often means that there is only one sense, even if there appears a semicolon as separator in another language)
Problems:
+ The use of the semicolon in sense descriptions is not coherent; sometimes a comma stands where in other languages a semicolon is used. Also, it is not clear when the semicolons separate synonyms (that describe the same sense), and when word senses.
