# Wordgourd changes

Much of the source material was full of noise, or incomplete as far as
language identification goes. To fix that, the material went through a lot of
changes and transformations, on the premise that artificial and clean is
better. Here is the list of operation types and what each was applied to, so
you know roughly what you are getting.

The curation work here was also AI assisted, treat it as needing verification by
your own eyes before you use it, I have verified and triple checked some of it but
the corpus is simply too big form me to have read it in full.

Where these documents say a text was read, the reader was mostly an AI model.

Each filter below names one kind of change, not a moment in a history: the
same filter can be run again on new material. A node's row in the table lists
the filters applied to it, so you can decide what you accept and what you
would rather redo from raw. Where the material comes from, and under what
licence, is in `SOURCES.md`.

## The rule every node was cut by

One chunking rule across the corpus. Length is measured in projected runes:
code points after a projection in which combining marks count as letters,
zero-width non-joiner is a boundary, and zero-width joiner is deleted. The
rule has a floor and a hard cap; a chunk below the floor is never emitted at
cutting time, so there are no trailing remainders, though banding later cuts
shorts below the floor. A chunk must clear a letter-mass gate. Exact
plus shingle deduplication runs inside the node. A cap limits how many texts
one source document may supply. Every node ships 150 texts, 100 compile and 50
exam. In 121 nodes the two splits share no source document. In the 25 legal
nodes they share two, the constitution and the UDHR, which are one document
each and are chunked across both splits; no chunk is repeated. `PROBLEMS.md`
carries the count. Each build tightens this rule where its material demanded
it.

**The nodes are length-banded.** Each node's own 150 texts are redistributed
into shorts, mediums and larges; nothing is added or removed. The manifest's
`band`, `role`, `src1` and `src2` columns say what each text is and, for a
spliced large, which two texts it glues. 26 nodes sit outside the banding:
hawaiian, whose texts are shorter, and the 25 legal nodes, which were cut to
their own length rule. All 26 ship band `u` and role `unbanded`, with their
own recorded length windows.

**A large that glues two licences ships under the stricter of the two.**
medieval-latin can glue CC-BY-4.0 to CC-BY-SA-4.0, and four of the five
medieval nodes carry more than one source. The stricter licence is
CC-BY-SA-4.0, which the corpus already declares; `src2` names the donor text,
whose row carries its own source, licence and receipt.

## The filters

**cut.** Selection and chunking from the source material, under the rule
above. Every node.

**mt-screen.** The candidate pool screened for machine translation before
cutting: every page carrying the edition's own machine-translation tag
dropped. valletta-maltese only; no other pool was screened, and that
inconsistency is stated in the material section.

**markdown-strip.** Heading lines, table rows, list markers and reference
markers stripped from the payloads; the prose they wrapped kept.

**duplicate-collapse.** Duplicate articles removed from the pool: by page
identity, exact content, and near identity.

**chrome-strip.** Wiki chrome removed: conversion leakage (LaTeX spans,
unconverted templates, wikilink wrappers, bare URLs), maintenance blocks,
dialect banners, stub notices, and flattened taxonomy and script boxes.

**template-kill.** Whole articles that are template output rather than
writing dropped: skeletons that match once digits and capitalised tokens are
blanked, and articles mostly reused from others.

**containment-dedup.** A standalone article whose whole content sits inside a
larger article of the same edition dropped; nothing is ever cut out of the
survivor.

**script-split.** Texts partitioned into nodes by dominant script, with
parents qualified by source edition.

**reassignment.** Documents moved between neighbouring nodes where source
metadata could not decide membership; documents fitting neither node cut;
both nodes refilled.

**register-cut.** Texts reading as a register other than the node's own prose
dropped and the slots refilled.

**source-merge.** A node filled from two source layers where one alone could
not reach 150 texts.

**deep-clean.** Cleaning applied to the packaged texts: residual markup,
bidirectional display marks inside words, off-script and off-family blocks,
texts that are mostly numbers, printed line-head numbering, English
furniture, name-list runs, embedded foreign blocks. Every flagged text read
before condemnation; condemned slots refilled from unused candidates, with a
refill held to a stricter bar than a survivor.

**ai-translation.** Texts made by AI models from named source articles enter
the node. cusco-quechua only, stated in full in the material section.

**content-removal.** Texts removed for what they say, and the slots
refilled. The removed texts asserted racial pseudo-science as fact, or a
racial curse as doctrine.

**banding.** The node's own 150 texts repackaged into shorts, mediums and
larges; nothing added or removed.

**rename.** The node's directory renamed; the texts untouched.

