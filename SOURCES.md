# Wordgourd sources

All 21,900 texts are cut or derived from existing sources. This lists every
source, the licence it carries, and where the licence was read.

A node is one directory under `tree/`: `excerpt-001` to `excerpt-100` are the
compile split, 101 to 150 the exam split. A node is named for a place, an era,
or the text it was cut from; `NAMES.tsv` maps every node to its old id, its
ISO advisory code, and the reason for the name.

The texts are transformed, not verbatim: every one is a chunk of a source
document that passed a language gate and a chunking rule, some with recorded
character repairs. Quality varies by node. Texts cut from old scans keep the
defects of their capture, OCR damage, editorial apparatus, printer's
furniture, and some have little readable structure at all, shipped as
captured. `CHANGES.md` says what was done to the material; `PROBLEMS.md` lists
what is known to be wrong with it.

## Licence of the whole corpus

**CC-BY-SA-4.0.** The strongest term in the mix is ShareAlike, from the
Wikipedia and Wikisource material, so the package as a whole is CC-BY-SA-4.0.
Nothing noncommercial, nothing no-derivatives, nothing unstated is inside.

Individual nodes are freer than the package. Thirty-three carry no ShareAlike
obligation and can be redistributed alone under any terms: tenochtitlan-nahuatl,
colonial-doctrina-quechua, kahnawake-mohawk, massachusett, cherokee, hawaiian,
saga-norse, anglo-norman, ohrid-slavonic, biblical-hebrew,
new-testament-greek, capetian-french, valois-french, washington-english,
commonwealth-english, and the eighteen brussels nodes brussels-croatian,
brussels-dutch, brussels-estonian, brussels-finnish, brussels-french,
brussels-german, brussels-irish, brussels-italian, brussels-latvian,
brussels-lithuanian, brussels-maltese, brussels-polish, brussels-portuguese,
brussels-romanian, brussels-slovak, brussels-slovene, brussels-spanish and
brussels-swedish. The other five brussels nodes (brussels-bulgarian,
brussels-czech, brussels-danish, brussels-greek, brussels-hungarian) take
their constitution texts from a Wikisource transcription and carry ShareAlike
on those rows. hawaiian has no copyright licence
to comply with at all. The per-row licence column says which node is which.
Sources with no stated licence were not used.

What CC-BY-SA-4.0 asks of anything built on this corpus:

1. **Attribution.** Credit the source named on the row: Wikipedia and its
   contributors (with FineWiki as the intermediate dataset) for the nodes cut
   from Wikipedia, the list below for everything else. Every row of
   `tree/manifest.tsv` carries its source URL or page id. Link the licence.
2. **ShareAlike.** Derivatives of the ShareAlike-bearing texts must ship under
   CC-BY-SA-4.0 or compatible. This binds derived corpora. It does not bind
   measurements or statistics, which are facts, not derivative works.
3. **Indicate changes.** `CHANGES.md` is the change record. Any further stage
   that cleans, cuts, deduplicates or normalises these texts must say so the
   same way.

**110 of the 150 cusco-quechua texts are synthetic: made by AI models, not
cut.** Each derives from a named Spanish or Quechua Wikipedia article. The
making and the per-text review were both machine work. They are derivative works of CC-BY-SA articles and ship under
the same licence; the `source` column names the translation layer on every
row. No other node carries written text.

## Attribution owed on redistribution

- Wikipedia and its contributors, and FineWiki (HuggingFaceFW).
- Meta-Wiki contributors, for "List of articles every Wikipedia should have"
  and its /Expanded subpages, CC-BY-SA. Candidate selection is keyed to those
  lists.
- Perseus Digital Library, Tufts University (canonical-latinLit,
  canonical-greekLit).
- Open Greek and Latin / First1KGreek.
- Society of Biblical Literature and Logos Bible Software (SBLGNT, ed. Michael
  W. Holmes, 2010).
- Open Scriptures Hebrew Bible, github.com/openscriptures/morphhb.
- Wikisource contributors (la.wikisource.org, sa.wikisource.org,
  ar.wikisource.org).
