# Wordgourd problems

Known problems and oddities in the shipped texts.

- Orthography is not normalised anywhere; every text keeps its own convention.
- The scan-cut nodes carry OCR damage, editorial apparatus and printer's
  furniture, uncorrected. Some texts have little readable structure.
- The medieval and scan editions' texts keep editorial brackets, manuscript
  titla and combining marks.
- Printed line-head and verse numbering was trimmed where it appeared;
  saga-norse still carries chapter numbers interleaved with an editor's
  restarting numbering.
- Deduplication keys on parent documents. Two near-duplicate pairs cross the
  compile and exam split: cusco-quechua excerpt-080 (compile) and excerpt-122
  (exam); cornish excerpt-063 (compile) and excerpt-119 (exam). Each pair
  shares about 60 percent of the smaller text's five-grams.
- On a spliced text the manifest's source, url, title and parent describe
  only the receiver's own contribution; the donor named in src2 often
  supplied most of the bytes.
- Only valletta-maltese's candidate pool was screened for machine
  translation. The other 102 Wikipedia-cut nodes were not.
- cusco-quechua: 110 of 150 texts are synthetic, written by AI models from a
  named Spanish or Quechua Wikipedia article: 91 translated from a Spanish
  article, 19 replacing earlier machine-translated text. The review was also
  machine work; no human has vouched for the Quechua. The node is not a
  sample of the qu edition. One article supplies three texts, against the
  two-per-article cap.
- uzhhorod-rusyn: mostly the Subcarpathian standard, much of it in
  etymological-yat orthography, with a small Presov-standard admixture.
- homeric-greek: lunate sigmas were converted to the standard sigma forms;
  one character in one text was restored from a sigma to an omicron.
- medieval-latin: editorial apparatus from the printed editions remains:
  column markers, page-line numbers.
- ohrid-slavonic: two letter-table entries in the source's ASCII
  transcription were corrected in decoding.
- anglo-norman: two exam texts carry the editor's English alongside the
  Anglo-Norman.
- capetian-french and valois-french: nothing later than the 15th century.
- Four scan nodes carry a long-s repair: OCR-read f converted to s by rule.
  The rule has a known error rate; wrong conversions and wrong keeps remain
  in the texts.
- kahnawake-mohawk: Sulpician Mohawk writes /w/ as the digit 8.
- colonial-doctrina-quechua: nothing before 1600.
- massachusett and cherokee: each rests on a handful of works.
- In four of the seven colonial-print nodes the shipped texts cannot be
  rebuilt from the fetched bytes alone.
- hawaiian: not length-banded; its texts run shorter than the rest. No
  ʻokina or kahakō was inserted or stripped. The 1833 to 1912 sources predate
  the modern orthographic convention, so the node does not read like modern
  written Hawaiian; better sources were not found. No other
  Polynesian language ships in the corpus and from our measurements it carries
  enough texture to not be easily confusable and grab modern orthography as well.
- Cleaning was not exhaustive. Known survivors: a half-English text in
  cusco-quechua (excerpt-107), a Lua error message opening vilnius-yiddish
  excerpt-106, an English bibliography as zanzibari-swahili excerpt-069, wiki
  banners in texts of copenhagen-danish, parisian-french, cornish, veps and
  huesca-aragonese, a Latin species list and a Russian bibliography in
  cheboksary-chuvash (excerpt-059, excerpt-070), the same French list of
  painting titles in naga-bikol excerpt-117 and fiji-hindi excerpt-071, a
  half-Latin text in uzhhorod-rusyn excerpt-007, bare name lists in
  palermo-sicilian excerpt-115 and vicipaedian-latin excerpt-145, code fences
  in uzhhorod-rusyn excerpt-093 and diyarbakir-kurmanji excerpt-131, a dozen
  texts under 130 bytes that are titles or headers, and disambiguation
  hatnotes in maastricht-limburgish (two texts) and connacht-irish
  excerpt-102.
- cheboksary-chuvash writes ă, ĕ, ç and ÿ in Latin where the orthography
  uses Cyrillic ӑ, ӗ, ҫ and ӳ, mixed inside single words in most texts, as
  the source wiki writes it.
- cyrillic-shtokavian is almost entirely from the sr edition while
  latin-shtokavian pools bs, hr and sh, and the two nodes separate by script
  alone.
- The two Belarusian nodes differ in line structure enough to separate on
  formatting alone: the be-tarask payload is one line per article.
- A few cusco-quechua translations share their source article with
  madrid-spanish texts.
- The synthetic cusco-quechua texts use more Spanish loans than the node's
  real texts do.
