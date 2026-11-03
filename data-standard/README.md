# Open Menstrual Pain Log (v0.1)

A privacy-first JSON format for recording one day of menstrual cycle and pain data.

- **Schema:** [`menstrual-pain-log.schema.json`](menstrual-pain-log.schema.json) (JSON Schema 2020-12)
- **Example:** [`examples/log-entry.json`](examples/log-entry.json) (synthetic data only)

## What one entry captures

| Section | Fields |
|---|---|
| Who (pseudonymous) | `user_ref`, `age_band`, `region` |
| Cycle | `local_date`, `cycle_day`, `period_status`, `flow` |
| Pain | `pain.score` (0–10), `locations`, `character`, `duration_hours` |
| Symptoms | nausea, fatigue, painful bowel movements and other red-flag symptoms |
| Interventions | TENS device use and settings, painkiller doses, pain score after |
| Impact | missed school or work, activity limitation |
| Care | where care was sought |

## Privacy rules

- No names, phone numbers, ID numbers, exact birth dates or free text.
- Location stops at county level (ISO 3166-2).
- Apps for users under 18 must not ask about pain during intercourse.

## Validate

```bash
pip install jsonschema
python -c "import json, jsonschema; jsonschema.validate(json.load(open('examples/log-entry.json')), json.load(open('menstrual-pain-log.schema.json'))); print('valid')"
```