## How each material was cut

### From Wikipedia

103 nodes, 15,450 texts.

**Cutting**: the corpus rule, two texts per source article, a pool cap per
node.

**In the cleaning sweeps, every flagged text was read before it was
condemned**, and every condemned slot was refilled from articles the build
had walked and never used. A refill is held to a stricter bar than a
survivor: any flag disqualifies it, where a survivor only dies on a verdict.

### From critical editions

Five nodes: ciceronian-latin, medieval-latin, homeric-greek,
new-testament-greek, biblical-hebrew. Nothing here is
generated, translated or paraphrased.

**Extraction.** Sources fetched once, never modified. From the TEI, `<note>`
elements are dropped, which removes the critical apparatus. Language is read
off the source filename, never guessed from the text, and translation
editions are excluded. From the Hebrew source, four rulings: vowel pointing
kept; cantillation accents dropped; where the tradition gives a read form
beside a written one, the read form is taken; the source's morpheme
segmentation marks removed as an editorial layer, not the codex. From the
Wikisource dump, provenance headers and database key lines are dropped, and
HTML entities are unescaped twice, because one pass leaves escaped entities
standing as fake Latin words.

**Selection.**

- **ciceronian-latin** takes the classical Latin text groups and refuses Late
  Latin authors.
- **homeric-greek** takes the earlier Greek authors and holds out the Jewish
  and Christian Koine, New Testament and Septuagint included, so the two Greek
  nodes do not train against each other.
- **medieval-latin** refuses anything composed before 601, and refuses the
  humanists by name: their dates fall in the window, their Latin is not the
  register. One author is one group, with the key folded so two spellings of a
  name are one author.

**Cutting**: the corpus rule with five tightenings: a per-group cap on texts
from one author or book, the compile/exam split at group level rather than
document level, the folded group key, original-orthography candidates walked
before normalised ones, a stricter near-duplicate bar than the other builds.

### From medieval corpora and scans

Five nodes: saga-norse, capetian-french, valois-french, anglo-norman,
ohrid-slavonic.
anglo-norman takes 87 texts from BFM and 63 from Internet Archive scans;
capetian-french and valois-french take BFM, ohrid-slavonic the Helsinki Church
Slavonic corpus, saga-norse the scans. Nothing here is generated, translated
or paraphrased.

**Acquisition.** The BFM bodies came through the route BFM's own robots.txt
leaves open; the disallowed routes were not used. One long BFM text failed to
render and is absent.

**The CCMH texts are decoded, not edited.** They ship upstream as an ASCII
transcription. The conversion reuses the source's own tables, recovers tokens
the strict decoder rejects, and corrects two letter-table entries that mapped
to historic letterforms instead of standard Old Church Slavonic letters. Every
other letter is left as delivered.

**The scanned nodes are gated per window, not per document**: a scanned page
carries the editor's English introduction, Latin apparatus, glossaries,
sometimes a facing translation. Only maximal runs of accepted lines survive,
and scanning-house furniture is dropped.

- **saga-norse** is gated on orthography. A saga edition prints either
  normalised Old Norse or modern Icelandic spelling, and the two differ on
  every diagnostic word, so the surface decides and the date does not. Two
  corpora that convert everything to the modern column are banned.
- **anglo-norman** is gated on Oil function words plus at least one insular
  spelling system, with no other language rivalling them. The word list is
  deliberately the forms shared with continental Old French: this gate
  separates languages, not dialects. Which dialect the node is comes from the
  choice of books.
- **capetian-french and valois-french** are not gated by surface at all: BFM's
  own metadata routes them at composition year 1340.

**Cutting**: the corpus rule, with the per-document cap raised for the two
nodes with few documents.

### From colonial print and Wikisource

Seven nodes: tenochtitlan-nahuatl, colonial-doctrina-quechua,
kahnawake-mohawk, massachusett, cherokee, varanasi-sanskrit, abbasid-arabic.
Nothing here is generated, translated or paraphrased; the only character changes are the
long-s repairs and the numbering trim below.

**Selection.** `parent` is the edition and `family` is the work: three
printings of one translation are three parents, one family. Caps and the
compile/exam split key off family, so no work lands on both sides. Selection
is breadth first, so a thin node spreads across what it has. Excluded by name,
each after being read: items filed under the wrong language, lexicons that are
headword lists, and scans whose OCR has no word structure left.

**Gating.** Every source here is at least bilingual: doctrinas print Spanish
in facing columns, scripture reprints carry English front matter, the grammars
are mostly Spanish. Lines are scored on script, letter mass, coloniser
function words, word length and a per-node marker kit; only maximal runs of
accepted lines survive. The word lists are per node, because short function
words collide across the languages in play.