- Croatiae auctores Latini, Faculty of Humanities and Social Sciences,
  University of Zagreb.
- Monumenta Germaniae Historica and Bayerische Staatsbibliothek, Munich
  (openMGH).
- Base de Francais Medieval (BFM 2022), Lyon, ENS de Lyon, Laboratoire IHRIM,
  txm.bfm-corpus.org. BFM states the wording it wants at
  http://bfm.ens-lyon.fr/spip.php?article281.
- Corpus Cyrillo-Methodianum Helsingiense, University of Helsinki, via
  github.com/cltk/old_church_slavonic_ccmh.
- The holding library named on each Internet Archive item page.
- Library of Congress, Chronicling America.
- eBible.org.
- Biblioteca Nacional del Peru, BNP Digital.
- The European Union, via EUR-Lex, with MultiEURLEX (coastalcph) as the
  intermediate dataset. EUR-Lex asks that the source be acknowledged and
  states that reuse does not imply the Commission's endorsement.
- The National Archives (UK), for material under the Open Government Licence
  v3.0. OGL v3 asks for the licensor's name, the title of the material, a
  copyright notice and a link to the licence.
- Legislation.gov.uk, for statutory instruments and Acts.
- The United Nations, for the official translations of the Universal
  Declaration of Human Rights (OHCHR, and UNRIC for Finnish).
- Wikisource contributors (bg, cs, da, el, hu), for the constitution
  transcriptions in five brussels nodes.
- The national official publishers named on the corrector rows: Narodne
  novine, wetten.overheid.nl, Riigi Teataja via WIPO Lex, Conseil
  constitutionnel, Bundesamt fuer Justiz, Irish Statute Book, Corte
  costituzionale, Latvijas Vestnesis, Seimas of Lithuania, legislation.mt,
  Sejm Rzeczypospolitej Polskiej, Assembleia da Republica, Camera
  Deputatilor, Slov-Lex, Uradni list Republike Slovenije, Boletin Oficial
  del Estado, Sveriges riksdag.

## Wikipedia

103 nodes, 15,450 texts, from modern-language Wikipedia editions. 101 nodes
are one edition each; latin-shtokavian and cyrillic-shtokavian are script
nodes pooled from four editions.

| Source | Licence | Receipt | Nodes | Texts |
| --- | --- | --- | --- | --- |
| FineWiki (Wikipedia article text) | CC-BY-SA-4.0, also GFDL | https://huggingface.co/datasets/HuggingFaceFW/finewiki | 102 | 15,083 |
| be_x_oldwiki Cirrus dump (Wikipedia) | CC-BY-SA-4.0, also GFDL | https://dumps.wikimedia.org/other/cirrus_search_index/20260809/index_name=be_x_oldwiki_content/be_x_oldwiki_content-20260809-00000.json.bz2 | 1 | 150 |
| bat_smgwiki Cirrus dump (Wikipedia) | CC-BY-SA-4.0, also GFDL | https://dumps.wikimedia.org/other/cirrus_search_index/20260809/index_name=bat_smgwiki_content/bat_smgwiki_content-20260809-00000.json.bz2 | 1 | 107 |
| Wordgourd translation from FineWiki (Wikipedia), es payload | CC-BY-SA-4.0, also GFDL | https://huggingface.co/datasets/HuggingFaceFW/finewiki | 1 | 91 |
| Wordgourd translation from FineWiki (Wikipedia), qu payload | CC-BY-SA-4.0, also GFDL | https://huggingface.co/datasets/HuggingFaceFW/finewiki | 1 | 19 |

Two nodes draw on more than one row: samogitian takes 43 texts from FineWiki
and 107 from the Cirrus dump, cusco-quechua 40 from FineWiki and 110 from the
two translation layers.

