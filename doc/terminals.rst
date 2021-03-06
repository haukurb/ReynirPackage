.. _terminals:

Terminals
=========

This section lists the terminals that can occur within simplified sentence trees,
i.e. instances of the :py:class:`SimpleTree` class. The terminal associated
with a tree node is available in the :py:attr:`SimpleTree.terminal` property.

A terminal node always corresponds to a single token from the input text.

A typical terminal string looks like this (for instance matching the word *hestur*)::

    'no_kk_nf_et'   # Noun, masculine, nominative case, singular

The terminal category, i.e. the first part of the terminal name (``no`` in the
example), is available
in the :py:attr:`SimpleTree.tcat` property. The grammatical variants of the
terminal are stored in the list :py:attr:`SimpleTree.variants`,
which is ``[ 'kk', 'nf', 'et' ]`` in the example.

To obtain the entire set of variants (features) associated with a word form,
use the property :py:attr:`SimpleTree.all_variants`.

The terminal categories and grammatical variants are listed below.

.. _categories:

Word categories
---------------

+------------+---------------------------------------------------+
| no         | Noun (nafnorð)                                    |
+------------+---------------------------------------------------+
| so         | Verb (sagnorð)                                    |
+------------+---------------------------------------------------+
| lo         | Adjective (lýsingarorð)                           |
+------------+---------------------------------------------------+
| fs         | Preposition (forsetning)                          |
+------------+---------------------------------------------------+
| nhm        | Verb infinitive indicator (nafnháttarmerki, *að*) |
+------------+---------------------------------------------------+
| gr         | Definite article (laus greinir, *hinn/hin/hið*)   |
+------------+---------------------------------------------------+
| uh         | Exclamation (upphrópun)                           |
+------------+---------------------------------------------------+
| ao         | Adverb (atviksorð)                                |
+------------+---------------------------------------------------+
| spao       | Interrogative adverb (spurnaratviksorð)           |
+------------+---------------------------------------------------+
| eo         | Qualifying adverb (atviksorð sem stendur með      |
|            | nafnorði í einkunn)                               |
+------------+---------------------------------------------------+
| st         | Conjunction (samtenging)                          |
+------------+---------------------------------------------------+
| stt        | Connective conjunction (sem/er-samtenging)        |
+------------+---------------------------------------------------+
| fn         | Pronoun (fornafn)                                 |
+------------+---------------------------------------------------+
| pfn        | Personal pronoun (persónufornafn)                 |
+------------+---------------------------------------------------+
| abfn       | Reflexive pronoun (afturbeygt fornafn)            |
+------------+---------------------------------------------------+
| person     | Person name (mannsnafn)                           |
+------------+---------------------------------------------------+
| sérnafn    | Proper name (sérnafn)                             |
+------------+---------------------------------------------------+
| entity     | Proper name of recognized named entity            |
+------------+---------------------------------------------------+
| fyrirtæki  | Company name (fyrirtækisnafn)                     |
+------------+---------------------------------------------------+
| gata       | Street name (götuheiti)                           |
+------------+---------------------------------------------------+
| to         | Number word, inflectable (beygjanlegt töluorð)    |
|            | Only *núll, einn, tveir, þrír, fjórir*            |
+------------+---------------------------------------------------+
| töl        | Number word, uninflectable (óbeygjanlegt töluorð) |
+------------+---------------------------------------------------+

Number categories
-----------------

+------------+---------------------------------------------------+
| tala       | Number                                            |
+------------+---------------------------------------------------+
| prósenta   | Percentage                                        |
+------------+---------------------------------------------------+
| ártal      | Year                                              |
+------------+---------------------------------------------------+
| raðnr      | Ordinal number                                    |
+------------+---------------------------------------------------+

Date and time categories
------------------------

+------------+---------------------------------------------------+
| dags       | Date (year, month, day)                           |
+------------+---------------------------------------------------+
| tími       | Time (hour, minute, second)                       |
+------------+---------------------------------------------------+
| tímapunktur| Time point                                        |
|            | (year, month, day, hour, minute, second)          |
+------------+---------------------------------------------------+

Punctuation
-----------

+------------+---------------------------------------------------+
| p          | Punctuation                                       |
+------------+---------------------------------------------------+

|

.. _variants:

Variants
========

This section lists grammatical variants (features) that are
included as parts of terminal names, separated by underscores (``_``).

Gender
------

+------------+---------------------------------------------------+
| kk         | Masculine (karlkyn)                               |
+------------+---------------------------------------------------+
| kvk        | Feminine (kvenkyn)                                |
+------------+---------------------------------------------------+
| hvk        | Neutral (hvorugkyn)                               |
+------------+---------------------------------------------------+

Number
------