**Cutting**: the corpus rule, with sentence units extended beyond Latin
punctuation and a stricter near-duplicate bar, because liturgical print
repeats itself. A chunk carrying a script that cannot occur in the node is
refused, and the line gate runs again over the whole chunk. **The first chunk
of every archive document is dropped**: a scanned book opens with its title
page and dedication in the language of the book.

### hawaiian

150 texts of ʻŌlelo Hawaiʻi prose, 1833 to 1912. Nothing
here is generated, translated or paraphrased.

**Cutting.** Text is normalised to NFC with LF endings, no BOM, no control
characters, no soft hyphens. Line-break hyphenation in scanned books is
rejoined; page numbers and running headers are dropped. **Newspaper pages are
reduced to their maximal runs of Hawaiian lines**: those pages are bilingual
and the English columns are not wanted. Chunking is one rule for every source:
short paragraphs merge forward, very long ones split at sentence boundaries,
text accumulates to a floor and is emitted, with a ceiling and a dropped
trailing remainder. One book gives at most 12 chunks, and compile and exam
share no parent document. A chunk must clear gates on letter mass, Hawaiian
function-word share, non-Hawaiian letter share, English function-word share,
well-formed word share, Latin script share and scanner furniture.
Deduplication is exact match plus shingle similarity across the node.

### From legal publication

25 nodes, 3,750 texts: 23 brussels nodes, washington-english and
commonwealth-english. Nothing here is generated, translated or paraphrased,
and no character was changed on entry.

**Sources.** EU legislation through MultiEURLEX over EUR-Lex, with the Irish
expression from Cellar because MultiEURLEX has no Irish. US Federal Register
rules and public laws through govinfo. UK statutory instruments and Acts from
legislation.gov.uk. Each node also takes 12 texts from its jurisdiction's
constitution and 2 from the official UN translation of the Universal
Declaration of Human Rights.

**Selection is parallel across the EU tongues.** An act qualifies only if
every tongue yields enough chunks; a fixed 69-act plan then fills the same
slot with the same act in every tongue, chunks picked by shared relative
position. For all 136 legislation slots, excerpt-N is the same act, category
and split in all 22 MultiEURLEX nodes. brussels-irish stands on 69
regulations only, against the other nodes' regulation, decision and directive
mix.

**Cutting**: a length rule of the build's own, measured in characters rather
than projected runes: paragraphs under 40 characters merge forward, a
paragraph over 5 kB splits at sentence boundaries, paragraphs accumulate to
1500 bytes and emit, never past 5000, and a trailing remainder under 500 is
dropped. A quality gate holds letters at or above 60 percent of non-space
characters, which drops tables and number dumps. Deduplication is exact match
plus 5-gram shingle Jaccard at 0.5, scoped per node across both splits. Two
texts per source document. Schedules are excluded from every
legislation.gov.uk extraction.

**Apparatus dropped from the US texts**: the bracketed issue header, the
typographic rules, the page markers, the filing footer, the billing code and
the omitted-graphic markers. The source's own hard line wrapping is kept, and
`PROBLEMS.md` records that.

**These nodes are not banded.** They ship as cut, at band `u`.

## What was done to each node