The roster is the tier A and tier B editions of the Wikipedia edition-quality
table, minus the nine anglic-family editions, deliberately absent from the
Wikipedia roster: **en, simple, sco, ang, tpi, jam, srn, pcm, gpe**. The two
English nodes in the corpus, washington-english and commonwealth-english, are
cut from legal publication, not from Wikipedia. valletta-maltese is
represented since that one isn't covered by my other corpus, Wordhoard. (https://github.com/AndreiNicolaeEne/Wordhoard)

The vilnius-belarusian rows carry a page id rather than a URL: that edition
came from a Cirrus dump, not FineWiki.

**The two Shtokavian nodes.** The bs, hr, sh and sr editions do not ship as
edition nodes. Their texts are split by dominant script into latin-shtokavian
and cyrillic-shtokavian, 150 each, with `parent` qualified by edition because
a Wikidata id names a different article in each, so each text's source
edition is on its own manifest row.

### The acquisition

The nodes cut from Wikipedia were acquired 2026-08-15 from FineWiki.
be-tarask (Belarusian in Taraskievica orthography) has no FineWiki subset and
came from the be_x_oldwiki Cirrus dump named in the table. **The be-tarask
payload is one line per article**, so its paragraph units are sentences where
every other edition splits on lines; that is the only per-edition departure.

The raw payloads are not part of this repository. Every packaged text's
source article is identified in `tree/manifest.tsv` by URL or page id, so the
originals can be fetched again.

**Candidate selection.** Candidates are matched by Wikidata id, not by title.
Priority runs down Meta-Wiki's "List of articles every Wikipedia should
have", the 1,000 core topics in list order, then the /Expanded list of 9,000
more. The cap is 1,500 candidates per edition; where an edition has fewer,
everything that exists was taken. The node target is 150 texts, so the cap is
deliberate overshoot for the aggressive cutting downstream.

## Wikisource

Transcriptions of published works, made by Wikisource contributors. The
underlying works are out of copyright by age; only the transcription layer
carries CC-BY-SA-4.0.

| Source | Licence | Receipt | Node | Texts |
| --- | --- | --- | --- | --- |
| la.wikisource | CC-BY-SA-4.0 | https://la.wikisource.org/w/api.php?action=query&meta=siteinfo&siprop=rightsinfo | medieval-latin | 65 |
| sa.wikisource.org | CC-BY-SA-4.0 | https://sa.wikisource.org/w/api.php?action=query&meta=siteinfo&siprop=rightsinfo&format=json | varanasi-sanskrit | 150 |
| ar.wikisource.org | CC-BY-SA-4.0 | https://ar.wikisource.org/w/api.php?action=query&meta=siteinfo&siprop=rightsinfo&format=json | abbasid-arabic | 150 |

## Scholarly corpora and critical editions

Classical, medieval and biblical texts from critical editions, scholarly TEI
and research corpora.

| Source | Licence | Receipt | Nodes | Texts |
| --- | --- | --- | --- | --- |
| perseus-latinLit | CC-BY-SA-4.0 | https://github.com/PerseusDL/canonical-latinLit/blob/master/license.md | ciceronian-latin | 150 |
| perseus-greekLit | CC-BY-SA-4.0 | https://github.com/PerseusDL/canonical-greekLit/blob/master/license.md | homeric-greek | 89 |
| first1kGreek | CC-BY-SA-4.0 | https://github.com/OpenGreekAndLatin/First1KGreek/blob/master/license.md | homeric-greek | 61 |
| SBLGNT | CC-BY-4.0 | https://github.com/Faithlife/SBLGNT/blob/master/LICENSE | new-testament-greek | 150 |
| openscriptures/morphhb (WLC) | WLC text public domain, OSHB layer CC-BY-4.0 | https://github.com/openscriptures/morphhb/blob/master/LICENSE.md | biblical-hebrew | 150 |
| openMGH | CC-BY-4.0 | https://www.mgh.de/de/mgh-digital/openmgh | medieval-latin | 83 |
| CroALa | CC-BY-4.0 | https://github.com/nevenjovanovic/croatiae-auctores-latini-textus/blob/master/LICENSE.md | medieval-latin | 2 |
| BFM 2022, Base de Francais Medieval, ENS de Lyon / IHRIM | Licence Ouverte Etalab 2.0 | per text, the catalogue record at http://txm-bfm.huma-num.fr/txm/catalog/<name>, 151 distinct | capetian-french, valois-french, anglo-norman | 387 |
| Corpus Cyrillo-Methodianum Helsingiense, via cltk/old_church_slavonic_ccmh | Public Domain Mark 1.0 | https://raw.githubusercontent.com/cltk/old_church_slavonic_ccmh/master/LICENSE.md | ohrid-slavonic | 150 |

