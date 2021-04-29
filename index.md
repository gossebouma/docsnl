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

* ADJ (XPOS=ADJ) is used for adjectives. Adjectives occur as prenominal modifiers, as predicates, as seperable verb-particles, as adverbs, as part of fixed expressions and names. Also, in cases where an adjective functions as noun (_om Nederlandstaligen te pesten_) the POS is still ADJ. 
* ADP (XPOS=VZ) is used for prepositions and postpositions. They introduce nominal and verbal modifiers. They also occur as seperable verb-particles, as part of fixed expressions and names. The verbal inflexion element _te_ is also an ADP.  In prepositional phrases such as _ten opzichte van_ _ten_ and _van_ are ADP and _opzichte_ is a NOUN. 
* ADV (XPOS=BW) is used for adverbs. 
* AUX (XPOS=WW) is used for 
    * perfect tense auxiliaries _hebben_ and _zijn_
    * the passive tense auxiliaries _worden_ and _zijn_ and _krijgen_ (in so-called cases of _krijgen-passive_ such as _U krijgt een bewegwijzering toegezonden_)
    * the modal verbs _kunnen, zullen, moeten, mogen_ (The treebank annotation on which the conversion to UD is based does not distinguish between auxiliaries and main verbs. Here we take a conservative approach in labeling only these modals as auxiliaries. )
    * the copula verb _zijn_ (UD allows only one copula verb per language, even though traditional Dutch syntax lists several verbs as copula-verbs.)
* CCONJ (XPOS=VG|neven) is used for coordinating conjunctions such as _en_ and _of_, _zowel_ X _als_ Y. 
* DET (XPOS=LID, XPOS=VNW|prenom) is used for words that are part of a noun phrase and function as determiner. They are:
   * words that have XPOS LID in the original data (_de, het, een_). These are words traditionally seen as determiners in Dutch
   * Prenominal pronouns (_deze, welke, meerdere, sommige_) with the exception of possessive pronouns (_mijn_). They are labeled PRON. 
* INTJ (XPOS=TSW) Elements that are not part of the syntactic structure such as _ach, verrek, jazeker_
* NOUN (XPOS=N|soort) 
* NUM
* PRON is used for non-adverbial pronominal elements. They are: 
   * words with pt=vnw in the original annotation that do not function as determiner and that are not of pdtype=adv-pron.
* PROPN (XPOS=N|eigen) 
* PUNCT
* SCONJ
* SYM 
* VERB is used for words labeled pt=ww in the original data and that are not AUX. Note that according to this method, in nominalizations, the head is a VERB. 
* ADJ is used for words labeled pt=adj in the original data.
* NOUN is used for words labeled pt=n in the original data that do not have ntype=deeleigen. (The latter are part of a proper name and are labeled PROPN)
    
Detailed documentation of the decisions w.r.t. POS-tags in the original data can be found in the [D-COI POS-tagging and lemmatization manual](https://www.let.rug.nl/vannoord/Lassy/POS_manual.pdf)

---
**Instruction**: Specify any unused tags. Explain what words are tagged as PART. Describe how the AUX-VERB and DET-PRON distinctions are drawn, and specify whether there are (de)verbal forms tagged as ADJ, ADV or NOUN. Include links to language-specific tag definitions if any.

---

### Features

*

---
**Instruction**: Describe inherent and inflectional features for major word classes (at least NOUN and VERB). Describe other noteworthy features. Include links to language-specific feature definitions if any.

---

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
