## The MORIE ecosystem

*Multi-domain Open Research and Inferential Estimation* — one methodology, shipped as a family of packages. Home of the **MRM (Multilevel Reconciliation Methodology)** framework.

| Package | What it is |
|---|---|
| [**rmorie**](https://github.com/rootcoder007/rmorie) | The lean **R-only** carve for CRAN / rOpenSci — the same statistical core, 2,000+ exported functions across causal inference (DML, AIPW, IPW, matching), spatial statistics (LISA, kriging, Kulldorff scans), Hawkes processes, psychometrics/IRT, and survey-weighted inference. Dependency-light; rOpenSci statistical-software standards addressed across all nine categories. |
| [**morie**](https://github.com/rootcoder007/morie) | The full dual-language toolkit — **Python *and* R**, at parity — with bundled open datasets in a portable SQLite layer, a shared C/C++ core, and the complete MRM framework. The batteries-included home of the ecosystem. |
| [**rmoriedata**](https://github.com/rootcoder007/rmoriedata) | Data-only companion, 0.4.0 — public justice, policing and health tables (OTIS, CPADS, OCJ, SIU reports, Health Infobase and more) with checksums and a signed catalogue, plus privacy primitives (differential privacy, k-anonymity); on CRAN. |
| [**rmbl-action**](https://github.com/rootcoder007/rmbl-action) | GitHub Action, 1.0.1 — verifies, drift-checks, refreshes, reports and signs rmoriebricklayer data capsules in CI from a digest-pinned image: digests, schemas, HMAC/ML-DSA/XMSS bundles, source re-fetch with Wayback fallback, pull-request comments; capsules authored from any language; on the GitHub [**Marketplace**](https://github.com/marketplace/actions/rmbl-action). |
| [**rmoriebricklayer**](https://github.com/rootcoder007/rmorie-bricklayer) | Brick-proof reproducibility capsules, 1.0.2 — 431 functions and the `rmbl` shell: pinned sources, SHA-256 and Wayback provenance, drift screens, survey estimation, and post-quantum signatures (ML-KEM, ML-DSA, SLH-DSA, HQC, XMSS) in a compiled core with no system crypto library; on CRAN. |

<div align="center">

[![PyPI](https://img.shields.io/pypi/v/morie?style=for-the-badge&label=PyPI%20morie&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/morie/)
[![CRAN](https://img.shields.io/cran/v/rmoriebricklayer?style=for-the-badge&label=CRAN%20rmoriebricklayer&color=276DC3&logo=r&logoColor=white)](https://cran.r-project.org/package=rmoriebricklayer)
[![r-universe](https://img.shields.io/badge/r--universe-rmorie-0f3460?style=for-the-badge&logo=r&logoColor=white)](https://rootcoder007.r-universe.dev/rmorie)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPLv3-d97706?style=for-the-badge)](https://www.gnu.org/licenses/agpl-3.0)

</div>

```bash
pip install morie                                                     # Python: morie
Rscript -e 'install.packages(c("rmoriebricklayer", "rmoriedata"))'    # R, from CRAN
Rscript -e 'install.packages("rmorie",
  repos = "https://rootcoder007.r-universe.dev")'                     # R: rmorie (r-universe)
brew tap rootcoder007/morie && \
  brew install morie rmorie rmoriebricklayer rmoriedata               # macOS/Linux, CLI and R packages
```

Every result-emitting function returns a `RichResult` — a self-describing report (summary, tables, warnings, interpretation) that round-trips to JSON. One design, `(data, treatment, outcome, covariates)`, flows through any estimator; the MRM framework runs ~10 of them on one design and reconciles the answers.

**Upstream.** Contributor to rOpenSci's statistical-software review tooling:
[pkgstats](https://github.com/ropensci-review-tools/pkgstats),
[pkgcheck](https://github.com/ropensci-review-tools/pkgcheck), [srr](https://github.com/ropensci-review-tools/srr) and [review-tools actions](https://github.com/ropensci-review-tools/actions).

Website: [rmorie.com](https://www.rmorie.com) (packages, methods, verification, data terms) with the rmoriebricklayer page at [rmorie.com/provenance](https://www.rmorie.com/provenance/); the hosted tables are served from [data.rmorie.com](https://data.rmorie.com) with a key from [rmorie.com/access](https://www.rmorie.com/access/); save cited sources via [archive.rmorie.com](https://archive.rmorie.com).

<div align="center">

[![Documentation](https://img.shields.io/badge/Documentation-1a1a4e?style=for-the-badge&logo=readthedocs&logoColor=white)](https://rootcoder007.github.io/morie/)
[![r-universe](https://img.shields.io/badge/r--universe-0f3460?style=for-the-badge&logo=r&logoColor=white)](https://rootcoder007.r-universe.dev)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

</div>
