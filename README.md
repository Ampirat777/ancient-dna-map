# Ancient DNA samples by find spot

An interactive map of about 22,000 ancient human genomes, from the Palaeolithic
to the recent past. Each dot is one individual. Hover or tap it for its card:
date and how it was dated, culture, site, sex, Y-DNA and mtDNA haplogroups,
data quality and source. Clicking also lists everyone buried at the same site
(on a phone, use the card's "List all ... samples at this site"), and the
sortable table shows every sample that matches your search.

**Open the map:** https://ampirat777.github.io/ancient-dna-map/

## What is on the map

| Marker | Samples | Location |
|---|---|---|
| ● filled dot | 20,650 published individuals from the Allen Ancient DNA Resource (AADR v66) | the coordinates AADR records for the site, which are sometimes the nearest town |
| ● filled dot, card badge *not in AADR v66* | 817 published individuals not yet in AADR, each taken from its own paper (589 from Hungary and Romania, 224 from Spain, 4 from the Lower Rhine–Meuse area): Tian et al. 2026 (314), Schütz et al. 2025 (156), Vyas et al. 2023 (38), Gerber et al. 2024 (23), Yediay et al. 2024 (22, preprint), Gînguță et al. 2023 (13), Nagy et al. 2021 (9), Maróti et al. 2022 (3), Blöcher et al. 2026 (3), Gnecchi-Ruscone et al. 2024 (2), Penske et al. 2023 (2), Mattila et al. 2023 (2), Hajdu et al. 2026 (1), Varga et al. 2023 (1, St Ladislaus, pinned at his burial place) Olalde et al. 2026 (4) and Carrión et al. 2026 (224) | the paper's coordinates; where a paper gives none, AADR's for the paper's other samples from the same site, else the site named in it pinned from OpenStreetMap; the card says which |
| ○ hollow ring | 1,703 individuals from Akbari et al. 2026 whose locations were **anonymized** by the authors | **inferred** by this project, see below |
| ◆ diamond | 33 individuals added by hand from a PhD thesis (Rodrigues 2023, Romania) | the village or town named in the thesis |

Colour shows the date, in five periods from before 5000 BCE to after 500 CE.

## Inferred locations (hollow rings): read this first

Akbari et al. (2026) list these individuals but replaced their country and
coordinates with "anonymized"; their find spots are **not published**. This
map infers a likely country from indirect evidence in the published data, and
pins the individual at the site of the published sample the evidence points
to. Every hollow ring's card states the evidence used and how reliable that
kind of evidence is.

| Evidence | Meaning | Right country in tests* | Site |
|---|---|---|---|
| Adjacent lab number | Skeletons are numbered in batches; a number 1-3 away from a published sample is usually the same batch | 99.5-99.8% | likely |
| Block vote | Most published samples with nearby lab numbers (within 60) come from one country | 98.5% | probable or region only |
| Close relative | Shares 600+ cM of DNA with an already placed individual | 99.8% | follows the relative |
| IBD link | Shares long DNA segments with published people who lived within 300 years | 91% | region only |

\* Measured by hiding the known country of published samples and checking
whether the same evidence recovers it. This measures the country; the exact
site is less certain. Placements are dropped when relatives' dates contradict
each other. Samples with weaker evidence are not shown.

When a paper later publishes one of these individuals, its own find spot
replaces the inferred one and the card says where the map had placed it.
Four so far, and two of them show how wrong a confident-looking pin can be:

| Individual | Inferred at (confidence) | Published find spot | Off by |
|---|---|---|---|
| I12902 | Ottoland Kromme Elleboog, NL (site likely) | Mienakker, NL (Olalde et al. 2026) | 95 km |
| I7018 | Malonne Petit Ri, BE (region only) | Grotte Rousseau, BE (Olalde et al. 2026) | 9 km |
| I22103 | Birgi, Sicily (site probable, from a block of neighbouring lab numbers) | L'Hostalot, Castelló, Spain (Carrión et al. 2026) | 1,101 km |
| I23273 | Birgi, Sicily (through its relative I22103) | Necrópolis Blanes, Mérida, Spain (Carrión et al. 2026) | 1,641 km |

**These pins are working hypotheses, not recorded find spots. Do not cite
them as the location of a sample.** When these individuals are published,
their real locations replace anything shown here.

## Other things this map does to the data

- **Date corrections.** In AADR, 218 individuals have a date mean that falls
  outside their own date range (for example I6184: "1900-1450 BCE", mean 275
  BCE). Where the two disagree, the map resolves it and says so on the card
  ("Date check").
- **Sex and Y-DNA called here.** AADR lists 1,358 individuals with unknown sex
  and no Y call. For those, sex was called from the X and Y read rates and the
  Y haplogroup with yhaplo, from the public AADR genotypes. These are always
  labelled "called here". In checks against men AADR had already called,
  about 93% agree at the major-clade level.
- **One Y tree for every call.** The Y calls come from several sources
  (AADR, FamilyTreeDNA Discover, ybyra calls on the Akbari data, calls made
  here, papers),
  each with its own naming. Every call is placed on FamilyTreeDNA's public Y
  tree, so a search for a clade finds everything below it, whoever made the
  call.
  - FTDNA's public tree leaves out some well-known SNP names, such as Y3120
    and Z645. YFull's tree lists every SNP on each of its branches, so it
    shows which FTDNA branch carries the same mutations: Y3120 is FTDNA's
    I-S20602, so `y:Y3120` finds the same samples as `y:S20602`. Where even
    that fails, the sample is placed at a higher branch, never a lower one,
    and its card says so.
  - Sometimes FTDNA splits one YFull branch into an upper and a lower part,
    and it is unknown which part carries the SNP you searched for. The
    search then starts at the lower part, where every sample is certainly
    positive. Samples FTDNA puts only in the upper part are left out, unless
    the call their path comes from names that SNP itself. Example:
    `y:Y19966` (FTDNA H-P96 > H-Z19008) returns 102 samples; 15 at H-P96
    alone are left out.
  - **FamilyTreeDNA first.** Where FTDNA has assigned a Y haplogroup
    (about 9,200 samples), that is the only Y assignment shown, for every
    haplogroup: other sources' calls for the same sample are left out of
    the card, the table, the CSV and the search. Example: FTDNA stops MGS200
    at I-CTS10228 (AADR had called it I-Y3120), so it is found by
    `y:CTS10228` but not by `y:Y3120`. FTDNA's conclusion also settles the
    sex: a sample it assigns a Y haplogroup is shown as male (84 samples
    that AADR or this project had as female or unknown; the card says so).
    FTDNA often files an ancient sample under the paper's lab ID (PVper125
    for AADR's PV-125). Such a record is linked when the site letters and
    the grave or sample number agree in both IDs and in FTDNA's sample name
    ("Pitvaros 125"), or when the paper's own table gives that lab ID
    (MMper268 = MM-80 in Maróti et al. 2022). This added FTDNA's call to
    577 samples, mostly McColl et al. 2026 and Maróti et al. 2022.
  - **Without an FTDNA call** the sample's other calls are shown, each with
    who made it (a ybyra run made for this map, ybyra by Teepan, the
    publishing paper's own call, AADR's manual or automatic call, this
    project's yhaplo call), under the note "no FamilyTreeDNA assignment:
    unconfirmed, may be of low quality". Its tree place comes from the first
    of them in that order. ybyra comes first because it agrees with FTDNA
    most often where both called the same sample (ybyra 98%, AADR 96%, this
    project 96%); the paper's call ranks above AADR's because the map
    follows the publishing paper wherever it has one. ⚠ marks the few
    samples whose sources put them on different branches.
  - The table's **Y source** column says whose call each row's Y is (FTDNA,
    or which unconfirmed source), so you can sort them apart.
- **Y calls too young for the person.** Every Y call except FamilyTreeDNA's is checked against the age YFull gives its branch: when even the oldest formation age of the branch is more than 500 years after the person lived, the call cannot be right (typically an automatic call on very low coverage), so the sample moves up to the deepest branch on that line that already existed, and the card says so under *Y check*. Twenty samples are affected, e.g. Solutrean LPI002 (AADR: I-Y21293, a branch about 5,000 years old) now at I-M253. For I3004 (Aveline's Hole, Mesolithic) and I2181 (Smyadovo, Chalcolithic) a ybyra run made for this map places them at F-M89 and R-M207; AADR's automatic calls (R-Y11281, R-Y157823) are false positives.
- **Low-scoring and doubtful Y calls.** ybyra gives each call a score;
  ybyra itself flags scores under 50 as low. Measured against
  FamilyTreeDNA on the samples both called, ybyra calls scoring 150 or more
  land on a different branch 2.0% of the time (0 of 102 for the runs made
  for this map). AADR's calls do so 4.2% of the time, and the papers' own
  calls 4.5%. Below 150 there are too few FTDNA calls to measure. So a
  ybyra call still places the sample ahead of the paper's and AADR's calls
  even when its score is low; the card then carries a *low score* caution
  (53 runs). The exception is a low-scoring call that is the sample's only
  sign of a Y chromosome: some of those belong to women (I21899, score 12,
  is female by AADR's own sexing). Such a call is shown as *dubious*: it
  stays on the card but does not place the sample on the tree or match a Y
  search. Where it was the only sign of a man, the sex is shown as "male?"
  (filed under *unknown* in the sex filter). Nine calls are affected, seven
  of them on unpublished Akbari samples. Of the 183 ybyra runs made for this
  map, 107 overlap with FTDNA; they agree with it as described above. Sex
  proven otherwise overrides any table: I43953 (not on the map, as its find
  spot cannot be inferred) is female by its sequencing reads, so its E-V13
  call is treated as spurious. No ybyra placement may rest on transition
  SNPs alone (C↔T, G↔A). Post-mortem damage turns C into T and G into A,
  so a "derived" transition can be damage. A ybyra call whose branch is
  defined only by transitions sits at the deepest branch on its line that
  has a transversion, and the card says so under *Y check*. That moved 254
  calls (25 of the runs made for this map); for 249 of them FamilyTreeDNA's
  own call decides the placement anyway. Where AADR has the sample's
  genotypes, every ybyra call is also read against them along its line,
  from the root to the called branch. If a branch below the deepest one
  the genotypes read derived reads ancestral, the deeper call is likely a
  false positive and the sample sits at that deepest derived branch. Two so
  far: Ukraine_HG1 reads ancestral at CTS5437, the call's own SNP, and sits
  at R-CTS7500; NEO677 reads ancestral on R-V88 and sits at R-PF6289. AADR's
  1240K genotypes cover mostly older SNPs, though. The last branches of a
  deep call often have no SNP there and can't be checked: 29 of the 77
  checked calls end in such untested branches, which is not evidence
  against them. Every call is also age-checked, including
  calls in FTDNA's naming. I27983's low-scoring R-Z290 lies below P312, far
  too young for a man of about 5175 BCE, so the card says so and he sits
  at R-L51.
- **Date method.** Each card and the table show how the date was obtained,
  from AADR: radiocarbon on the individual itself, archaeological or
  historical context, or radiocarbon-dated relatives. Akbari et al. give only
  a date for their unpublished samples, so theirs is "not stated". For the
  589 samples not in AADR, everything follows their papers: a radiocarbon
  date where the paper gives one for the individual, otherwise the
  archaeological date the paper gives for the grave, burial group or
  cemetery (the middle of that range is used for sorting and filtering; the
  card quotes the range and says which it is). Where a paper sets a
  radiocarbon date aside (a freshwater reservoir effect: NKL-7, OFU-168,
  OFU-422) or dates the grave later by its finds, the card says so under
  *Date check*. Where a paper lists several equally possible mtDNA
  haplogroups, the map shows the one they share and the card lists them all.
  Samples a paper marks as a second sampling of another individual, as
  contaminated or as too low in coverage are left out; where a paper marks
  several samples as one individual, it is shown once. Where a paper gives no
  date (some burials in the Royal Basilica of Székesfehérvár), the sample is
  shown undated.
- **AADR rows that have since been published.** The 711 McColl et al. genomes AADR v66 carries as a 2025 preprint (McCollWillerslevBioRxiv2025) are labelled with the two 2026 *Nature* papers (Germanic and Celtic languages); their dates and dating method follow the papers (radiocarbon where a lab number is given, else the archaeological context), and the card's *Date check* says where AADR differed. CGG_2_021779 (Digomi, Georgia), which AADR gives no coordinates, is now on the map with the papers' coordinates.
- **AADR rows: the publishing paper first.** Where the map has the
  publishing paper's own tables (Maróti et al. 2022, Gerber et al. 2024,
  Gnecchi-Ruscone et al. 2024, Mattila et al. 2023, McColl et al. 2026,
  Penske et al. 2023, Varga et al. 2024: 1,674 AADR samples), the paper's
  coordinates, date, sex, mtDNA, Y call and coverage replace AADR's, and the
  card's *Note* lists every change with AADR's value in brackets. FTDNA's Y
  call still comes first. Examples: AADR's coordinates for 259 Maróti 2022
  samples are several kilometres from the paper's GPS readings; KD-29 is at
  Kaba-Dögös, not Orosháza; many McColl and Gnecchi-Ruscone samples gain the
  paper's mtDNA, which AADR leaves out. Exceptions, all from the papers
  themselves:
  - Radiocarbon dates are taken from wherever the paper reports them, not
    only from its main table. Maróti et al. 2022 give only centuries in
    their sample table, but 73 radiocarbon dates in Data S2A/S2B. These
    replace AADR's copies, and give five samples a radiocarbon date AADR
    lacks or does not use: KD-29, SZF-371, SZK-102, SZK-213 and MSG-1. The
    paper sets one aside, ARK-14, whose grave goods it trusts more; the map
    follows it and the card quotes the reason. A paper's archaeological date
    never replaces a radiocarbon date the same paper reports; the card notes
    where they disagree.
  - Every supplement of every paper was read for dates, not only the main
    tables. This added radiocarbon dates for 9 Abasár samples (Varga et
    al. 2024, Supplementary Information) and 41 Rákóczifalva and Hajdúnánás
    samples (Gnecchi-Ruscone et al. 2024, Supplementary Tables 2 and 6). It
    also turned up two burials at Kruszyn, lbk102 and lbk104, whose
    radiocarbon dates Mattila et al. 2023 reject; the paper dates them by
    context to c. 7,300-7,000 cal BP, a thousand years before AADR's date.
    Olalde et al. 2026 set aside the radiocarbon dates AADR gives for five
    Swifterbant-period burials (a freshwater reservoir effect) and date them by
    stratigraphy; the map follows the paper and quotes it under *Date check*.
    The same paper moves I7010 from the Neolithic to the Mesolithic
    (8000-5500 BCE) and gives I38447 a radiocarbon date where AADR has only
    a placeholder.
    The Yunatsite infants YUN035 and YUN037 take the date of the urn burial
    they share with YUN036 and YUN038 (Penske et al. 2023). The other
    Gnecchi-Ruscone et al. graves (327) are dated by their phase in the
    paper's Supplementary Table 2. The years come from the paper's Fig. 1:
    early Avar period 567-650, middle 650-700, late 700-822. The paper gives
    no years for its late sub-phases (LA I-III), so those graves get the
    whole late period.
  - For 379 McColl et al. samples AADR gives a "radiocarbon" date without a
    lab number, where the papers' tables give a context date. The papers'
    Supplementary Information has a radiocarbon date on the individual for
    one of them (CGG_2_106490, 2159±50 BP, UBA-31576), now used. For the
    rest the map shows the papers' context dates.
  - A Y call the paper gives only as an ISOGG name (R1a1a1b2...) is not
    used, because the map can place it only at the top of its haplogroup.
    McColl et al.'s own ybyra calls scoring below 150 are not used either.
  - An ID a paper lists twice (PIE064 in Penske et al.) is not used.
  - A few years in Penske et al.'s table lack their minus sign (KTL001:
    3343-3502 for a radiocarbon age of 4609±26 BP); they are read as BCE.

  ASZK-1, which AADR places at Marosszentgyörgy (Romania), is at
  Árpás-Dombiföld (Hungary), as Maróti et al. 2022 and Schütz et al. 2025
  give it. Its date is the paper's radiocarbon date (366-533 cal CE,
  DeA-26539). AADR's date combines that with DeA-26559, which the paper
  gives to MSG-1, the Marosszentgyörgy man. **PV-12 and PV-125** (Pitvaros, Avar period): AADR's genome data
  for the two appear to be swapped. AADR's Y calls and coverage for each
  match the other man in Maróti et al. 2022, while FamilyTreeDNA and a ybyra
  run agree with the paper (PV-12 E-Z5016, PV-125 I-S8269). The map shows
  the paper's data; analyses of these two on AADR data use the other man's
  genome. KD-29 and OBH-52, whom the paper lists as identical twins from two
  cemeteries, are shown separately. AADR's merged genome of the two
  (KD-29_OBH-52_twins) is left off the map.
