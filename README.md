<div id="top"></div>

<div align="center">

# 🌍 HORIZON SCAN PROTOTYPE

**Automated invasion risk triage for non-native species in the Southeastern US**

[![License](https://img.shields.io/github/license/SokolAnn/Horizon_Scan_Prototype?style=for-the-badge)](LICENSE)
[![Last Commit](https://img.shields.io/github/last-commit/SokolAnn/Horizon_Scan_Prototype?style=for-the-badge&logo=git&logoColor=white&color=0080ff)](https://github.com/SokolAnn/Horizon_Scan_Prototype/commits)
[![Top Language](https://img.shields.io/github/languages/top/SokolAnn/Horizon_Scan_Prototype?style=for-the-badge&color=0080ff)](https://github.com/SokolAnn/Horizon_Scan_Prototype)

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=Python&logoColor=white)](https://python.org)
[![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=Jupyter&logoColor=white)](https://jupyter.org)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org)
[![Neo4j](https://img.shields.io/badge/Neo4j-008CC1?style=for-the-badge&logo=neo4j&logoColor=white)](https://neo4j.com)
[![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=OpenAI&logoColor=white)](https://openai.com)

</div>

---

A pipeline that retrieves ecological literature, extracts invasion-relevant signals from text, builds a knowledge graph, and produces **RRAT-style risk scores** with traceable citations — targeting non-native animals and terrestrial plants in the Southeastern United States.

> **Who is this for?** Invasion ecologists, conservation practitioners, biosecurity teams, and researchers building reproducible, evidence-grounded risk triage workflows.

## 📖 Documentation

Full project documentation lives in the **[Wiki](../../wiki)**:

| Page | What you'll find |
|:--|:--|
| [Project Overview](../../wiki/Project-Overview) | Scope, research questions, hypotheses, significance |
| [Data Sources](../../wiki/Data-Sources) | All input files and external databases with links |
| [Pipeline & Workflow](../../wiki/Pipeline-and-Workflow) | 8-step architecture from species list to scored output |
| [RRAT Scoring Rubric](../../wiki/RRAT-Scoring-Rubric) | Full 1–5 criteria for Arrival, Impact, Eradication, Climate |
| [Confidence & Traceability](../../wiki/Confidence-and-Traceability) | Evidence quality framework and citation requirements |
| [Knowledge Graph Schema](../../wiki/Knowledge-Graph-Schema) | Neo4j entity types, relationships, and design |
| [Literature Retrieval](../../wiki/Literature-Retrieval) | Query templates, source types, fallback strategy |
| [Validation Plan](../../wiki/Validation-Plan) | Human vs. AI comparison and student scoring workflow |
| [FAQ](../../wiki/FAQ) | Key project questions answered |
| [Future Work](../../wiki/Future-Work) | SWAP integration, planned extensions |

## 🚀 Quickstart

```bash
# 1. Clone and set up
git clone https://github.com/SokolAnn/Horizon_Scan_Prototype.git
cd Horizon_Scan_Prototype
pip install -r requirements.txt

# 2. Place input files into data/ subfolders (see Wiki → Data Sources)

# 3. Run notebooks
jupyter notebook notebooks/Horizon_SCAN.ipynb

# 4. Outputs → outputs/
```

## 🗂️ Repository Structure

```
📦 Horizon_Scan_Prototype
├── 📂 data/
│   ├── species/          ← Species.xlsx
│   ├── eddmaps/          ← HORIZON_SCAN_combined.xlsx
│   ├── climatch/         ← species_for_climatch.csv
│   └── rubric/           ← SERISCC_HS_RRAT(Scoring Tables).csv
├── 📂 notebooks/         ← Prototype Jupyter notebooks
├── 📂 src/               ← Pipeline code
├── 📂 prompts/           ← Versioned LLM prompts
├── 📂 configs/           ← Run configs, region definitions
└── 📂 outputs/           ← Generated artifacts (gitignored)
```

## ⚠️ Limitations

> [!IMPORTANT]
> - A horizon scan is **not** a full formal risk assessment — outputs are **triage support**.
> - Evidence quality varies across taxa — use [confidence scores](../../wiki/Confidence-and-Traceability) to prioritize expert review.
> - Full-text access and usage rights vary by publisher.

## 📄 License

Add a license before public release. For code and derived metadata, **MIT** or **Apache 2.0** are common choices.

---

<div align="center">

**[📖 Read the Wiki](../../wiki)** · **[⬆ Back to Top](#top)**

Made with 🌿 for invasion ecology

</div>