+------------+---------------------------------------------------+
| et         | Singular (eintala)                                |
+------------+---------------------------------------------------+
| ft         | Plural (fleirtala)                                |
+------------+---------------------------------------------------+

Case
----

The *case* variants may occur with nouns, pronouns, adjectives, prepositions
and verbs (``lhþt`` and ``subj``). In the case of prepositions, the
variant indicates which case the preposition controls.

+------------+---------------------------------------------------+
| nf         | Nominative (nefnifall)                            |
+------------+---------------------------------------------------+
| þf         | Accusative (þolfall)                              |
+------------+---------------------------------------------------+
| þgf        | Dative (þágufall)                                 |
+------------+---------------------------------------------------+
| ef         | Genitive/Possessive (eignarfall)                  |
+------------+---------------------------------------------------+

Arguments
---------

Verb terminals, other than ``lhþt`` and ``subj``, indicate the number
and cases of the verb's arguments as follows::

    'so_0_et_p3_gm'        # No argument, singular/3rd person/active voice
    'so_1_þf_et_p3_gm'     # Same, but with one argument in accusative case
    'so_2_þgf_þf_et_p3_gm' # Two arguments, dative and accusative

An example of a verb that matches the last terminal would be
*skrifaði* (wrote) in the sentence *"Hann skrifaði konunni bréf"*
("He wrote a letter to the woman").

+------------+---------------------------------------------------+
| 0          | No argument                                       |
+------------+---------------------------------------------------+
| 1          | One argument, whose case is in the following      |
|            | variant                                           |
+------------+---------------------------------------------------+
| 2          | Two arguments, whose cases are in the following   |
|            | two variants                                      |
+------------+---------------------------------------------------+

Person
------

Occurs with verbs (``so`` terminal category) only.

+------------+---------------------------------------------------+
| p1         | First person *(Ég er / Við erum)*                 |
+------------+---------------------------------------------------+
| p2         | Second person *(Þú ert / Þið eruð)*               |
+------------+---------------------------------------------------+
| p3         | Third person *(Það er / Þau eru)*                 |
+------------+---------------------------------------------------+

Degree
------

Occurs with adjectives (``lo`` terminal category) only.

+------------+---------------------------------------------------+
| mst        | Comparative *(stærri)*                            |
+------------+---------------------------------------------------+
| esb        | Superlative, indefinite *(maðurinn er stærstur)*  |
+------------+---------------------------------------------------+
| evb        | Superlative, definite *(stærsti maðurinn)*        |
+------------+---------------------------------------------------+

Verb forms
----------

These variants occur with verbs (``so`` terminal category) only.

+------------+---------------------------------------------------+
| gm         | Active voice (germynd)                            |
+------------+---------------------------------------------------+
| mm         | Middle voice (miðmynd)                            |
+------------+---------------------------------------------------+
| nh         | Infinitive (nafnháttur)                           |
+------------+---------------------------------------------------+
| fh         | Indicative (framsöguháttur)                       |
+------------+---------------------------------------------------+
| bh         | Imperative (boðháttur)                            |
+------------+---------------------------------------------------+
| vh         | Subjunctive (viðtengingarháttur)                  |
+------------+---------------------------------------------------+
| nt         | Present tense (nútíð)                             |
+------------+---------------------------------------------------+
| þt         | Past tense (þátíð)                                |
+------------+---------------------------------------------------+
| lh         | | Present participle (lýsingarháttur nútíðar)     |
|            | | (note that the nt variant will also be present) |
+------------+---------------------------------------------------+
| lhþt       | | Past participle (lýsingarþáttur þátíðar)        |
|            | | (note that the þt variant will NOT be present)  |
+------------+---------------------------------------------------+
| sagnb      | Supine (sagnbót)                                  |
+------------+---------------------------------------------------+
| sb         | Indefinite (sterk beyging),                       |
|            | only occurs with lhþt                             |
+------------+---------------------------------------------------+
| vb         | Definite (veik beyging),                          |
|            | only occurs with lhþt                             |
+------------+---------------------------------------------------+
| op         | Impersonal verb (ópersónuleg sögn)                |
+------------+---------------------------------------------------+
| subj       | Verb that requires the subject's case to be       |
|            | non-nominative (sögn sem krefst frumlags í        |
|            | aukafalli)                                        |
+------------+---------------------------------------------------+

Noun qualifiers
---------------

These variants occur with noun terminals (``no`` category) only.

+------------+---------------------------------------------------+
| gr         | Definite, attached to noun (viðskeyttur greinir   |
|            | með nafnorði)                                     |
+------------+---------------------------------------------------+
| abbrev     | Abbreviation (skammstöfun)                        |
+------------+---------------------------------------------------+

