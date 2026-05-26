# Sierra Leone Administrative Divisions / Sierra Leone



## Overview

| Item | Details |
|------|---------|
| Province | 5 |
| District | 16 |
| Chiefdom | 167 |
| Section | 1,316 |
| Coordinates | ✅ Included (all levels) |
| Formats | JSON, NDJSON, CSV |
| License | CC-BY-4.0 |
| Last Updated | 2026-05-26 |

## Browse by Province

| # | Province | Districts | Chiefdoms | Sections | Link |
|---|----|----|----|----|------|
| 1 | Eastern | 3 | 46 | 265 | [Browse](divisions/eastern-sl01/) |
| 2 | North Western | 3 | 23 | 284 | [Browse](divisions/north-western-sl05/) |
| 3 | Northern | 4 | 31 | 258 | [Browse](divisions/northern-sl02/) |
| 4 | Southern | 4 | 54 | 422 | [Browse](divisions/southern-sl03/) |
| 5 | Western | 2 | 13 | 87 | [Browse](divisions/western-sl04/) |

## Data Files

| File | Format | Description |
|------|--------|-------------|
| [all-province.json](data/all-province.json) | JSON | All 5 province records |
| [all-district.json](data/all-district.json) | JSON | All 16 district records |
| [all-chiefdom.json](data/all-chiefdom.json) | JSON | All 167 chiefdom records |
| [all-section.json](data/all-section.json) | JSON | All 1,316 section records |
| [all-flat.json](data/all-flat.json) | JSON | Levels 1-3 flat array |
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
| `level` | integer | 1=province, 2=district, 3=chiefdom, 4=section |
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
divisions/{province-slug}/{district-slug}/{chiefdom-slug}/
```

Sections are listed inline in each chiefdom's README.

## AI Integration

- [llms.txt](docs/llms.txt) — Quick reference for AI agents
- [llms-full.txt](docs/llms-full.txt) — Summary with per-province links
- [Per-province data](docs/llms-full/) — Full data by province

## Citation

```
Sierra Leone Administrative Divisions Dataset (CC-BY-4.0)
URL: https://github.com/open-admin-data/sierra-leone-administrative-divisions
```

See [CITATION.cff](CITATION.cff) for machine-readable citation.

## License

- **Data**: [CC-BY-4.0](LICENSE)

## Related

- [ListBase](https://www.listbase.org) — Structured reference data for every country
- [open-admin-data](https://github.com/open-admin-data) — Open administrative data for ASEAN countries
- [thailand-administrative-divisions](https://github.com/open-admin-data/thailand-administrative-divisions) — Thailand dataset
