---
layout: base
title:  'Dutch UD'
udver: '2'
---

# UD for Dutch <span class="flagspan"><img class="flag" src="../../flags/svg/NL.svg" /></span>

## Tokenization and Word Segmentation


* Words are delimited by whitespace or punctuation
* Words do not contain spaces, although some lemma's for multi-word expressions do (_au serieux, dat wil zeggen, onder ander, onder veel, ter plaatse, tot en met_)
* Words (e.g. abbreviations, names, URLs etc.) may contain arbitrary punctuation signs (http://www.speelgoedmuseum.be, vroeg-renaissance, o.a., ex-VU&ID)
* No multiword tokens occur (i.e. forms like _ten_ are treated as a single token, not as _te+een_)

---
**Instruction**: Describe the general rules for delimiting words (for example, based on whitespace and punctuation) and exceptions to these rules. Specify whether words with spaces and/or multiword tokens occur. Include links to further language-specific documentation if available.


---

## Morphology


### Tags

* ADJ (XPOS=ADJ) is used for adjectives. Adjectives occur as prenominal modifiers, as predicates, as seperable verb-particles, as adverbs, as part of fixed expressions and names. Also, in cases where an adjective functions as noun (_om Nederlandstaligen te pesten_) the POS is still ADJ. Ordinal number words such as _eerste, 60ste_ (XPOS=TW|rang) are also ADJ.
* ADP (XPOS=VZ) is used for prepositions and postpositions. They introduce nominal and verbal modifiers. They also occur as seperable verb-particles, as part of fixed expressions and names. The verbal inflexion element _te_ is also an ADP.  In prepositional phrases such as _ten opzichte van_ _ten_ and _van_ are ADP and _opzichte_ is a NOUN. 
* ADV (XPOS=BW) is used for adverbs. Also, some adverbial pronouns (R-pronouns) such as _daar, er, ergens, waar_ are ADV. 
* AUX (XPOS=WW) is used for 
    * perfect tense auxiliaries _hebben_ and _zijn_
    * the passive tense auxiliaries _worden_ and _zijn_ and _krijgen_ (in so-called cases of _krijgen-passive_ such as _U krijgt een bewegwijzering toegezonden_)
    * the modal verbs _kunnen, zullen, moeten, mogen_ (The treebank annotation on which the conversion to UD is based does not distinguish between auxiliaries and main verbs. Here we take a conservative approach in labeling only these modals as auxiliaries. )
    * the copula verb _zijn_ (UD allows only one copula verb per language, even though traditional Dutch syntax lists several verbs as copula-verbs.)
* CCONJ (XPOS=VG|neven) is used for coordinating conjunctions such as _en_ and _of_, _zowel_ (X _als_ Y). (ISSUE: Note that _als_ in this context is labeled SCONJ as it is XPOS=VG|onder)
* DET (XPOS=LID, XPOS=VNW|prenom) is used for words that are part of a noun phrase and function as determiner. They are:
   * words that have XPOS LID in the original data (_de, het, een_). These are words traditionally seen as determiners in Dutch
   * Prenominal pronouns (_deze, welke, meerdere, sommige_) with the exception of possessive pronouns (_mijn_). They are labeled PRON. 
   * ISSUE: In multi-word determiner expressions such as _maar weinig_, _helemaal geen_, _al mijn_, both words are DET. The modifiers should be ADV and _mijn_ should be PRON. 
   * ISSUE: Numeric elements such as +11,77 or 26% (XPOS=SPEC|symb) are labeled as DET if their grammatical function is det, where this should be NUM. (Note that regular numeric values such as 11 or 26 have XPOS=TW and are labeled NUM.)
* INTJ (XPOS=TSW) Elements that are not part of the syntactic structure such as _ach, verrek, jazeker_
* NOUN (XPOS=N|soort) Nouns can be the head of a variety of dependents, such as subject, object, oblique, etc. 
* NUM (XPOS=TW|hoofd). Tokens such as _1, 0,80, +4,20 -1, 1.000, 040-12280, drieduizend, iv, twaalf_. Note that elements such as _eerste_ are labeled ADJ. 
* PART is not used. In particular, seperable verb prefixes are assigned their regular POS and are a compound:prt dependent of the verb. 
* PRON (XPOS=VNW) is used for 
   * possessive pronouns
   * pronominal elements that do not occur in prenominal position but are depedents of a verb, like personal and impersonal pronouns (_ik, u, iemand _)
* PROPN (XPOS=N|eigen, SPEC|deeleigen) is used for proper names (_Achterberg_) and the parts of multi-word names (_ Gerrit Achterberg_). When used as adjective (_Amsterdamse_), names are labeled ADJ. 
* PUNCT (XPOS=LET) is used for punctuation. 
* SCONJ (XPOS=VG|onder) is used for subordinating conjunctions (_als, dat, of, omdat, toen_).  
   * ISSUE: in multi-word expressions such as _dan wel_ _dan_ is VG|onder but could also be VG|neven and thus CCONJ with seems more appropriate as it also introduces a cc in syntax. 
* SYM (XPOS=SPEC|sym, SPEC|afgebr, SPEC|vreemd, LET) is used for symbols (), foreign words (_unit, vici, walkover_), incomplete words (_welzijns-, zorg-_) and interpunction that does not introduce a punc relation in syntax (i.e. as it is part of a name/title (_ZinderZlam !_) or a multi-word unit (_en / of_) ). 
* VERB (XPOS=WW) is used for verbs that are not AUX. Note that adjectively used verbs and nominalized verbs are VERB (_passende maatregelen, het verplaatsen van voorwerpen_).  
* X (XPOS=SPEC|afk) is used for abbreviations (_ v.Chr., o.a., nr._) 

Detailed documentation of the decisions w.r.t. POS-tags in the original data can be found in the [D-COI POS-tagging and lemmatization manual](https://www.let.rug.nl/vannoord/Lassy/POS_manual.pdf)

### Features

* Abbr=Yes for abbreviations (POS=X, XPOS=SPEC|afk)
* Case=Acc,Nom for PRON (Nom for XPOS=VNW|nomin, Acc for XPOS=VNW|obl). 
* Definite=Def,Ind for DET (Def for XPOS=LID|bep, Ind for XPOS=LID|onbep)
* Degree=Pos,Cmp,Sup for adjectives (POS=ADJ, Pos for XPOS=ADJ|basis, Sup for ADJ|sup, Cmp for ADJ|comp) 
* Gender=Com,Neut for NOUN and PROPN, Com for N|onz, Neut for N|onz, Com,Neut for N|genus 
* Person=1,2,3 for PRON (1 for XPOS=VNW|1, 2 for XPOS=VNW|2,2v,2b, 3 for XPOS=VNW|3,3p,3v,3p,3o
* PronType=Int,Prs,Ind,Rel,Dem for PRON (Dem for demonstratives, VNW|aanw, Rel for relative pronouns, VNW|betr, Prs for personal and possessive pronouns, VNW|pers and VNW|bez, Ind for indefinite pronouns,  VNW|onbep, Int for interoggative pronouns, VNW|vb). 
* Number=Sing,Plur for AUX, NOUN, VERB, PROPN, Sing for WW|ev, WW|met-t, N|ev, Plur for WW|mv, N|mv 
* Poss=Yes for PRON with VNW|bez 
* Reflex=Yes for PRON with VNW|refl 
* VerbForm=Inf,Fin,Part for AUX and VERB with Inf for WW|inf, Fin for WW|pv and Part for WW|od or WW|vd 

Detailed documentation of the decisions w.r.t. features in the original data can be found in the [D-COI POS-tagging and lemmatization manual](https://www.let.rug.nl/vannoord/Lassy/POS_manual.pdf)

## Syntax

*

---
**Instruction**: Give criteria for identifying core arguments (subjects and objects), and describe the range of copula constructions in nonverbal clauses. List all subtype relations used. Include links to language-specific relations definitions if any.

---

## Treebanks

There are [2](../treebanks/nl-comparison.html) Dutch UD treebanks:

  * [UD_Dutch-Alpino](../treebanks/nl_alpino/index.html)
  * [UD_Dutch-LassySmall](../treebanks/nl_lassysmall/index.html)

---
**Instruction**: Treebank-specific pages are generated automatically from the README file in the treebank repository and
from the data in the latest release. Link to the respective `*-index.html` page in the `treebanks` folder, using the language code and the treebank code in the file name.

---
