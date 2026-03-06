# open-dpp

Open tools for EU Digital Product Passport compliance. No paywalls, no newsletters, no noise.

**→ [View the legislation tracker](https://rhys-the-davies.github.io/open-dpp)**
**→ [View the textile schema](https://rhys-the-davies.github.io/open-dpp/schemas/textile/schema.html)**

---

## What's in this repo

Two tools, maintained together.

### Legislation tracker

Tracks the regulatory milestones that determine when DPP obligations arrive — across four parallel EU regulatory tracks.

| Track | Regulation | Key deadline |
|---|---|---|
| ESPR Framework | Reg. (EU) 2024/1781 | Textile DPP mandatory ~2028 |
| Battery Passport | Reg. (EU) 2023/1542 | Mandatory 18 Feb 2027 |
| Textile & Apparel DPP | ESPR delegated act (forthcoming) | Consultation expected 2026 |
| CRMA Permanent Magnet Passport | Reg. (EU) 2024/1252 | Mandatory 24 May 2027 |

The rule here is simple: every claim links to a primary source. No speculation, no secondary-source-as-fact. If something is uncertain or unverified, it's marked as such.

The canonical data source is `data/milestones.json`. `index.html` currently embeds the data directly for portability — a future release will fetch from the JSON at runtime.

### Textile DPP field schema

An open field schema for ESPR-compliant textile Digital Product Passports. The textile delegated act is still pending — so rather than wait, this schema maps what the regulation already requires against what the delegated act is expected to confirm.

Every field carries its regulatory basis, mandate status, access tier, data behaviour, and a plain-language description of who is responsible for it.

The schema lives in `schemas/textile/` and has two forms: `schema.json` for implementation, `schema.html` for human review. A `schemas/batteries/` directory is reserved for a future implementation based on the Battery Regulation.

---

## Repo structure

```
open-dpp/
├── index.html              # Legislation tracker (self-contained)
├── data/
│   └── milestones.json     # Canonical tracker data
├── schemas/
│   └── textile/
│       ├── schema.json     # Field schema (canonical)
│       └── schema.html     # Human-readable schema viewer
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## How to use it locally

No build step, no dependencies, no server required for the legislation tracker.

```bash
git clone https://github.com/rhys-the-davies/open-dpp.git
cd open-dpp
open index.html
```

The schema viewer fetches `schema.json` at runtime, so it needs a local server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/schemas/textile/schema.html
```

---

## Contributing

This project runs on contributions. We particularly need help from compliance teams, legal professionals, policy researchers, and sustainability leads at brands navigating these requirements.

See [CONTRIBUTING.md](CONTRIBUTING.md) for full guidance. The short version:

- **Verify a milestone** — check a primary source and confirm the tracker data is accurate
- **Correct an error** — something is wrong or outdated, open an issue or submit a fix
- **Add a missing milestone** — something relevant isn't tracked yet
- **Propose a new schema field** — with regulatory basis, mandate status, and access tier
- **Improve either tool** — the tracker or schema themselves, not just the data

Browse [open issues](https://github.com/rhys-the-davies/open-dpp/issues) to find something to pick up.

---

## Licence

Released under [CC BY-SA 4.0](LICENSE). Free to use, adapt, and redistribute with attribution, under the same licence.

---

## About

These tools were started by [AWARE™](https://aware.community) — a textile supply chain traceability platform helping brands and manufacturers prepare for DPP requirements. They are open for contribution and not affiliated with or endorsed by any regulatory body.

[aware.community](https://aware.community) · [hello@aware.community](mailto:hello@aware.community)
