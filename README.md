<!-- <div id="top">

<!-- HEADER STYLE: CLASSIC -->
<div align="center">

# HORIZON SCAN PROTOTYPE

<!-- BADGES -->
<img src="https://img.shields.io/github/license/SokolAnn/Horizon_Scan_Prototype" alt="License">
<img src="https://img.shields.io/github/last-commit/SokolAnn/Horizon_Scan_Prototype?style=flat&logo=git&logoColor=white&color=0080ff" alt="Last Commit">
<img src="https://img.shields.io/github/languages/top/SokolAnn/Horizon_Scan_Prototype?style=flat&color=0080ff" alt="Top Language">
<img src="https://img.shields.io/github/languages/count/SokolAnn/Horizon_Scan_Prototype?style=flat&color=0080ff" alt="Language Count">

<img src="https://img.shields.io/badge/Python-3776AB.svg?style=flat&logo=Python&logoColor=white" alt="Python">
<img src="https://img.shields.io/badge/Jupyter-F37626.svg?style=flat&logo=Jupyter&logoColor=white" alt="Jupyter">
<img src="https://img.shields.io/badge/Pandas-150458.svg?style=flat&logo=pandas&logoColor=white" alt="Pandas">
<img src="https://img.shields.io/badge/Neo4j-008CC1.svg?style=flat&logo=neo4j&logoColor=white" alt="Neo4j">
<img src="https://img.shields.io/badge/OpenAI-412991.svg?style=flat&logo=OpenAI&logoColor=white" alt="OpenAI">

</div>
<br/>

Automated horizon scanning for non native animals and terrestrial plants in the Southeastern United States. The pipeline retrieves evidence, extracts mechanistic signals from text, represents them in a knowledge graph, and produces RRAT style scores with traceable citations.

**Who is this for?** Invasion ecologists, conservation practitioners, biosecurity teams, and researchers building reproducible, evidence grounded risk triage workflows.

</div>

## Contents

- <a href="#scope">Scope</a>
- <a href="#inputs">Inputs</a>
- <a href="#workflow">Workflow</a>
- <a href="#scoring">RRAT scoring</a>
- <a href="#confidence">Confidence and traceability</a>
- <a href="#repo-structure">Repository structure</a>
- <a href="#quickstart">Quickstart</a>
- <a href="#limitations">Limitations</a>
- <a href="#license">License</a>

## Scope

- Region: Southeastern United States
- Species: non native to the Southeast, may be native elsewhere in the United States
- Inclusion rule: each species must have an invasion history, meaning it has been moved outside its native range at least once
- Exclusions: marine species and aquatic plants
- Project type: horizon scan (rapid triage), with stronger documentation than typical horizon scans

## Inputs

This repo is currently organized around these working inputs.

- `data/species/Species.xlsx`
  - Canonical candidate species list for the horizon scan.
- `data/eddmaps/HORIZON_SCAN_combined.xlsx`
  - EDDMapS export used for occurrence evidence and follow up records.
  - Key sheets: `observations`, `revisits`, `species`, `data_dictionary`.
- `data/climatch/species_for_climatch.csv`
  - Input points per species for climate matching and reproducible reruns.
- `data/rubric/SERISCC_HS_RRAT(Scoring Tables).csv`
  - RRAT scoring table definitions used to align scoring and rater training.

Planned external sources are tracked as citations and derived facts (not necessarily stored as full text).

- USGS NAS: occurrence context and pathway narratives
- IUCN spatial data: range polygons for distribution context
- EPA traits database and global trait syntheses: structured trait backfill and cross checks
- Primary and gray literature: mechanistic evidence for pathways, establishment, impacts, and management

## Workflow

1. Load and normalize species names.
2. Ingest occurrence evidence (EDDSMapS export, and additional sources as available).
3. Prepare climate match inputs and compute climate similarity outputs.
4. Retrieve literature and reports per species using reproducible query templates.
5. Extract evidence into structured records (pathways, dispersal, reproduction, overwintering, impacts, management outcomes), each linked to a citation.
6. Build a knowledge graph (species, traits, pathways, locations, invasion events, impacts, management actions, evidence).
7. Score each species using the RRAT rubric and generate an explanation tied to evidence IDs.
8. Assign confidence separately from risk, then run student validation and adjudication for disagreements.

## RRAT scoring

Four dimensions are scored from 1 to 5.

- Arrival (pathway): dispersal mechanisms and pathways, including anthropogenic movement and spread dynamics.
- Impact: ecological, socio economic, and human health effects.
- Ease of eradication: higher means harder to manage, lower feasibility.
- Climate match: derived from climate similarity outputs and binned to 1 to 5.

Final risk score:

`FinalRisk = ArrivalPathway * Impact * EaseOfEradication * ClimateMatch`

The authoritative scoring language is kept in:

- `data/rubric/SERISCC_HS_RRAT(Scoring Tables).csv`

## Confidence and traceability

Risk score and confidence are separate.

- Risk score answers: how risky is this species likely to be, given the evidence.
- Confidence answers: how strong, consistent, and traceable is the evidence supporting the score.

Every score must be supported by evidence items that include:

- a citation pointer (paper, report, database page)
- a short supporting snippet
- extracted structured fields (for example pathway type, dispersal distance, overwintering claim)

Confidence is recorded on a 1 to 5 scale based on evidence coverage, source quality, consistency, traceability, and recency.

## Repository structure

```text
.
├── data/
│   ├── species/Species.xlsx
│   ├── eddmaps/HORIZON_SCAN_combined.xlsx
│   ├── climatch/species_for_climatch.csv
│   └── rubric/SERISCC_HS_RRAT(Scoring Tables).csv
├── notebooks/
│   ├── Horizon_SCAN.ipynb
│   └── Horizon_SCAN_v1.ipynb
├── src/                 # pipeline code
├── prompts/             # versioned prompts
├── configs/             # run configs, region definitions
└── outputs/             # generated artifacts (recommended: gitignore)
```

## Quickstart

1. Create an environment and install dependencies.
2. Put the input files into the `data/` subfolders listed above.
3. Run the prototype notebooks in `notebooks/`.
4. Write outputs to `outputs/`.

Suggested conventions:

- Keep a run manifest with date, git commit hash, and settings for climate match and retrieval queries.
- Do not commit restricted full text. Commit citations and derived structured outputs instead.

## Limitations

- A horizon scan is not a full formal risk assessment, outputs should be interpreted as triage support.
- Evidence quality varies widely across taxa, confidence should be used to prioritize expert review.
- Full text access and usage rights vary by publisher and source.

## License

Add a license before public release. If the repository contains code and derived metadata only, permissive licenses like MIT or Apache 2.0 are common. If it includes restricted content, keep it private and publish only what you are allowed to share.

<p align="right">(<a href="#top">back to top</a>)</p>
 -->
