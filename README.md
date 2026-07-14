<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a23,50:1a1a4e,100:0f3460&height=120&section=header" width="100%" alt="Header"/>

### Building tools that make science reproducible and accessible.

**University of Toronto** · causal inference · spatial statistics · reproducibility · post-quantum crypto

</div>

## The MORIE ecosystem

*Multi-domain Open Research and Inferential Estimation* — one methodology, shipped as a family of packages. Home of the **MRM (Multilevel Reconciliation Methodology)** framework.

| Package | What it is |
|---|---|
| [**rmorie**](https://github.com/rootcoder007/rmorie) | The flagship R toolkit — 1,800+ exported functions across causal inference (DML, AIPW, IPW, matching), spatial statistics (LISA, kriging, Kulldorff scans), Hawkes processes, psychometrics/IRT, survey-weighted inference, and the MRM framework. rOpenSci statistical-software standards addressed across all nine categories. |
| [**morie**](https://github.com/rootcoder007/morie) | The Python side — the same estimators with Python/R parity, 60+ built-in datasets in a portable SQLite layer, and a shared C/C++ core. |
| [**rmoriedata**](https://github.com/rootcoder007/rmoriedata) | Data-only companion — integrated open datasets (OTIS, CPADS, …) plus privacy primitives (differential privacy, k-anonymity). |
| [**rmorie-bricklayer**](https://github.com/rootcoder007/rmorie-bricklayer) | Brick-proof reproducibility capsules — compiled C provenance core, CKAN resolution, SHA-256 + Wayback provenance, synthetic fallback. |

<div align="center">

[![PyPI](https://img.shields.io/pypi/v/morie?style=for-the-badge&color=blue)](https://pypi.org/project/morie/)
[![rmorie on r-universe](https://rootcoder007.r-universe.dev/badges/rmorie?style=for-the-badge)](https://rootcoder007.r-universe.dev/rmorie)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPLv3-d97706?style=for-the-badge)](https://www.gnu.org/licenses/agpl-3.0)

</div>

```bash
pip install morie                                        # Python
Rscript -e 'install.packages("rmorie",
  repos = "https://rootcoder007.r-universe.dev")'        # R
brew tap rootcoder007/morie && brew install morie        # macOS/Linux CLI
```

Every result-emitting function returns a `RichResult` — a self-describing report (summary, tables, warnings, interpretation) that round-trips to JSON. One design, `(data, treatment, outcome, covariates)`, flows through any estimator; the MRM framework runs ~10 of them on one design and reconciles the answers.

<div align="center">

[![Site](https://img.shields.io/badge/projectmorie.com-0a0a23?style=for-the-badge&logo=firefox&logoColor=white)](https://projectmorie.com)
[![Documentation](https://img.shields.io/badge/Documentation-1a1a4e?style=for-the-badge&logo=readthedocs&logoColor=white)](https://rootcoder007.github.io/morie/)
[![r-universe](https://img.shields.io/badge/r--universe-0f3460?style=for-the-badge&logo=r&logoColor=white)](https://rootcoder007.r-universe.dev)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Flutter](https://img.shields.io/badge/Flutter-02569B?style=flat&logo=flutter&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

<img src="./coding-setup.gif" width="100%" alt="Coding setup animation"/>
</div>
