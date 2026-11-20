# Ancient DNA samples by find spot

An interactive map of about 22,000 ancient human genomes, from the Palaeolithic
to the recent past. Each dot is one individual. Hover it for its date and how
it was dated, culture, sex, Y-DNA and mtDNA haplogroups, site and source.
Click it to list everyone buried at the same site, or open the sortable table
of every sample that matches your search.

**Open the map:** https://ampirat777.github.io/ancient-dna-map/

## What is on the map

| Marker | Samples | Location |
|---|---|---|
| ● filled dot | 20,650 published individuals from the Allen Ancient DNA Resource (AADR v66) | the coordinates AADR records for the site, which are sometimes the nearest town |
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
  call. FTDNA Discover's own call is shown for about 8,300 samples.
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
  - **Each sample sits on the tree once.** Its place (its path) comes from
    FamilyTreeDNA's call wherever there is one, for every haplogroup. Without
    one it comes from the ybyra call, then AADR's, then the calls made here.
    That order follows how often each source agrees with FTDNA on samples
    FTDNA also called (ybyra 98%, AADR 96%, calls made here 96%). Searches,
    the table's Y column and its sorting use this path only. Example: FTDNA
    stops MGS200 at I-CTS10228 while AADR calls it I-Y3120, so it is found by
    `y:CTS10228` but not by `y:Y3120`.
  - **Every call is still shown.** A sample's card lists every assignment
    and who made it (FTDNA Discover, AADR's manual or automatic call, ybyra
    by Teepan, this project's yhaplo call, the publication). It says when
    another source goes deeper than the path, and marks with ⚠ (also in the
    table) a source that puts the sample on a different branch.
- **Doubtful Y calls.** ybyra gives each call a score. FamilyTreeDNA has
  its own call for nearly every ybyra call scoring 150 or more, but for only
  3 of the 49 below that, and the low-scoring calls include samples known to
  be female. A ybyra call under 150 that FTDNA does not confirm is therefore
  shown as *dubious*: it stays on the card but does not place the sample on
  the tree or match a Y search. Where it was the only sign of a man, the sex
  is shown as "male?" (filed under *unknown* in the sex filter). Nine calls
  are affected, seven of them on unpublished Akbari samples. Sex proven
  otherwise overrides any table: I43953 (not on the map, as its find spot
  cannot be inferred) is female by its sequencing reads, so its E-V13 call
  is treated as spurious.
- **Date method.** Each card and the table show how the date was obtained,
  from AADR: radiocarbon on the individual itself, archaeological or
  historical context, or radiocarbon-dated relatives. Akbari et al. give only
  a date for their unpublished samples, so theirs is "not stated".
- **Site coordinates for the thesis samples** are village or town centres;
  the thesis gives no coordinates.

## Using the map

- **Search box:** words match anywhere. `field:value` narrows the search:
  `y:L151` (L151 and everything below it: P312, U106 and so on), `y:L11`
  (an equivalent SNP gives the same result), `y:R1b`, `mt:H1` (H1 and its
  subclades, not H10), `culture:Maros`, `site:Mokrin`, `country:Hungary`,
  `id:I2762`. Terms combine: `y:P312 country:Hungary`. Y searches follow
  each sample's path (see below). Use SNP names for complete results: long
  ISOGG names such as `y:I2a1b` can only reach samples whose path comes from
  AADR, because only AADR gives ISOGG names; short ones (R1b, I2, J2a, E1b1b)
  work for every sample.
- **Period and from/to:** filter by date, for example `3000 BCE` to `500 CE`.
- **Table** lists every sample that matches the filters, or only those in the
  map view. Click a column heading to sort by it, again to reverse; the Y
  column sorts in tree order, so each clade stays together. Click a row to
  go to that sample on the map.
- **Download filtered CSV** exports the matching samples with all their fields.
- **Links:** the address can carry a search and a pinned sample, for example
  `index.html?q=y:V13&to=1 CE#id=I2762`.
- **Layers** (top right): grey or OpenStreetMap background; rivers on or off.

## Sources and licences

| Data | Source | Terms |
|---|---|---|
| Published samples | Mallick S. et al. (2024) The Allen Ancient DNA Resource (AADR), *Scientific Data* 11:182; data v66, Harvard Dataverse doi:[10.7910/DVN/FFIDCW](https://doi.org/10.7910/DVN/FFIDCW) | CC0 1.0 |
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
