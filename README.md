# Ancient DNA samples by find spot

An interactive map of about 22,000 ancient human genomes, from the Palaeolithic
to the recent past. Each dot is one individual. Hover it for its date,
culture, sex, Y-DNA and mtDNA haplogroups, site and source. Click it to list
everyone buried at the same site.

**Open the map:** `https://<your-user-name>.github.io/<repository-name>/`
(this address works once GitHub Pages is switched on, see below).

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
- **Site coordinates for the thesis samples** are village or town centres;
  the thesis gives no coordinates.

## Using the map

- **Search box:** words match anywhere. `field:value` narrows the search:
  `y:V13` (follows the Y tree), `y:R1b`, `mt:H1` (H1 and its subclades, not
  H10), `culture:Maros`, `site:Mokrin`, `country:Hungary`, `id:I2762`.
- **Period and from/to:** filter by date, for example `3000 BCE` to `500 CE`.
- **List samples in view** and **Download filtered CSV** export what you see.
- **Links:** the address can carry a search and a pinned sample, for example
  `index.html?q=y:V13&to=1 CE#id=I2762`.
- **Layers** (top right): grey or OpenStreetMap background; rivers on or off.

## Sources and licences

| Data | Source | Terms |
|---|---|---|
| Published samples | Mallick S. et al. (2024) The Allen Ancient DNA Resource (AADR), *Scientific Data* 11:182; data v66, Harvard Dataverse doi:[10.7910/DVN/FFIDCW](https://doi.org/10.7910/DVN/FFIDCW) | CC0 1.0 |
| Anonymized samples: dates, coverage, IBD used for placement | Akbari A. et al. (2026) Ancient DNA reveals pervasive directional selection across West Eurasia, *Nature*, doi:[10.1038/s41586-026-10358-1](https://doi.org/10.1038/s41586-026-10358-1), supplementary data | the publisher's and authors' terms; please cite the paper |
| Y and mtDNA haplogroup calls for the Akbari individuals | third-party haplogroup calls made on the Akbari 2026 data | as received; please cite Akbari et al. 2026 |
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
