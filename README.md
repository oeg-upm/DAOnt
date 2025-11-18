## DAOnt: EU Data Act Ontology

Formal Ontology for Automated Compliance with Regulation (EU) 2023/2854 


Ontology published at: <https://w3id.org/def/daont>

### Overview

This repository provides the first comprehensive ontology for the EU Data Act (Regulation 2023/2854), enabling automated deontic reasoning and compliance verification across business-to-consumer (B2C), business-to-business (B2B), and business-to-government (B2G) data-sharing scenarios.

The ontology integrates 3 foundational standards—LKIF-Core, ODRL, and DPV—to model obligations, permissions, and prohibitions in machine-readable form.
It allows organizations to verify compliance, detect violations, and evaluate FRAND conditions through SPARQL queries and semantic reasoning.

Applicable from September 12, 2025, the EU Data Act introduces complex requirements for data access and sharing. This ontology bridges the gap between legal text and computational enforcement, supporting interoperability in European data spaces and automated contract validation.

### Key Features

- Semantic Representation of the Data Act

    - Models rights, duties, and prohibitions across B2C, B2B, and B2G contexts.

    - Includes formal representations of:

      - Article 4(1) – B2C user access rights

      - Article 8(6) – B2B trade secret exceptions

      - Article 19(2)(a) – B2G competitive use prohibitions

- Multi-Standard Integration

- Automated Compliance Checking
  - SPARQL queries validate whether contractual terms satisfy Data Act requirements.
  - Python compliance checker (built with rdflib) executes reasoning tasks and reports results.
  - Results identify violations, exceptions, and unfulfilled obligations for each article-based contract.

## Repository Structure

```
compliance-checks/
│
├── contracts/
│
├── queries/
│   ├── query-4.1.sparql
│   ├── query-8.6.sparql
│   ├── query-19.2.a.sparql
│
├── compliance_checker.py      # Core reasoning and validation module
└── run_compliance_check.py    # CLI runner for automated checks
│
├── DAOnt.owl               # Main ontology (LegalRuleML + LKIF + ODRL + DPV)
├── DAOnt.ttl               # Turtle serialization
│
├── webvowl/                   # Visualization files (WebVOWL)
├── resources/                 # Auxiliary resources
├── sections/                  # Paper sectioned fragments
│
├── index-en.html              # Ontology HTML documentation
├── LICENSE
└── README.md
```

## Installation and Usage
- Prerequisites
  - Python 3.9+
  - RDFLib
  - SPARQLWrapper

Install dependencies:

``pip install rdflib sparqlwrapper``

- Run a Compliance Check
``python run_compliance_check.py``
or 
``python run_compliance_check.py --contract contracts/b2b_8.6.owl --query queries/query-8.6.update.sparql``

The system will:
- Load the specified contract ontology
- Execute the compliance SPARQL query
- Return the list of fulfilled, violated, or pending obligations


## Proof-of-Concept Examples

Each compliance scenario includes:
- Formalized contract ontology (.owl)
- SPARQL compliance queries
- Screenshot of results

| **Scenario** | **Article** | **Description** |
|---------------|--------------|-----------------|
| **B2C** | Art. 4(1) | User access rights to connected product data |
| **B2B** | Art. 8(6) | Trade secret exceptions and FRAND conditions |
| **B2G** | Art. 19(2)(a) | Prohibition of data use for competitive purposes |


## Citation
If you use this ontology, please cite the corresponding paper:
Toward A Formal Ontology for EU Data Act Compliance: Automated Deontic Reasoning for Data Sharing Agreements
In: Proceedings of the JURIX 2025 Conference on Conventicle on Artificial Intelligence Regulation and Safety

### 📄 License

This project is released under the **Creative Commons Attribution–ShareAlike (CC BY-SA 4.0)** license.  
You are free to share and adapt the material for any purpose, even commercially, provided that appropriate credit is given and adaptations are distributed under the same license.

See the full license text at: [https://creativecommons.org/licenses/by-sa/4.0/](https://creativecommons.org/licenses/by-sa/4.0/)