Two licence facts:

1. Most BFM texts rest on a reference edition published after 1929, and some
   carry none at all. BFM states "Corps de texte : Domaine public, licence
   Etalab" for every one, on the position that the medieval text is public
   domain and only the critical apparatus attracts new copyright, licensed
   separately as CC BY-NC-SA 3.0 FR. The export used here contains no
   apparatus. BFM's position is taken at face value; this is not an argument
   from age.
2. The CCMH Public Domain Mark is asserted by the CLTK mirror, not by
   Helsinki, whose own site is gone.

## Scan archives

Scans of printed books, colonial and mission-press imprints, and newspaper
pages.

| Source | Licence | Receipt | Nodes | Texts |
| --- | --- | --- | --- | --- |
| Internet Archive scans, all editions published before 1929 | public domain by edition date | per item, https://archive.org/details/<id>, 91 distinct | saga-norse, anglo-norman | 213 |
| Internet Archive scans, all editions published before 1929 | public domain | per item, https://archive.org/details/<id>, 95 distinct | tenochtitlan-nahuatl, colonial-doctrina-quechua, kahnawake-mohawk, massachusett, cherokee | 660 |
| Internet Archive scans of Hawaiian books printed 1833 to 1903 | public domain | per item, https://archive.org/details/<id>, 23 distinct | hawaiian | 100 |
| Biblioteca Nacional del Peru (BNP Digital) | public domain | per item, https://hdl.handle.net/20.500.14428/<id>, 27 distinct | colonial-doctrina-quechua | 90 |
| Chronicling America (Library of Congress) newspaper pages, 1844 to 1912 | public domain | https://www.loc.gov/collections/chronicling-america/about-this-collection/rights-and-access/ | hawaiian | 38 |