- **Béla, Duke of Macsó (BPDOM01).** The paper's own Y call is only in its
  paywalled main text. The map shows a call made here from the paper's raw
  Yleaf marker list (its Supplementary Table 2), labelled *called here*: 374
  of the 407 derived markers lie on one line, N-L550, the deepest branch
  with at least two derived reads. A single read points one step deeper, to
  N-Y4341.
- **Site coordinates for the thesis samples** are village or town centres;
  the thesis gives no coordinates.

## Using the map

- **Search box:** words match anywhere. `field:value` narrows the search:
  `y:L151` (L151 and everything below it: P312, U106 and so on), `y:L11`
  (an equivalent SNP gives the same result), `y:R1b`, `mt:H1` (H1 and its
  subclades, not H10), `culture:Maros`, `site:Mokrin`, `country:Hungary`,
  `id:I2762`. Terms combine: `y:P312 country:Hungary`. Y searches follow
  each sample's path (see below). A Y SNP or branch name typed on its own
  (`S20602`) searches the tree just as `y:S20602` does, but also matches
  other fields as text: `V13` alone also finds mtDNA HV13b, while `y:V13`
  finds Y-DNA only. Use SNP names for complete results: long
  ISOGG names such as `y:I2a1b` can only reach samples whose path comes from
  AADR, because only AADR gives ISOGG names; short ones (R1b, I2, J2a, E1b1b)
  work for every sample.
