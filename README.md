# Cambodia Administrative Divisions / កម្ពុជា

Open dataset of Cambodia's complete administrative hierarchy — from provinces down to communes. This repository provides structured, bilingual (Khmer + English) reference data for all three levels of Cambodia's administrative divisions, including postal codes and geographic coordinates at every level. Designed for developers, researchers, government agencies, and AI agents.

Licensed under CC-BY-4.0. Browse the hierarchy through GitHub's folder navigation, download aggregate files in JSON/CSV/NDJSON, or integrate directly via raw URLs.

## Overview

| Item | Details |
|------|---------|
| Province | 25 |
| District | 210 |
| Commune | 1,652 |
| Coordinates | ✅ Included (all levels) |
| Postal Codes | ✅ Included (commune level) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-09-02 |
| Website | [openadmindata.org/kh](https://openadmindata.org/kh/) |
| API | [openadmindata.org/api/kh](https://openadmindata.org/api/kh/) |
| Flag | [PNG](https://onlygames.me/flags-png/kh/) · [CDN](https://www.freeflags.org/cdn/) · [CSS](https://www.freeflags.org/css/) · [Collections](https://www.freeflags.org/collections/) |
| National Anthem | [🎵 Listen & Download Cambodia National Anthem MP3](https://onlygames.me/national-anthems/kh/) |

## Browse by Province

| # | Province | Districts | Communes | Link |
|---|----|----|----|------|
| 1 | បន្ទាយមានជ័យ (Banteay Meanchey) | 9 | 67 | [Browse](divisions/banteay-meanchey-01/) |
| 2 | បាត់ដំបង (Battambang) | 14 | 103 | [Browse](divisions/battambang-02/) |
| 3 | កំពង់ចាម (Kampong Cham) | 10 | 109 | [Browse](divisions/kampong-cham-03/) |
| 4 | កំពង់ឆ្នាំង (Kampong Chhnang) | 8 | 71 | [Browse](divisions/kampong-chhnang-04/) |
| 5 | កំពង់ស្ពឺ (Kampong Speu) | 9 | 88 | [Browse](divisions/kampong-speu-05/) |
| 6 | កំពង់ធំ (Kampong Thom) | 9 | 81 | [Browse](divisions/kampong-thom-06/) |
| 7 | កំពត (Kampot) | 9 | 93 | [Browse](divisions/kampot-07/) |
| 8 | កណ្តាល (Kandal) | 13 | 127 | [Browse](divisions/kandal-08/) |
| 9 | កោះកុង (Koh Kong) | 7 | 29 | [Browse](divisions/koh-kong-09/) |
| 10 | ក្រចេះ (Kratié) | 7 | 48 | [Browse](divisions/krati-10/) |
| 11 | មណ្ឌលគិរី (Mondulkiri) | 5 | 21 | [Browse](divisions/mondulkiri-11/) |
| 12 | ភ្នំពេញ (Phnom Penh) | 14 | 105 | [Browse](divisions/phnom-penh-12/) |
| 13 | ព្រះវិហារ (Preah Vihear) | 8 | 51 | [Browse](divisions/preah-vihear-13/) |
| 14 | ព្រៃវែង (Prey Veng) | 13 | 116 | [Browse](divisions/prey-veng-14/) |
| 15 | ពោធិ៍សាត់ (Pursat) | 7 | 49 | [Browse](divisions/pursat-15/) |
| 16 | រតនគិរី (Ratanakiri) | 9 | 50 | [Browse](divisions/ratanakiri-16/) |
| 17 | សៀមរាប (Siem Reap) | 13 | 100 | [Browse](divisions/siem-reap-17/) |
| 18 | ព្រះសីហនុ (Preah Sihanouk) | 6 | 29 | [Browse](divisions/preah-sihanouk-18/) |
| 19 | ស្ទឹងត្រែង (Stung Treng) | 6 | 34 | [Browse](divisions/stung-treng-19/) |
| 20 | ស្វាយរៀង (Svay Rieng) | 8 | 80 | [Browse](divisions/svay-rieng-20/) |
| 21 | តាកែវ (Takéo) | 10 | 100 | [Browse](divisions/tako-21/) |
| 22 | ឧត្តរមានជ័យ (Oddar Meanchey) | 5 | 24 | [Browse](divisions/oddar-meanchey-22/) |
| 23 | កែប (Kep) | 2 | 5 | [Browse](divisions/kep-23/) |
| 24 | ប៉ៃលិន (Pailin) | 2 | 8 | [Browse](divisions/pailin-24/) |
| 25 | ត្បូងឃ្មុំ (Tboung Khmum) | 7 | 64 | [Browse](divisions/tboung-khmum-25/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 25 province records |
| [all-district.json](data/all-district.json) | JSON | All 210 district records |
| [all-commune.json](data/all-commune.json) | JSON | All 1,652 commune records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-2 flat array |
| [all-flat.ndjson](data/all-flat.ndjson) | NDJSON | Streaming format |
| [all-flat.csv](data/all-flat.csv) | CSV | Spreadsheet format |
| [hierarchy.json](data/hierarchy.json) | JSON | Nested tree |
| [schema.json](data/schema.json) | JSON Schema | Data schema |

## Quick Start

### Python

```python
import json

with open("data/all-province.json", "r", encoding="utf-8") as f:
    data = json.load(f)

for r in data:
    print(f"{r['name']['local']} ({r['name']['en']}) — {r['children_count']['district']} districts")
```

### JavaScript

```javascript
import { readFileSync } from "fs";

const data = JSON.parse(readFileSync("data/all-province.json", "utf-8"));
console.log(`Total: ${data.length} provinces`);
```

## Schema

| Field | Type | Description |
|-------|------|-------------|
| `id` | string | Unique identifier |
| `level` | integer | 1=province, 2=district, 3=commune |
| `level_name` | object | Level label (local + English) |
| `name.local` | string | Name in local script |
| `name.en` | string | English name |
| `name.slug` | string | URL-safe slug |
| `parent` | object/null | Parent division reference |
| `ancestors` | array | Full ancestor chain |
| `children_count` | object | Count of children per level |
| `zip_codes` | array | Postal codes (where available) |
| `geo.lat` | string | Latitude (WGS84) |
| `geo.lon` | string | Longitude (WGS84) |

Full schema: [data/schema.json](data/schema.json)

## Hierarchy Browse

```
divisions/{province-slug}/
divisions/{province-slug}/{district-slug}/
```

Communes are listed inline in each district's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Cambodia Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/cambodia-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [Open Admin Data](https://openadmindata.org) — Browse, search and explore administrative divisions for every country
- [open-admin-data](https://github.com/open-admin-data) — GitHub organization with all country repos
- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [FreeFlags.org](https://www.freeflags.org) — Free flag images for every country
- [Flag CDN](https://www.freeflags.org/cdn/) — Hotlink flag images directly
- [Flag CSS](https://www.freeflags.org/css/) — CSS flag sprites for web projects
- [Flag Collections](https://www.freeflags.org/collections/) — Curated flag image packs