Where a holding library states its own rights position, the manifest's
`licence_basis` column quotes it ("NOT_IN_COPYRIGHT", "The Library of Congress
is unaware of any copyright restrictions for this item", and so on); where it
does not, the basis is publication in the United States before 1929. The BNP
items carry `dc.rights.uri` Public Domain Mark 1.0 and a persistent handle as
the receipt. The Chronicling America basis is the National Digital Newspaper
Program's own rule: it digitises only content free of known copyright
restrictions.

## eBible.org

| Source | Licence | Receipt | Node | Texts |
| --- | --- | --- | --- | --- |
| eBible.org, Baibala Hemolele, the 1868 revision | public domain, declared on the translation's own page | https://ebible.org/details.php?id=haw1868&all=1 | hawaiian | 12 |

## Legal publication

25 nodes, 3,750 texts, cut from the legal publication of the European Union,
the United States and the United Kingdom. The 23 brussels nodes are one EU
official language each; washington-english and commonwealth-english are the
two anglophone nodes.

136 of each node's 150 texts come from that jurisdiction's secondary and
primary legislation. The remaining 14 come from the country's constitution
(12) and the official translation of the Universal Declaration of Human
Rights (2).

| Source | Licence | Receipt | Nodes | Texts |
| --- | --- | --- | --- | --- |
| MultiEURLEX (coastalcph), the parquet branch, over EUR-Lex | EUR-Lex reuse, Decision 2011/833/EU (source acknowledged) | https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32011D0833 | 22 | 2,992 |
| EUR-Lex / Cellar, the Irish expression | EUR-Lex reuse, Decision 2011/833/EU (source acknowledged) | https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32011D0833 | 1 | 136 |
| EUR-Lex national implementing measure, the Finlex print of 731/1999 | EUR-Lex reuse, Decision 2011/833/EU (source acknowledged) | https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32011D0833 | 1 | 12 |
| legislation.gov.uk, statutory instruments and Acts | Open Government Licence v3.0 | https://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/ | 1 | 148 |
| Federal Register, the govinfo issue text | US public domain | https://uscode.house.gov/view.xhtml?req=granuleid:USC-prelim-title17-section105 | 1 | 130 |
| govinfo PLAW, public laws of Congresses 111 to 114 | US public domain | https://uscode.house.gov/view.xhtml?req=granuleid:USC-prelim-title17-section105 | 1 | 6 |
| US National Archives, the 1787 Constitution transcript | US public domain | https://uscode.house.gov/view.xhtml?req=granuleid:USC-prelim-title17-section105 | 1 | 12 |
| OHCHR and UNRIC, official UN translations of the UDHR | UN, free reproduction with attribution | https://www.un.org/en/about-us/copyright | 24 | 48 |
| Wikisource (bg, cs, da, el, hu), constitution transcriptions | CC-BY-SA-4.0 on the transcription | per edition, https://<code>.wikisource.org/w/api.php?action=query&meta=siteinfo&siprop=rightsinfo&format=json | 5 | 60 |
| National official publishers, 18 distinct sources | national-law copyright exclusion, or the publisher's own reuse terms | per source, the publisher's page | 17 | 206 |

**The EU selection is parallel.** The 22 MultiEURLEX nodes stand on one
identical set of 69 acts. For all 136 legislation slots, excerpt-N is the same
act, the same category and the same split in all 22 tongues. Only the language
differs, so no two of those texts share bytes. brussels-irish is outside that
set: Irish is absent from MultiEURLEX and came from Cellar, on 69 regulations
where the other nodes carry a mix of regulations, decisions and directives.

Three licence facts:

1. EUR-Lex reuse rests on Commission Decision 2011/833/EU. It asks that the
   source be acknowledged and that reuse not be presented as the
   Commission's endorsement. It carries no ShareAlike obligation.
2. Open Government Licence v3.0 asks for the licensor's name, the title of
   the material, a copyright notice and a link to the licence. It carries no
   ShareAlike obligation.
3. The national corrector sources are national-law positions, not published
   licences: statutory text is excluded from copyright in most of these
   jurisdictions, and the licence column quotes the provision where the
   source states one. For those rows the receipt is the publisher's own page,
   because that is where the text and its status were read. Five nodes take
   their constitution from a Wikisource transcription instead, and that
   transcription layer is CC-BY-SA-4.0.

## The tables

`SOURCES.tsv` at the repository root, 836 rows, tab separated:

    node  source  licence  licence_receipt  texts

One row per distinct source within a node, and one row per receipt where
receipts are per item, so a source with per-item receipts spans several rows
under the same source string: sum the `texts` column rather than keying on
node and source. It names every individual Internet Archive item, every BNP
item, every BFM text, every Wikisource work. The tables above roll it up.

`tree/manifest.tsv` carries one row per text: source, url, licence, receipt,
parent, title, checksum, size, and the length band it ships in.

On a spliced text (`role` receiver), `source`, `url`, `title` and `parent`
describe the receiver's own contribution, and the donor named in `src2` often
supplied most of the bytes; the donor's own row carries its article.

Column meanings the names do not state. `band`: s, m or l for short, medium
or large, u for the 26 unbanded nodes. `role`: keep, donor, receiver, or
unbanded.
`src1` and `src2`: the slots a banded text is built from. `cut_k`: how many
paragraphs the cut kept. `cut_end`: head or tail, which end it kept.
`cut_span`: the kept paragraph range. `share`: the kept fraction of the
source text. `glue_order`: which part opens a spliced file, receiver (its own
cut) or remainder (the donor's leftover). `paras`: paragraph count. `runes`:
length in projected runes, defined in `CHANGES.md`.
