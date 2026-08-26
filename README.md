# FinRAG-QA
 
**A benchmark dataset for financial question answering over banks' annual and Pillar 3 reports.**
 
FinRAG-QA contains 999 practitioner-curated questions on 10 standardised financial indicators, grounded in 209 annual and Pillar 3 reports published by 24 major European and U.S. banks over the period 2019–2023. Unlike prior financial QA benchmarks, which centre on U.S. filings and single-institution analysis, FinRAG-QA targets **cross-institutional retrieval** over long regulatory documents (198k words on average).
 
📄 **Paper (SSRN pre-print):** [Enhancing Financial Question Answering: A Novel Benchmark Dataset of Banks' Financial Statements](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7243178)
 
<!-- ---
 
## Repository structure
 
```
FinRAG-QA/
├── data/
│   └── finrag_qa.csv        # the 999 benchmark rows
├── docs/
│   └── source_documents.md  # references to the 209 public source reports
├── LICENSE
└── README.md
```
 
> Adjust the paths above to match the final layout of the repository.
 
--- -->
 
## Dataset
 
### Schema
 
| Column | Description |
|---|---|
| `Data` | Name of the financial indicator (10 distinct values). |
| `Year` | Reporting year the figure refers to (2019–2023). |
| `Bank` | Institution the figure refers to (24 banks). |
| `Doc Type` | Type of source document: *Financial Report* or *Pillar 3*. |
| `Query` | The question submitted to the system, in a standardised template (see below). |
| `Value` | Ground-truth value, a decimal number in millions, in the currency of the source document. All ground truths are "simple" values, i.e. never derived by combining other figures. |
| `Numerical` | Whether the value is reported in explicit numerical form. In 21 cases the value is not available and is expressed in natural language or as a dash (−) in a table. |
| `In table` | Whether the value appears inside a table (`Y`) or in running text (`N`) in the source document. |
| `Source Document Year` | Publication year of the source document, which may differ from `Year` because reports include comparative figures for previous periods. |
 
### Query template
 
```
What is the consolidated <Data> value in millions for <Bank> for the year <Year>?
```
 
### Indicators covered
 
Common Equity Tier 1 (CET1) capital · Day One Profit · Total Additional Valuation Adjustments (AVA) · Total Assets · Total Fair Value Level 1 / 2 / 3 Assets · Total Fair Value Level 1 / 2 / 3 Liabilities
 
### Example row
 
| Data | Year | Bank | Doc Type | Query | Value | Numerical | In table | Source Document Year |
|---|---|---|---|---|---|---|---|---|
| Total Assets | 2023 | Banco BPM | Report | What is the consolidated Total Assets value in millions for Banco BPM for the year 2023? | 202131.973 | Y | Y | 2023 |
 
---
 
## Citation
 
If you use FinRAG-QA, please cite:
 
```bibtex
@misc{miola2026finragqa,
  title        = {Enhancing Financial Question Answering: A Novel Benchmark
                  Dataset of Banks' Financial Statements},
  author       = {Miola, Arianna and Spaccavento, Bruno and Silotto, Lorenzo
                  and Bianchetti, Marco and Cagliero, Luca},
  year         = {2026},
  howpublished = {SSRN pre-print},
  url          = {https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7243178}
}
```
 
---
 
<!-- ## License
 
The dataset is released under [LICENSE — to be specified]. -->
 
 
## Disclaimer
 
The views expressed here are those of the authors and do not necessarily reflect those of their respective institutions.