| Node | Filters |
| --- | --- |
| abbasid-arabic | cut, deep-clean, banding, rename |
| addis-ababa-amharic | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| alemannic | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| almaty-kazakh | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| amritsar-punjabi | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| amsterdam-dutch | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| anglo-norman | cut, reassignment, deep-clean, banding |
| asuncion-guarani | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| athenian-greek | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| baku-azerbaijani | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| bangkok-thai | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| barcelona-catalan | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, banding, rename |
| beijing-mandarin | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| biblical-hebrew | cut, banding |
| bilbao-basque | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| bratislava-slovak | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| brussels-bulgarian | cut, rename |
| brussels-croatian | cut, rename |
| brussels-czech | cut, rename |
| brussels-danish | cut, rename |
| brussels-dutch | cut, rename |
| brussels-estonian | cut, rename |
| brussels-finnish | cut, rename |
| brussels-french | cut, rename |
| brussels-german | cut, rename |
| brussels-greek | cut, rename |
| brussels-hungarian | cut, rename |
| brussels-irish | cut, rename |
| brussels-italian | cut, rename |
| brussels-latvian | cut, rename |
| brussels-lithuanian | cut, rename |
| brussels-maltese | cut, rename |
| brussels-polish | cut, rename |
| brussels-portuguese | cut, rename |
| brussels-romanian | cut, rename |
| brussels-slovak | cut, rename |
| brussels-slovene | cut, rename |
| brussels-spanish | cut, rename |
| brussels-swedish | cut, rename |
| bucharest-romanian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, deep-clean, banding, rename |
| budapest-hungarian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, banding, rename |
| cairo-academy-arabic | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| cape-afrikaans | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| capetian-french | cut, reassignment, banding, rename |
| cheboksary-chuvash | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| chennai-tamil | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| cherokee | cut, deep-clean, banding |
| ciceronian-latin | cut, banding, rename |
| colombo-sinhala | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| colonial-doctrina-quechua | cut, deep-clean, banding, rename |
| commonwealth-english | cut, rename |
| compostela-galician | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| connacht-irish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| copenhagen-danish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| cornish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| cusco-quechua | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, ai-translation, banding, rename |
| cyrillic-shtokavian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, script-split, deep-clean, banding |
| delhi-hindi | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| diyarbakir-kurmanji | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| dushanbe-tajik | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| esperanto | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| fiji-hindi | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| florentine-italian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, deep-clean, banding, rename |
| gwynedd-welsh | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| hamburg-german | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| hanoi-vietnamese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| hawaiian | cut, content-removal |
| hebridean-gaelic | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| helsinki-finnish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| homeric-greek | cut, deep-clean, banding, rename |
| hong-kong-cantonese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| huesca-aragonese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| hyderabad-sindhi | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| ido | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, banding, rename |
| istanbul-turkish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| jakarta-indonesian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, deep-clean, banding, rename |
| johor-malay | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, deep-clean, banding, rename |
| jorhat-assamese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| kahnawake-mohawk | cut, deep-clean, banding, rename |
| kandahar-pashto | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| kathmandu-nepali | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| kaunas-lithuanian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| kolkata-bengali | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| kottayam-malayalam | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| kyiv-ukrainian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, banding, rename |
| latin-shtokavian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, script-split, deep-clean, banding |
| leeuwarden-frisian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| leon-breton | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| ljubljana-slovene | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| luxembourgish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| maastricht-limburgish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| madrid-spanish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, deep-clean, banding, rename |
| manila-tagalog | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, content-removal, banding, rename |
| massachusett | cut, deep-clean, banding, rename |
| medieval-latin | cut, deep-clean, banding |
| minsk-belarusian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| moscow-russian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| mysore-kannada | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| naga-bikol | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| new-testament-greek | cut, banding, rename |
| ohrid-slavonic | cut, banding, rename |
| oslo-norwegian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| oviedo-asturian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| palermo-sicilian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| parisian-french | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, banding, rename |
| prague-czech | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| pune-marathi | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| reykjavik-icelandic | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, banding, rename |
| riga-latvian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| rio-portuguese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, banding, rename |
| saga-norse | cut, deep-clean, banding, rename |
| samogitian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, source-merge, deep-clean, banding, rename |
| seoul-korean | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| skopje-macedonian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| sofia-bulgarian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| stockholm-swedish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, banding, rename |
| sulaymaniyah-sorani | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| surakarta-javanese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| tallinn-estonian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| tashkent-uzbek | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| tbilisi-georgian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| tehrani-persian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| tel-aviv-hebrew | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| tenochtitlan-nahuatl | cut, deep-clean, banding, rename |
| tirana-albanian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| tokyo-japanese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| toulouse-occitan | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, banding, rename |
| ufa-bashkir | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| ulaanbaatar-mongolian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| uzhhorod-rusyn | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| valletta-maltese | cut, mt-screen, deep-clean, banding, rename |
| valois-french | cut, deep-clean, banding, rename |
| varanasi-sanskrit | cut, deep-clean, banding, rename |
| veps | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| vestland-norwegian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| vicipaedian-latin | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, register-cut, deep-clean, banding, rename |
| vigan-ilocano | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| vijayawada-telugu | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| vilnius-belarusian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| vilnius-yiddish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| warsaw-polish | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| washington-english | cut, rename |
| yakutsk-sakha | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| yangon-burmese | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| yerevan-armenian | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |
| zanzibari-swahili | cut, markdown-strip, duplicate-collapse, chrome-strip, template-kill, containment-dedup, deep-clean, banding, rename |

## Tried and reverted

**The shared-vocabulary cut.** Cut the word types shared by most editions of
a script family. Tried but seemed to not be worth it according to local LID
extraction efforts. Not in the corpus.

## Licence

The corpus is CC-BY-SA-4.0. The licence asks that changes to the source texts
be indicated; this file is that indication.