- **Period and from/to:** filter by date, for example `3000 BCE` to `500 CE`.
- **Second filter row:** *Country*, *Region*, *Culture / group*, *Study*, *Y source* and
  *Date method* each open a list with a search box. Tick one or more values;
  each shows how many samples it would give under your other filters.
  Region is the UN's M49 subregion of the country (Hungary and Romania are
  Eastern Europe, Serbia and Croatia Southern Europe). Unpublished samples
  are listed under their anchor's culture, marked [inferred]. *Coverage*
  takes a minimum and/or maximum (`1` = at least 1×); samples without a
  coverage figure drop out once it is set. **Reset all filters** clears
  everything. The page address keeps every filter, so copying it shares
  exactly what you see.
- **Table** lists every sample that matches the filters, or only those in the
  map view. Click a column heading to sort by it, again to reverse; the Y
  column sorts in tree order, so each clade stays together. Click a row to
  go to that sample on the map. **Copy table** copies every row, in the
  current order, ready to paste into Excel or Google Sheets (selecting with
  the mouse only reaches the rows on screen).
- **Draw area** lets you outline a region by hand: click its corners on the
  map, then click the first corner again (or double-click, or press Enter)
  to close it. Backspace removes the last corner; Esc cancels. Only samples
  inside the outline stay on the map, in the table (which opens by itself)
  and in the CSV, together with any search and date filter. The outline is
  kept in the page address, so copying the link shares it. Inferred samples
  (hollow rings) count by their pin. **Clear area** removes it.
