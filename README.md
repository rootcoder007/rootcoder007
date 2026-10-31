
<div align="center">

[![NOQTIS release](https://img.shields.io/github/v/release/rootcoder007/noqtis?style=for-the-badge&label=NOQTIS&color=2ea44f)](https://github.com/rootcoder007/noqtis/releases/latest)
[![Documentation](https://img.shields.io/badge/NOQTIS-Documentation-1a1a4e?style=for-the-badge)](https://rootcoder007.github.io/noqtis/)
[![License: Apache-2.0 WITH LLVM-exception](https://img.shields.io/badge/License-Apache--2.0%20WITH%20LLVM--exception-0b7285?style=for-the-badge)](https://github.com/rootcoder007/noqtis/blob/main/LICENSE)

[![OpenSSF Best Practices](https://www.bestpractices.dev/projects/16049/badge)](https://www.bestpractices.dev/projects/16049)
[![PyPI](https://img.shields.io/pypi/v/noqtis?label=PyPI&color=3775a9)](https://pypi.org/project/noqtis/)
[![npm](https://img.shields.io/npm/v/noqtis?label=npm&color=cb3837)](https://www.npmjs.com/package/noqtis)
[![crates.io](https://img.shields.io/crates/v/noqtis?label=crates.io&color=f0b400)](https://crates.io/crates/noqtis)
[![Maven Central](https://img.shields.io/maven-central/v/io.github.rootcoder007/noqtis?label=Maven%20Central&color=6f42c1)](https://central.sonatype.com/artifact/io.github.rootcoder007/noqtis)
[![Go Reference](https://pkg.go.dev/badge/github.com/rootcoder007/noqtis/bindings/go.svg)](https://pkg.go.dev/github.com/rootcoder007/noqtis/bindings/go)
[![r-universe](https://rootcoder007.r-universe.dev/badges/noqtis)](https://rootcoder007.r-universe.dev/noqtis)
[![COPR](https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fcopr.fedorainfracloud.org%2Fapi_3%2Fpackage%2F%3Fownername%3Drootcoder007%26projectname%3Dnoqtis%26packagename%3Dnoqtis%26with_latest_build%3Dtrue&query=%24.builds.latest.state&label=COPR%20build&color=2ea44f)](https://copr.fedorainfracloud.org/coprs/rootcoder007/noqtis/)
[![OBS](https://build.opensuse.org/projects/home:rootcoder007/packages/noqtis/badge.svg?type=default)](https://build.opensuse.org/package/show/home:rootcoder007/noqtis)

</div>

**[NOQTIS](https://github.com/rootcoder007/noqtis)** (Notary Of Quantum-safe Traceable Inputs and Seals): seal the exact files behind a result with a post-quantum signature (ML-DSA, SLH-DSA, ML-KEM, in C11), so anyone can check later, offline, that nothing changed. Docs: [rootcoder007.github.io/noqtis](https://rootcoder007.github.io/noqtis/).

```bash
brew install rootcoder007/noqtis/noqtis                               # macOS/Linux
curl -fsSL https://github.com/rootcoder007/noqtis/releases/latest/download/install.sh | sh
sudo dnf copr enable rootcoder007/noqtis && sudo dnf install noqtis   # Fedora, EPEL
docker run --rm ghcr.io/rootcoder007/noqtis                           # container (Wolfi)
pip install noqtis                                                    # Python
npm install noqtis                                                    # JavaScript (WebAssembly)
cargo add noqtis                                                      # Rust
go get github.com/rootcoder007/noqtis/bindings/go@latest              # Go
Rscript -e 'install.packages("noqtis",
  repos = "https://rootcoder007.r-universe.dev")'                     # R
```

```powershell
irm https://github.com/rootcoder007/noqtis/releases/latest/download/install.ps1 | iex   # Windows
```

Java (Maven Central): `io.github.rootcoder007:noqtis`. Debian, Ubuntu and openSUSE: the [openSUSE Build Service repositories](https://build.opensuse.org/package/show/home:rootcoder007/noqtis) (commands on the [install page](https://rootcoder007.github.io/noqtis/start/install/)).

---

<div align="center">

[![PyPI](https://img.shields.io/pypi/v/morie?style=for-the-badge&label=PyPI%20morie&color=3776AB&logo=pypi&logoColor=white)](https://pypi.org/project/morie/)
[![CRAN](https://img.shields.io/cran/v/rmoriebricklayer?style=for-the-badge&label=CRAN%20rmoriebricklayer&color=276DC3&logo=r&logoColor=white)](https://cran.r-project.org/package=rmoriebricklayer)
[![r-universe](https://img.shields.io/badge/r--universe-rmorie-0f3460?style=for-the-badge&logo=r&logoColor=white)](https://rootcoder007.r-universe.dev/rmorie)
[![apt and dnf](https://img.shields.io/badge/apt%20%26%20dnf-apt--morie-a81d33?style=for-the-badge&logo=debian&logoColor=white)](https://github.com/rootcoder007/apt-morie)
[![License: AGPL v3](https://img.shields.io/badge/License-AGPLv3-d97706?style=for-the-badge)](https://www.gnu.org/licenses/agpl-3.0)

</div>

**MORIE** (Python [`morie`](https://github.com/rootcoder007/morie); R [`rmorie`](https://github.com/rootcoder007/rmorie), [`rmoriedata`](https://github.com/rootcoder007/rmoriedata), [`rmoriebricklayer`](https://github.com/rootcoder007/rmorie-bricklayer); GitHub Action [`rmbl-action`](https://github.com/rootcoder007/rmbl-action)):

```bash
pip install morie                                                     # Python: morie
Rscript -e 'install.packages(c("rmoriebricklayer", "rmoriedata"))'    # R, from CRAN
Rscript -e 'install.packages("rmorie",
  repos = "https://rootcoder007.r-universe.dev")'                     # R: rmorie (r-universe)
brew tap rootcoder007/morie && \
  brew install morie rmorie rmoriebricklayer rmoriedata               # macOS/Linux, CLI and R packages
# - uses: rootcoder007/rmbl-action@v1                                  # GitHub Actions: check data capsules in CI
```

Debian / Ubuntu, from the signed [apt-morie](https://github.com/rootcoder007/apt-morie) repository:

```bash
sudo install -d -m 0755 /etc/apt/keyrings
curl -fsSL https://rootcoder007.github.io/apt-morie/key.gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/rootcoder007.gpg
echo "deb [signed-by=/etc/apt/keyrings/rootcoder007.gpg] https://rootcoder007.github.io/apt-morie/apt stable main" \
  | sudo tee /etc/apt/sources.list.d/morie.list
sudo apt update
sudo apt install morie rmorie rmoriedata rmoriebricklayer
```

Fedora 41+ (dnf5), from the same repository:

```bash
sudo dnf config-manager addrepo --from-repofile=https://rootcoder007.github.io/apt-morie/rpm/morie.repo
sudo dnf install morie rmorie rmoriedata rmoriebricklayer
```

Website: [rmorie.com](https://www.rmorie.com) (packages, methods, verification, data terms) with the rmoriebricklayer page at [rmorie.com/provenance](https://www.rmorie.com/provenance/); the hosted tables are served from [data.rmorie.com](https://data.rmorie.com) with a key from [rmorie.com/access](https://www.rmorie.com/access/); save cited sources via [archive.rmorie.com](https://archive.rmorie.com).

<div align="center">

[![MORIE documentation](https://img.shields.io/badge/MORIE-Documentation-1a1a4e?style=for-the-badge&logo=readthedocs&logoColor=white)](https://rootcoder007.github.io/morie/)
[![r-universe](https://img.shields.io/badge/r--universe-0f3460?style=for-the-badge&logo=r&logoColor=white)](https://rootcoder007.r-universe.dev)

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![R](https://img.shields.io/badge/R-276DC3?style=flat&logo=r&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=flat&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=flat&logo=cplusplus&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

</div>

---

**Upstream.** Contributor to rOpenSci's statistical-software review tooling:
[pkgstats](https://github.com/ropensci-review-tools/pkgstats),
[pkgcheck](https://github.com/ropensci-review-tools/pkgcheck), [srr](https://github.com/ropensci-review-tools/srr) and [review-tools actions](https://github.com/ropensci-review-tools/actions).

