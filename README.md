<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a23,50:1a1a4e,100:0f3460&height=120&section=header" width="100%" alt="Header"/>
</div>

### 🚀 Building tools that make science reproducible and accessible.

- 🎓 **University of Toronto**
- 💻 Author of [**MORIE**](https://github.com/rootcoder007/morie) — dual-language (Python + R) scientific computing toolkit
- 🧠 **Causal inference, DML, IPW/AIPW, spatial analysis, IRT, post-quantum crypto**
- ⚡ ML on **Raspberry Pi 5** using TurboQuant quantization

---

<div align="center">

[![PyPI](https://img.shields.io/pypi/v/morie?style=for-the-badge&color=blue)](https://pypi.org/project/morie/)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPLv3-d97706?style=for-the-badge)](https://www.gnu.org/licenses/agpl-3.0)

</div>

**[MORIE](https://github.com/rootcoder007/morie)** — *Multi-domain Open Research and Inferential Estimation* —
is a multi-domain scientific computing toolkit hosting the **MRM
(Multilevel Reconciliation Methodology) framework** as its primary application for Canadian
carceral, police, and oversight data. Python + R parity across the same
estimators; 60+ built-in datasets shipped in a portable SQLite layer.

| Surface | What |
|---|---|
| **Causal estimators** | ATE / ATT / ATC / GATE / CATE / LATE, AIPW, G-computation, DML (PLR / IRM / PLIV), PSM, Rosenbaum bounds, E-value |
| **MRM framework** | 10-estimator ensemble + Mandela classifier (UN Rules 43/44) + χ² + provincial-vs-federal cross-comparison |
| **Spatial statistics** | Moran's I, LISA, Getis-Ord G\*, kriging, GWR, Ripley's K/L, Kulldorff space-time scan |
| **Hawkes processes** | Markovian Mohler-Bertozzi-Brantingham + non-Markovian Kwan-Chen-Dunsmuir kernels (Gamma / Weibull / Lomax) |
| **Statistical physics of crime** | Short-Brantingham reaction-diffusion, Bettencourt urban scaling, Lévy-flight tail, Lotka-Volterra |
| **Survey-weighted inference** | Horvitz-Thompson, Hájek, raking, complex-survey GLM, bootstrap + jackknife |
| **Psychometrics** | Cronbach α, McDonald ω, IRT (1PL/2PL/3PL/GRM), DIF, parallel analysis (250+ functions) |
| **Carbon-aware computing** | Pure-Python emissions tracker with 213-country IEA carbon-intensity data |

```python
import morie
df = morie.load_dataset("otis-2025")

# MRM module on OTIS data
from morie.otis_all_analyze import analyze_a01_mrm
result = analyze_a01_mrm(df)
print(result)
```

```r
library(morie)
cpads <- morie_load_dataset("cpads_2021")
ate   <- estimate_ate(cpads, "outcome", "treatment", c("age", "sex"))
```

<div align="center">

[![Explore MORIE](https://img.shields.io/badge/Explore_MORIE-0a0a23?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rootcoder007/morie)
[![Documentation](https://img.shields.io/badge/Documentation-rootcoder007.github.io-1a1a4e?style=for-the-badge&logo=readthedocs&logoColor=white)](https://rootcoder007.github.io/morie/)

</div>

> AI assistance via Anthropic Claude and Google Gemini / Vertex AI research-credit programs.

### 🧩 Architecture (estimator spine)

Every analysis function in MORIE returns a `RichResult`. Estimator
hierarchies share a common `BaseEstimator` contract; concrete classes
specialise it for a particular causal / spectral / sampling method.

```mermaid
classDiagram
  class RichResult {
    +str title
    +list summary_lines
    +list tables
    +list warnings
    +str interpretation
    +Any payload
    +__str__()
    +to_json()
  }

  class BaseEstimator {
    <<abstract>>
    +DataFrame data
    +str treatment
    +str outcome
    +list covariates
    +fit() RichResult
    +describe()
    +_check_inputs()*
    +_estimate()*
  }

  class IPWEstimator {
    +bool stabilised
  }
  class AIPWEstimator {
    +SuperLearner outcome_model
    +SuperLearner propensity_model
  }
  class DMLEstimator {
    +int n_folds
    +str score
  }
  class MatchingEstimator {
    +str method
    +int caliper
  }
  class HawkesEstimator {
    +str kernel
    +str baseline
  }

  BaseEstimator <|-- IPWEstimator
  BaseEstimator <|-- AIPWEstimator
  BaseEstimator <|-- DMLEstimator
  BaseEstimator <|-- MatchingEstimator
  BaseEstimator <|-- HawkesEstimator

  BaseEstimator ..> RichResult : returns
```

The MRM framework composes ten of these `BaseEstimator` subclasses on
a single (treatment, outcome, covariates) design and reports them in
one aggregate `RichResult`.

```mermaid
classDiagram
  class MRMModule {
    <<abstract>>
    +DataFrame data
    +str treatment
    +str outcome
    +list covariates
    +run() RichResult
  }

  class PerRowMRM
  class AggregateMRM {
    +str family
  }
  class MRMChiSquare {
    +ndarray table
  }
  class MandelaClassifier {
    +str jurisdiction
  }

  MRMModule <|-- PerRowMRM
  MRMModule <|-- AggregateMRM
  MRMModule <|-- MRMChiSquare
  MRMModule <|-- MandelaClassifier

  PerRowMRM o-- IPWEstimator
  PerRowMRM o-- AIPWEstimator
  PerRowMRM o-- DMLEstimator
  PerRowMRM o-- MatchingEstimator
```

---

## 🛠️ Technical Skills

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=flat&logo=go&logoColor=white)
![Shell](https://img.shields.io/badge/Shell-4EAA25?style=flat&logo=gnubash&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=mysql&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat&logo=javascript&logoColor=black)
![LaTeX](https://img.shields.io/badge/LaTeX-008080?style=flat&logo=latex&logoColor=white)
![Markdown](https://img.shields.io/badge/Markdown-000000?style=flat&logo=markdown&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)
![SciPy](https://img.shields.io/badge/SciPy-8CAAE6?style=flat&logo=scipy&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![MLX](https://img.shields.io/badge/MLX-000000?style=flat&logo=apple&logoColor=white)
![Ollama](https://img.shields.io/badge/Ollama-000000?style=flat&logo=ollama&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat&logo=plotly&logoColor=white)
![Sphinx](https://img.shields.io/badge/Sphinx-000000?style=flat&logo=sphinx&logoColor=white)
![Quarto](https://img.shields.io/badge/Quarto-75AADB?style=flat&logo=quarto&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=flat&logo=githubactions&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat&logo=postgresql&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry_Pi-A22846?style=flat&logo=raspberrypi&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)
![Ubuntu](https://img.shields.io/badge/Ubuntu-E95420?style=flat&logo=ubuntu&logoColor=white)
![macOS](https://img.shields.io/badge/macOS-000000?style=flat&logo=apple&logoColor=white)
![Tailscale](https://img.shields.io/badge/Tailscale-000000?style=flat&logo=tailscale&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-007ACC?style=flat&logo=visualstudiocode&logoColor=white)
![Neovim](https://img.shields.io/badge/Neovim-57A143?style=flat&logo=neovim&logoColor=white)
![Causal Inference](https://img.shields.io/badge/Causal_Inference-DML%2FIPW%2FAIPW-0a0a23?style=flat)
![Spatial Stats](https://img.shields.io/badge/Spatial-Moran%2FKriging%2FGWR-1a1a4e?style=flat)
![Psychometrics](https://img.shields.io/badge/Psychometrics-IRT%2FCTT%2FDIF-2a2a5e?style=flat)
![Survival](https://img.shields.io/badge/Survival-Cox%2FKM%2FLogRank-3a3a6e?style=flat)
![Bayesian](https://img.shields.io/badge/Bayesian-MCMC%2FGibbs-4a4a7e?style=flat)
![Hawkes](https://img.shields.io/badge/Hawkes-Markovian%2FNon--Markovian-5a5a8e?style=flat)
![Epidemiology](https://img.shields.io/badge/Epidemiology-SIR%2FSEIR%2FR0-6a6a9e?style=flat)
![Signal Processing](https://img.shields.io/badge/Signal_Processing-FFT%2FHRT%2FEMG-7a7aae?style=flat)
![Cryptography](https://img.shields.io/badge/Cryptography-ML--KEM%2FLattice-8a8abe?style=flat)
![Quantization](https://img.shields.io/badge/Quantization-TurboQuant-ff6600?style=flat)

</div>

---

## 📜 Research Interests

My research sits at the intersection of public-health epidemiology and
modern causal-inference methodology. On the substantive side I work on
environmental-health determinants of mental health and substance use,
and correctional and police-oversight data (Ontario OTIS, federal
SIU, Toronto Police Service) — drawing on Canadian PUMFs (CPADS,
CCS, CSADS, CSUS, CADS) and CIHI / PHAC aggregates. On the methodological side I focus on semiparametric
causal inference (double machine learning, AIPW, G-computation,
TMLE), Hawkes self-exciting point processes for spatiotemporal
crime data, spatial statistics (Moran's I, kriging, GWR), and
post-quantum cryptography for privacy-preserving analytics. Most of
this lives in MORIE as composable estimators sharing a single
`RichResult` contract.

---

<div align="center">

[![GitHub](https://img.shields.io/badge/GitHub-rootcoder007-181717?style=flat&logo=github&logoColor=white)](https://github.com/rootcoder007) [![PyPI](https://img.shields.io/badge/PyPI-morie-3776AB?style=flat&logo=pypi&logoColor=white)](https://pypi.org/project/morie/) [![ORCID](https://img.shields.io/badge/ORCID-0009--0004--1750--3592-A6CE39?style=flat&logo=orcid&logoColor=white)](https://orcid.org/0009-0004-1750-3592) [![Email](https://img.shields.io/badge/Email-vsruhela%40proton.me-8B5CF6?style=flat&logo=protonmail&logoColor=white)](mailto:vsruhela@proton.me)

</div>

---



<br/>

<div align="center">
<img src="./coding-setup.gif" width="100%" alt="Coding setup animation"/>
</div>