- **Hide filters / Show filters** (next to the title) folds everything above
  the map away; the title bar then shows the sample count and how many
  filters are active. On phones the filters start folded, and the page
  remembers your choice on each device.
- **Download filtered CSV** exports the matching samples with all their fields;
  while the table is open it follows the table's rows and sort order.
- **Links:** the address can carry a search and a pinned sample, for example
  `index.html?q=y:V13&to=1 CE#id=I2762`.
- **Layers** (top right): grey or OpenStreetMap background; rivers on or off.

## Sources and licences

| Data | Source | Terms |
|---|---|---|
| Published samples | Mallick S. et al. (2024) The Allen Ancient DNA Resource (AADR), *Scientific Data* 11:182; data v66, Harvard Dataverse doi:[10.7910/DVN/FFIDCW](https://doi.org/10.7910/DVN/FFIDCW) | CC0 1.0 |
| Not in AADR: 156 individuals | Schütz O. et al. (2025) Unveiling the origins and genetic makeup of the "forgotten people": a study of the Sarmatian-period population in the Carpathian Basin, *Cell* 188:4074-4090, doi:[10.1016/j.cell.2025.05.009](https://doi.org/10.1016/j.cell.2025.05.009). Cemetery, grave, coordinates, radiocarbon dates, coverage, sex, mtDNA and group from its Tables S1a and S1c; archaeological dates from the site descriptions in its supplement; Y from FamilyTreeDNA Discover | open access, CC BY-NC-ND 4.0; please cite the paper |
| Not in AADR: MSG-1, OBH-52, SH-66 | Maróti Z. et al. (2022) The genetic origin of Huns, Avars, and conquering Hungarians, *Current Biology* 32:2858-2870, doi:[10.1016/j.cub.2022.04.093](https://doi.org/10.1016/j.cub.2022.04.093), Data S1A; for MSG-1 also Schütz et al. 2025, Table S1b | please cite the paper |
| Not in AADR: 314 individuals | Tian Y. et al. (2026) Unveiling the complexity of post-Roman polity formation in Pannonia using ancient DNA, *Science* 392:eaec2634, doi:[10.1126/science.aec2634](https://doi.org/10.1126/science.aec2634). Site, sex, coverage, mtDNA and radiocarbon dates from its Table S1, each man's terminal Y SNP from Table S2, and site dates from Supplementary Text S1 (the published version withdraws 75 of the preprint's low-coverage mtDNA calls; the map follows it) | please cite the paper |
| Not in AADR: 38 individuals | Vyas D. N. et al. (2023) Fine-scale sampling uncovers the complexity of migrations in 5th-6th century Pannonia, *Current Biology* 33:3951-3961, doi:[10.1016/j.cub.2023.07.063](https://doi.org/10.1016/j.cub.2023.07.063), Table S1 | please cite the paper |
| Not in AADR: 22 individuals | Yediay F. E. et al. (2024) Ancient genomics support deep divergence between Eastern and Western Mediterranean Indo-European languages, bioRxiv preprint, doi:[10.1101/2024.12.02.626332](https://doi.org/10.1101/2024.12.02.626332), Tables S2 and S7 | please cite the preprint |
| Not in AADR: KUP003, KUP025 | Gnecchi-Ruscone G. A. et al. (2024) Network of large pedigrees reveals social practices of Avar communities, *Nature* 629:376-383, doi:[10.1038/s41586-024-07312-4](https://doi.org/10.1038/s41586-024-07312-4), Supplementary Table 1 and Information; coordinates as AADR gives for the paper's other Kunpeszér individuals | please cite the paper |
| Not in AADR: 23 individuals | Gerber D. et al. (2024) Ancient genomes reveal Avar-Hungarian transformations in the 9th-10th centuries CE Carpathian Basin, *Science Advances* 10:eadq5864, doi:[10.1126/sciadv.adq5864](https://doi.org/10.1126/sciadv.adq5864), Table S1 | CC BY-NC 4.0; please cite the paper |
| Not in AADR: 13 individuals | Gînguță A. et al. (2023) Genetic identification of members of the prominent Báthory aristocratic family, *iScience* 26:107911, doi:[10.1016/j.isci.2023.107911](https://doi.org/10.1016/j.isci.2023.107911), Table S1 | please cite the paper |
| Not in AADR: 9 individuals | Nagy P. L. et al. (2021) Determination of the phylogenetic origins of the Árpád Dynasty based on Y chromosome sequencing of Béla the Third, *European Journal of Human Genetics* 29:164-172, doi:[10.1038/s41431-020-0683-z](https://doi.org/10.1038/s41431-020-0683-z), Tables 1 and 2 | please cite the paper |
| Not in AADR: Arg1, Arg3, Arg5_1 | Blöcher J. et al. (2026) Demography and life histories across the Roman frontier in Germany 400-700 CE, *Nature* 654:984-993, doi:[10.1038/s41586-026-10437-3](https://doi.org/10.1038/s41586-026-10437-3), Supplementary Table 1 (Argamum) | please cite the paper |
| Not in AADR: PIE016 (= PIE007, PIE031), PIE061 (= PIE060) | Penske S. et al. (2023) Early contact between late farming and pastoralist societies in southeastern Europe, *Nature* 620:358-365, doi:[10.1038/s41586-023-06334-8](https://doi.org/10.1038/s41586-023-06334-8), Supplementary Table A | please cite the paper |
| Not in AADR: buk013, buk031 | Mattila T. M. et al. (2023) Genetic continuity, isolation, and gene flow in Stone Age Central and Eastern Europe, *Communications Biology* 6:793, doi:[10.1038/s42003-023-05131-3](https://doi.org/10.1038/s42003-023-05131-3), Supplementary Data 1 | please cite the paper |
| Not in AADR: BPDOM01 | Hajdu T. et al. (2026) Murder in cold blood? Forensic and bioarchaeological identification of the skeletal remains of Béla, Duke of Macsó (c. 1245-1272), *Forensic Science International: Genetics* 81:103381, doi:[10.1016/j.fsigen.2025.103381](https://doi.org/10.1016/j.fsigen.2025.103381), Supplementary Information | please cite the paper |
| Not in AADR: SZTL (King Ladislaus I) | Varga G. I. B. et al. (2023) The archaeogenomic validation of Saint Ladislaus' relic provides insights into the Árpád dynasty's genealogy, *Journal of Genetics and Genomics* 50:58-61, doi:[10.1016/j.jgg.2022.06.008](https://doi.org/10.1016/j.jgg.2022.06.008), Table S1b. The sample is his skull relic (Győr); the pin is his burial place, the cathedral of Várad (Oradea), from historical sources | please cite the paper |
| Not in AADR: I7018, I12902, SWA001, I13659; 40 more in AADR | Olalde I. et al. (2026) Lasting Lower Rhine–Meuse forager ancestry shaped Bell Beaker expansion, *Nature* 652:938-946, doi:[10.1038/s41586-026-10111-8](https://doi.org/10.1038/s41586-026-10111-8). Site, coordinates, date, sex, coverage, mtDNA and Y from its Supplementary Table 1; radiocarbon dates also in Supplementary Table 16, site context in its Supplementary Information. I7018 and I12902 were shown before as anonymised Akbari et al. 2026 samples at inferred find spots (Malonne, Ottoland), now at the paper's (Grotte Rousseau, Mienakker) | please cite the paper |
| Not in AADR: 224 individuals; 10 more in AADR | Carrión P. et al. (2026) Contrasting demographic impacts of Roman colonization and early medieval migrations in the Iberian Peninsula, *Cell* 189, doi:[10.1016/j.cell.2026.09.052](https://doi.org/10.1016/j.cell.2026.09.052). Locality, coordinates, date, sex, mtDNA and Y from its Table S1A (radiocarbon dates also in Table S5A). Left out: the 9 individuals the paper itself flags for contamination. Two were shown before as anonymised Akbari et al. 2026 samples at inferred find spots in Sicily (I22103, I23273) | please cite the paper |
| Published versions of AADR's McCollWillerslevBioRxiv2025 (711 individuals) | McColl H. et al. (2026) Tracing the spread of Germanic languages using ancient genomics, *Nature*, doi:[10.1038/s41586-025-09064-1](https://doi.org/10.1038/s41586-025-09064-1), Table S1.1; and McColl H. et al. (2026) Tracing the spread of Celtic languages using ancient genomics, *Nature*, doi:[10.1038/s41586-026-11198-9](https://doi.org/10.1038/s41586-026-11198-9), Table S1.1. Study label, dates and dating method from the papers; coordinates for CGG_2_021779 (Digomi), which AADR lacks | please cite the papers |
| Site locations where a paper gives no coordinates | [OpenStreetMap](https://www.openstreetmap.org/copyright) (Nominatim): the street, district or village the paper's site name gives | ODbL; &copy; OpenStreetMap contributors |
| Anonymized samples: dates, coverage, IBD used for placement | Akbari A. et al. (2026) Ancient DNA reveals pervasive directional selection across West Eurasia, *Nature*, doi:[10.1038/s41586-026-10358-1](https://doi.org/10.1038/s41586-026-10358-1), supplementary data | the publisher's and authors' terms; please cite the paper |
| Y-DNA calls for the Akbari individuals | made with ybyra by Teepan (genarchivist.net) on the Akbari 2026 data | please credit Teepan and cite Akbari et al. 2026 |
| mtDNA calls for the Akbari individuals | third-party calls on the Akbari 2026 data, received with the Y calls | as received; please cite Akbari et al. 2026 |
| Y tree | [FamilyTreeDNA public Y-DNA haplotree](https://www.familytreedna.com/public/y-dna-haplotree/R), downloaded 2026-11-20 | FamilyTreeDNA's; no licence stated. Used to place and search the calls; only branch names are shown |
| FTDNA haplogroups and names of ancient samples | [FamilyTreeDNA Discover](https://discover.familytreedna.com/), as compiled by [ancientsampledb.app](https://ancientsampledb.app/) | FamilyTreeDNA's; no licence stated. Shown with credit on every card |
| SNP names between trees | [YFull YTree](https://github.com/YFullTeam/YTree) v14.06.0, © YFull | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/); used to translate SNP names, not shown |
| SNP name synonyms | ISOGG Y-DNA Haplogroup Tree 2016, as packaged with [yhaplo](https://github.com/23andMe/yhaplo) | used only to translate SNP names, not shown |
| Thesis samples (◆) | Rodrigues S. M. (2023) *Archaeogenetics and Palaeogenetics of Southeast and Eastern Europe*, PhD thesis, University of Huddersfield ([record](https://pure.hud.ac.uk/en/studentTheses/archaeogenetics-and-palaeogenetics-of-southeast-and-eastern-europ/)) | facts cited from the thesis; please cite it |
| Rivers | [Natural Earth](https://www.naturalearthdata.com/) 1:10m rivers and lake centrelines | public domain |
| Background map | [OpenFreeMap](https://openfreemap.org), [OpenMapTiles](https://www.openmaptiles.org/), data &copy; [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors | ODbL (data); free to use |
| Map libraries | [Leaflet](https://leafletjs.com) 1.9.4, [MapLibre GL JS](https://maplibre.org) 5.24.1, [maplibre-gl-leaflet](https://github.com/maplibre/maplibre-gl-leaflet) 0.1.4 | their open-source licences |

The page itself (its HTML, CSS and JavaScript) is released under the MIT
licence, see `LICENSE`. The data keep their sources' terms above.

## Publishing on GitHub Pages

1. Create a new **public** repository on GitHub and push this folder to it.
2. In the repository, open **Settings > Pages**. Under *Build and deployment*,
   choose *Deploy from a branch*, branch `main`, folder `/ (root)`, and save.
3. After a minute the map is live at
   `https://<your-user-name>.github.io/<repository-name>/`.

To update it, replace `index.html` with a newly built map and push again.

## Corrections

If a sample is wrong (a location, date or haplogroup), please open an issue
in this repository and include the sample ID and your source.
