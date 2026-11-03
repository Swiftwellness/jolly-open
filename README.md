# Jolly Open

**Open tools for drug-free menstrual pain relief and menstrual health intelligence for girls and women in Africa.**

Jolly Open is the open-source home of [Swift Wellness Limited](https://swifthealth.care)'s menstrual health technology:

- **Jolly Device**: a small, rechargeable wearable that relieves menstrual pain without medication, using TENS (transcutaneous electrical nerve stimulation).
- **Botsolai**: an AI companion that learns each user's cycle and pain patterns, predicts painful days, shares age-appropriate menstrual health information, and flags warning signs that need medical attention.

## Why this exists

Period pain is one of the most common and most neglected health problems facing girls in Kenya and across Africa. A study of Kenyan secondary school girls found that 72% experience dysmenorrhea and 29% experience severe pain (Kagia et al., *East African Medical Journal*, 2018). Most have no safe, affordable way to manage it, and conditions such as endometriosis often go undiagnosed for years because no one tracks symptoms.

We believe the building blocks for solving this should be open, so that local manufacturers, schools, researchers and health programmes can adapt, audit and scale them.

## Traction

- Over **9,600** Jolly Devices supplied to women and girls
- Pilot running in **Kisumu, Kenya** for almost a year
- **65%** of users reduced their painkiller intake
- Botsolai AI in final training, improving continuously from user data

## What's in this repository

| Component | Status | Licence |
|---|---|---|
| [`data-standard/`](data-standard/): Open Menstrual Pain Log schema (v0.1) | ✅ Released | Apache 2.0 |
| `firmware/`: Jolly Device TENS control firmware | 🔜 Planned | Apache 2.0 |
| `hardware/`: Jolly Device schematics and PCB design files | 🔜 Planned | CERN-OHL-W v2 |
| `botsolai-sdk/`: pain-tracking SDK for apps and health systems | 🔜 Planned | Apache 2.0 |
| `model-cards/`: documentation of Botsolai models, evaluation and safeguards | 🔜 Planned | CC BY 4.0 |

See [ROADMAP.md](ROADMAP.md) for the release timeline.

## The data standard

The **Open Menstrual Pain Log** is a simple, privacy-first JSON format for recording menstrual cycle and pain data. It is designed so that different apps, school health programmes and hospital systems (HMIS) can share menstrual health data in a common structure.

Key design choices:

- **Privacy-first**: no names, phone numbers, free-text notes or exact birth dates. Users are identified only by pseudonymous IDs and age bands.
- **Low-resource ready**: small payloads that work offline and sync later.
- **Built for adolescents**: captures what matters for girls, including impact on school attendance.
- **Clinically useful**: structured pain scores (0–10), symptoms and interventions that help flag possible conditions like endometriosis.

Validate a record:

```bash
pip install jsonschema
python -c "import json, jsonschema; jsonschema.validate(json.load(open('data-standard/examples/log-entry.json')), json.load(open('data-standard/menstrual-pain-log.schema.json'))); print('valid')"
```

## Principles

We follow the [Principles for Digital Development](https://digitalprinciples.org/) and aim for recognition as a [Digital Public Good](https://digitalpublicgoods.net/).

## Contributing

We welcome contributions from developers, clinicians, researchers and health programmes. See [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

Software and data standard: [Apache License 2.0](LICENSE). Hardware design files, when released: CERN-OHL-W v2.

## Contact

Swift Wellness Limited, Nairobi, Kenya · [swifthealth.care](https://swifthealth.care)
