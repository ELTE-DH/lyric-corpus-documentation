# Documentation of the Corpus of Hungarian Lyrical Poetry

This repository contains the documentation of the Corpus of Hungarian Lyrical Poetry, developed by the Research Group in Stylistics at Eötvös Loránd University. The corpus itself is not publicly accessible for copyright reasons.


# Subcorpora, sizes, sampling methods

- **All:** 531/525 texts (From the 531 texts, 6 texts were removed at the manual annotation stages.) Number of tokens: 170 000
- **Canonical poems from the 20th century:** 159 poems by 19 authors were selected from popular high school literary anthologies published between 2007 and 2020. Poems were selected if they appeared in at least three of the five textbooks used. From the level2_corrected files containing the morphosyntactic annotations corrected manually, six long poems were removed, the number of remaining authors is 18. Number of tokens: 38 000
- **Contemporary poems:** 120 poems by 40 authors were selected from the database of the [Digitális Irodalmi Akadémia](https://dia.hu/) (Digital Literary Academy). Three poems by each author were sampled randomly. Number of tokens: 19 000
- **Song lyrics:** 144 songs were selected from the annual streaming and radio charts provided by [MAHASZ](https://www.mahasz.hu/) (Hungarian Association of Record Producers), covering the period from 2014 to 2022. A maximum of three songs per artist were included. Number of tokens: 52 000. The songs can be listened to [here](https://open.spotify.com/playlist/66U9J7G8TyCpX9RNIIuMvV?si=wkq-4521SgmHb0a28hgvVg).
- **Slam poetry texts:** 108 texts by 54 authors were selected based on the view counts of videos from the [Slam Poetry Magyarország](https://www.youtube.com/@slampoetrymagyarorsz) (Slam Poetry Hungary) YouTube channel. A maximum of three texts per author were included. Number of tokens: 60 000


# Remarks on the slam poetry subcorpus

Since the slam poetry transcriptions in the level0 folder have not yet been verified by the authors, the generated files in the level1 and level2 folders are only temporary versions. Therefore, we have not included metadata in the TEI headers (e.g., author name, title). The metadata can be found in the slam\_corpus\_content.tsv file.


## High school literary anthologies used for the compilation of the canonical subcorpus

- Domonkos Péter: Irodalmi szöveggyűjtemény III. \[második kiadás\] Budapest: Nemzeti Tankönyvkiadó. 2007
- Domonkos Péter: Irodalmi szöveggyűjtemény IV. \[negyedik kiadás\] Budapest: Nemzeti Tankönyvkiadó. 2008
- Madocsai László: Irodalmi szöveggyűjtemény a középiskolák 11. évfolyama számára. \[első kiadás\] Budapest: Nemzeti Tankönyvkiadó. 2011.
- Madocsai László: Irodalmi szöveggyűjtemény a középiskolák 12. évfolyama számára. \[első kiadás\] Budapest: Nemzedékek Tudása Tankönyvkiadó. 2014
- Magyar Tünde: Irodalom szöveggyűjtemény 11. Budapest: Oktatási Hivatal (Esterházy Károly Egyetem). 2020. \[2012-es NAT alapján\]
- Magyar Tünde: Irodalom szöveggyűjtemény 12. Budapest: Oktatási Hivatal (Eszterházy Károly Egyetem) 2020. \[2012-es NAT alapján\]
- Mohácsy Károly: Irodalmi szöveggyűjtemény a középiskolák 11. évfolyama számára. Budapest: Krónika Nova Kiadó. 2006.
- Mohácsy Károly – Vasi Géza: Irodalmi szöveggyűjtemény a középiskolák 12. évfolyama számára. Budapest: Krónika Nova Kiadó. 2007.
- Pethőné Nagy Csilla: Irodalom 11. Szöveggyűjtemény. Budapest: Eszterházy Károly Egyetem Oktatáskutató és Fejlesztő Intézet. 2020. \[2012-es NAT alapján\]
- Pethőné Nagy Csilla: Irodalom 12. Szöveggyűjtemény. Budapest: Eszterházy Károly Egyetem Oktatáskutató és Fejlesztő Intézet. 2020. \[2012-es NAT alapján\]


# Annotation levels

For level3\_without\_meter, level3, and level4, we used the workflow applied in building the [ELTE Poetry Corpus](https://github.com/ELTE-DH/poetry-corpus). See the detailed description of the workflow [_here_](https://aclanthology.org/2022.lrec-1.372/).

- **level0:** manually corrected slam poetry transcriptions without annotations and the non-annotated texts of songs, canonical poems and contemporary poems generated from the level1 files.
- **level1:** manually created annotations of structural units (lines, stanzas). 
    - Format: [_TEI XML_](https://tei-c.org/).
    - Subcorpora: Canonical, Contemporary, Song Lyrics, Slam Poetry
    - Remark: The transcriptions of the slam poetry texts have not been verified by the authors. They include the annotators’ comments on poorly audible or inaudible sections, which are indicated in square brackets.
- **level2:** automatically created annotations of lemma, part of speech and morphosyntactic features of words. 
    - Tool: emtsv version of [_e-magyar_](https://github.com/nytud/emtsv), [_Universal Dependencies_](https://universaldependencies.org/) labels.
    - Format: [_TEI XML_](https://tei-c.org/)
    - Subcorpora: Canonical, Contemporary, Song Lyrics, Slam Poetry
    - Remark: The transcriptions of the slam poetry texts have not been verified by the authors. They include the annotators’ comments on poorly audible or inaudible sections, which are indicated in square brackets. These notes are also annotated automatically, which can distort the research results. 
- **level2\_corrected:** Manually corrected annotations of lemma, part of speech and morphosyntactic features of words.
    - Format: [_TEI XML_](https://tei-c.org/)
    - Subcorpora: Canonical, Contemporary, Song Lyrics
- **level2\_corrected\_conllu:** Manually corrected annotations of lemma, part of speech and morphosyntactic features of words. This is the input format of the program Inception used for syntactic annotation.
    - Format: [_CoNLL-U_](https://universaldependencies.org/format.html)
    - Subcorpora: Canonical, Contemporary, Song Lyrics 
- **level3\_without\_meter:** Automatically created annotations of rhyme patterns, rhyme pairs, rhythm of lines, alliterations, and phonological features of words, in addition to the already created annotations.
    - Tool:  hunpoem\_analyzer-TEI Python program originally developed for the ELTE Poetry Corpus
    - Format: [_TEI XML_](https://tei-c.org/)
    - Subcorpora: Canonical, Contemporary, Song Lyrics
- **level3:** Automatically created annotations of quantitative and qualitative meters, in addition to the already created annotations.
    - Tool: [_Hunpoem\_meter\_analyzer_](https://github.com/ELTE-DH/hunpoem-meter-analyzer) Python program originally developed for the [_ELTE Poetry Corpus_](https://github.com/ELTE-DH/poetry-corpus)
    - Format: [_TEI XML_](https://tei-c.org/)
    - Subcorpora: Canonical, Contemporary, Song Lyrics
- **level4:** Modified position and/or name of some elements and attributes, and automatically generated annotations of syllable counts, word counts per structural unit, and other simple numeric features, alongside existing annotations.
    - Format: XML developed for the [_ELTE Poetry Corpus_](https://github.com/ELTE-DH/poetry-corpus)
    - Subcorpora: Canonical, Contemporary, Song Lyrics
- **level5:** Manually annotated syntactic features. The annotations focus on the dependency relations between the verb and its complements.
    - Tool: [Inception](https://inception-project.github.io/)
    - Format: XML, TSV, JSON
    - Subcorpora: Canonical, Contemporary, Song Lyrics 


# Elements and attributes of the XML files

## level1 -- annotation of structural units

- `<head>` : title
- `<lg>`: stanza
- `<l>`: line
- `<p>`: subtitle, epigraph, separator
- `@type` attribute of `<l>` elements: type of text parts for song lyrics
	- `verse`
	- `chorus`
- `type="background"`: in song lyrics, those lines that are sung, rapped, said or repeated in the background, not as part of the main vocal.

## level2 -- tokenization and annotation of grammatical features of words

- `<w>` : word
- `<pc> `: punctuation mark
- `@lemma` : lemma
- `@pos `: part of speech
- `@msd` : morphosyntactic features ([Universal Dependencies](https://universaldependencies.org/))
- `@join` : its value indicates the attachment direction of punctuation marks.
    - `right`
	- `left`

## level2_corrected -- manual corrections of the automatic annotations in level2

- `@change`: its value indicates whether the automatically created annotation was corrected manually.
	- `no`
	- `yes`
- `@type` attribute of `<w>` elements: its value indicates whether the annotator was unsure when correcting the word’s grammatical annotations.
    - `no_problem`
	- `problem` (Since annotators usually asked the project coordinator in problematic cases, these values are rarely used in the final version.)
	
## level3_without_meter -- annotation of sound devices without meter

The same as level3 without the `@met` attribute containing the meter of the poem. This is the input format of the program [_Hunpoem\_meter\_analyzer_](https://github.com/ELTE-DH/hunpoem-meter-analyzer) detecting quantitative and qualitative meters in Hungarian poetry.

## level3 -- annotation of sound devices

- `@met `: meter
	- `Qual` : qualitative meter based on stressed and unstressed syllables
	- `Quan` : quantitative meter based on long and short syllables (possible values: iambic, trochaic, dactylic, anapestic)
	- `QuanScore` : score of quantitative meter (before 0.5, the poem does not really have any intended quantitative meter)
- `@rhyme `: rhyme pattern
- `@real `: rhythm (0: short syllable; 1: long syllable)
- `<spanGrp type="phonStructures">` : standoff annotation of the phonological features of words
- `<span>` : standoff annotation of the phonological features of a word
	content of `<span>` : phonological representation of the word
	- `c`: consonant
	- `b`: short back vowel
	- `B`: long back vowel
	- `f`: short front vowel
	- `F`: long front vowel
- `@subtype` : syllable number
- `@type` : type of vowels
	- `low`: only back vowels in the word
	- `high`: only front vowels in the word
	- `mixed`: front and back vowels in the word
- `@target` : the `xml:id` of the annotated word
- `<linkGrp type="rhymePairs">` : standoff annotation of rhyme pairs
- `<link>` : standoff annotation of a rhyme pair
- `@target` : xml:id of the two words in a rhyme pair
- `<spanGrp type="alliterations">` : standoff annotation of alliterations
- `<span>` : standoff annotation of an alliteration
- `@target` : `xml:id` of the words in the alliteration
- `@type` : structure of the alliteration
	- `a`: alliterating word
	- `n`: non-alliterating word (only one non-alliterating word can be between two alliterating words)
	
## level4 -- conversion of the TEI format into non-TEI format

By changing the name and the position of certain elements and attributes in level3 and by adding further annotations to the corpus, it is easier to process but cannot be expressed in valid TEI XML format. This format was originally developed for the [_ELTE Poetry Corpus_](https://github.com/ELTE-DH/poetry-corpus)

- `@met_qual` : qualitative meter based on stressed and unstressed syllables (conversion of level3's `@met` in `<div>`)
- `@met_quan` : quantitative meter based on long and short syllables, possible values: iambic, trochaic, dactylic, anapestic (conversion of level3's `@met` in `<div>`)
- `@met_quanScore` : score of quantitative meter, before 0.5, the poem does not really have any intended quantitative meter (conversion of level3's `@met` in `<div>`)
- `@div_numStanza` : number of stanzas in the poem
- `@div_numLine `: number of lines in the poem
- `@div_numWord `: number of words in the poem
- `@div_numSyll `: number of syllables in the poem
- `@div_numShortSyll` : number of short syllables in the poem
- `@div_numLongSyll `: number of long syllables in the poem
- `@div_rhyme` : the rhyme pattern of the poem
- `@div_syllPattern` : syllable numbers of lines in the poem
- `@lg_numLine `: number of lines in the stanza
- `@lg_numWord `: number of words in the stanza
- `@lg_numSyll `: number of syllables in the stanza
- `@lg_numShortSyll` : number of short syllables in the stanza
- `@lg_numLongSyll `: number of long syllables in the stanza
- `@lg_syllPattern `: syllable numbers of lines in the stanza
- `@l_numWord `: number of words in the line
- `@l_numSyll `: number of syllables in the line
- `@l_numShortSyll` : number of short syllables in the line
- `@l_numLongSyll `: number of long syllables in the line 
- `@w_numSyll` : syllable number of word (conversion of level3's `@subtype` in `<span>`)
- `@phonType` : type of vowels in the word (conversion of level3's `@type` in `<span>`)
- `@phonStruct` : phonological representation of the word (conversion of level3's `<span>` content)
- `<rhymePairs> `: standoff annotation of rhyme pairs (conversion of level3's `<linkGrp type="rhymePairs">`)
- `<rhymePair>` : standoff annotation of a rhyme pair (conversion of level3's `<link>`)
- `<firstRhyme>`, `<secondRhyme>` : standoff annotation of the first and second word of a rhyme pair
	- content of `<firstRhyme>` and `<secondRhyme>` : the rhyming word form
- `@rhyme_lemma` : the lemma of the rhyming word
- `@rhyme_pos` : the part of speech of the rhyming word
- `@rhyme_msd` : the morphosyntactic features of the rhyming word (Universal Dependencies)
- `@rhyme_numSyll` : the syllable number of the rhyming word
- `@rhyme_phonType `: the type of vowels in the rhyming word
- `@rhyme_phonStruct` : the phonological representation of the rhyming word
- `<alliterations>` : standoff annotation of alliterations (conversion of level3's `<spanGrp type="alliterations">`)
- `<alliteration>` : standoff annotation of an alliteration (conversion of level3's `<span>`)
	- content of `<alliteration>` : the alliterating word forms
- `@allStruct` : structure of the alliteration (conversion of level3's `@type` in `<span>`)
- `@posTags` : the parts of speech of the alliterating words
- `@msdTags `: the morphosyntactic features of the alliterating words
- `@lemmas` : the lemmas of the alliterating words

# Syntactic labels of the level5 files

## Labels of tokens

- `Core`: finitie verb or infinitive
- `Aux`: auxiliary verb
- `Prev`: verbal prefix separated from the verb
- `Arg`: complement of the verb
- `Arg:core`: an argument of the verb that forms a clausal core together with the verb (a complement that specifies a light verb)
- `Case`: postposition, postpositional adjective (e.g., _az asztal alatti_), or the word _mint_ used in the function of the _-ként_ suffix
- `Poss`: unmarked or marked (with the _-nak/-nek_ suffix) possessive modifier
- `Voc`: vocative (the entire vocative structure, including articles, modifiers, and interjections, receives this label)
- `Flat`: in multi-word expressions (usually proper names), all elements before the last one
- `Core:omitted`, `Arg:omitted`, `Aux:omitted`: elements realized in a previous (or later) verbal structure that allow for elliptical constructions; not present in the elliptical structure itself

## Labels of dependency reletaions

- `tr`: the relation of a verb or infinitive (Core) to the semantic subject (Arg) or to a vocative referring to the semantic subject (Voc)
- `lm`: the relation of a verb or infinitive (Core) to a non-subject complement (Arg) or a vocative not referring to a non-subject complement (Voc)
- `prev`: the relation of a verb or infinitive (Core) to a verbal prefix (Prev) separated from the verb
- `case`: the relation of a nominal argument (Arg) to a postposition, postpositional adjective, or to the word _mint_ used in the function of the _-ként_ suffix (Case)
- `aux`: the relation of an infinitive (Core) to an auxiliary verb (Aux)
- `poss`: the relation of a noun to an unmarked or marked (with the _-nak/-nek_ suffix) possessive modifier (Poss)
- `cor`: the relation of a nominal or pronominal argument (Arg) to a coreferential vocative (Voc)
- `flat`: in multi-word expressions (usually proper names), the relation of the last element to the preceding elements

See the detailed guidelines in syntactic\_annotation\_guidelines.pdf, and in this paper: 

Horváth Péter -- Simon Gábor -- Tátrai Szilárd 2022: Annotation of person marking constructions in the Corpus of Hungarian Lyrical Poetry: principles and practices. _Studia Lingustica Hungarica_ 34: 22--37.
[https://ojs.elte.hu/slh/article/view/5400/4372](https://ojs.elte.hu/slh/article/view/5400/4372)


# Scripts

The scripts folder contains the Python scripts used to automate format conversion, validation, fixing, and certain stages of the corpus-building workflow. Researchers using this corpus do not need these scripts.


# Contributors

- [Péter Horváth](https://github.com/luhpeg): workflow, project coordination, annotation scheme
- Szilárd Tátrai: principal investigator, annotation scheme
- Gábor Simon: annotation scheme
- Róbert Kopcsák: annotation
- Noémi Prótár: annotation
- Kata Heller: annotation
- Emese K. Molnár: annotation
- Márton Mészáros: speech-to-text recognition
- We are grateful to the other members of the Research Group in Stylistics at Eötvös Loránd University, who contributed ideas to the annotation scheme and participated in the test annotations.


# Funding

The corpus building was supported by the project No. K-137659 (_Corpus-based cognitive poetic research on person marking constructions_) of the National Research, Development and Innovation Office of Hungary.


# Copyright

- The content of the corpus is not public and cannot be disclosed due to copyright protection. 
- The corpus is for research purposes only, and can only be used by those who have received a permission from the head of the Research Group in Stylistics.
