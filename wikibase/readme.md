# Scripts for upload to Qichwa Wikibase

https://qichwa.wikibase.cloud

## qwbi.py

This contains the setup of a bot for interaction with the wikibase, using [WikibaseIntegrator version 0.12](https://github.com/LeMyst/WikibaseIntegrator/tree/rewrite-wbi).

## create_lexeme.py

This was used in June 2022 for upload of lexemes and POS. Input was 'lemma-upload.csv'.

The mapping of the POS literal values was done according to 'pos-mapping.csv'.

All interim ID from the source CSV correspond to wikibase lexeme entities, as in 'done-lemma-uploads.csv'.


Problems:
+ if there are several lexemes in the lexemes column separated by semicolon, only the last of these is used as lemma when creating the wikibase lexeme. Fix to be discussed: Treat as synonyms, i.e. create a new lexeme for each, and link their sense(s) as synonym sense(s) to each other?
+ we have ignored "fon." POS ("phoneme"). These have an interim ID. A POS entity for "fon." has been created (Q44).
+ we have ignored lexemes not starting with a alphabet letter (these have no interim ID, see 'datasources/MASTER_runasimi_original_with_id.ods' starting at line 25,204)

## add_sense_description.py

This is used in June 2022 for upload of sense descriptions in DE, EN, ES, for monosemous lexemes. Input was 'sense-description-upload.csv'.
Lexemes with sense descriptions that contain a semicolon IN ALL THREE languages are regarded polysemous and excluded from this run. (If there is no semicolon in one language, that most often means that there is only one sense, even if there appears a semicolon as separator in another language).

Lexemes the sense descriptions have been uploaded to are listed in 'done-sense-descriptions.csv'. In a first run, no semicolon had been accepted (one or more semicolon in one or more languages > skip). In a second run, lexemes with one description without semicolon in any of the three languages have been regarded monosemous.

Problems:
+ The use of the semicolon in sense descriptions is not coherent; sometimes a comma stands where in other languages a semicolon is used. Also, it is not clear when the semicolons separate synonyms (that describe the same sense), and when word senses. But most polysemous items should have been skipped.