- Not 100% sure Hamburg is the proper seat for German, but a place had to
  be named.
- The 25 legal nodes put two source documents on both sides of the compile
  and exam split: the node's constitution, 12 texts at slots 005, 032, 036,
  040, 053, 083, 090, 098, 114, 115, 116 and 144, and the UDHR, 2 texts at
  slots 067 and 133. No chunk is repeated. The other 121 nodes share no
  source document across the split.
- The 22 MultiEURLEX nodes stand on one set of 69 acts. For all 136
  legislation slots, excerpt-N is the same act, the same category and the
  same split in every one of the 22. Only the language differs. No act sits
  in one node's compile split and another node's exam split.
- brussels-irish carries regulations only, 136 of them, where every other
  brussels node carries a mix of regulations, decisions and directives. It
  is also off the parallel grid: its slots hold different acts.
- The treaty citation recurs inside every brussels node. The most widely
  shared eight-word run in a node appears in 15 to 23 of its 150 texts,
  median 20, and is the same formula in every language.
  commonwealth-english carries "in exercise of the powers conferred by
  sections" in 19 texts.
- Eight pairs inside a single node share 30 percent or more of their
  five-grams, the worst brussels-irish excerpt-119 and excerpt-150. Six
  cross the compile and exam split: washington-english excerpt-010 and
  excerpt-145, 64 percent of the smaller text's five-grams; brussels-romanian
  excerpt-094 and excerpt-109, 57; brussels-french excerpt-088 and
  excerpt-109, 56; brussels-romanian excerpt-084 and excerpt-109, 55;
  brussels-french excerpt-094 and excerpt-109, 55; brussels-finnish
  excerpt-043 and excerpt-127, 47.
- washington-english keeps the source's fixed-column line wrapping in 130 of
  its 150 texts, continued lines clustering at 66 to 72 characters. Every
  other node in the corpus puts one paragraph on one line.
- Federal Register apparatus survives in washington-english: FOR FURTHER
  INFORMATION CONTACT and SUPPLEMENTARY INFORMATION in 30 texts, AGENCY,
  ACTION and SUMMARY in 25, DATES in 24, ADDRESSES in 9, the section masthead
  in 3. GPO markup remains: the amendment bullet reduced to a bare 0 on its
  own line in 22 texts, the omitted-text marker in 13, [deg] for the degree
  sign in 8, and the placeholder [email protected] where an address stood in
  18.
- washington-english excerpt-089 is five regulatory-analysis boilerplate
  blocks and nothing else. excerpt-136 is a masthead, contact fields, a
  postal address and three telephone numbers. Fixed-width tables flattened
  into column-wise fragments leave dot-leader rows in 9 texts.
- commonwealth-english carries legislation.gov.uk furniture: Annotations and
  Commencement Information blocks in 12 texts, EXPLANATORY NOTE in 13, a bare
  "Statutory Instruments" line in 16, repealed provisions written as dot
  leaders in 5.
- commonwealth-english statutory-instrument mastheads lost their dates in 18
  texts, leaving "Made Laid before Parliament Coming into force" as one line,
  and glued the date to its label in 15 more. Quotation marks carry a space
  inside them in 17 texts.
- The four English UDHR texts carry spaces inside words from the source PDF's
  text layer.
- washington-english's 12 constitution texts keep the 1787 orthography:
  chuse, defence, encreased, hyphenated state names, and capitals on common
  nouns mid-sentence.
- Named individuals, telephone numbers and postal addresses stand in the
  washington-english contact fields and the commonwealth-english signature
  blocks. All are officials named in official capacity by the government's
  own publications; email addresses were already masked at the source.
- brussels-croatian writes the word "od" with the Cyrillic letter о in
  excerpt-003, 019, 061, 093, 101, 107, 135 and 150.
- Superscript ordinals were flattened on the way out of EUR-Lex:
  brussels-portuguese writes "N.o" and "n.o" in 105 texts and the correct
  form in 4, brussels-spanish writes "(CE) no" in 67.
- brussels-greek keeps the tonos on capitals in ALL-CAPS headings in 111
  texts, against the convention that drops it.
- brussels-maltese splits the "għ" digraph and neighbouring letters with
  spurious spaces in 56 texts, and its 10 constitution texts carry the print
  edition's running header.
- 19 of the 3,750 legal texts run above 15 percent digits, the highest at 21
  percent, where a table was flattened into running text.
- The 25 legal nodes are not length-banded. Their texts run 443 to 4,795
  projected runes.
- The legal nodes had no cleaning sweep. Their filters are cut and rename
  only, so everything above ships as the build emitted it.
