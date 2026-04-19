# Growth-modelling-using-ELEFAN
# Non‑Bootstrap ELEFAN Workflow for Estimating VBGF Parameters  
This repository contains a reproducible R workflow for estimating **Von Bertalanffy Growth Function (VBGF)** parameters using **non‑bootstrap ELEFAN** routines from the **TropFishR** package.  
The workflow is designed to run automatically across multiple scenarios (GSA × period × sex).

---

## 📦 Methods
We use the ELEFAN implementation from **TropFishR** to estimate:

- **L∞** (asymptotic length)  
- **K** (growth coefficient)  
- **t₀** (optional)  
- **Rn** (goodness‑of‑fit score)

The workflow:
1. Reads length‑frequency data in wide or long format  
2. Converts to `lfq` objects  
3. Runs ELEFAN without bootstrapping  
4. Saves parameter tables and plots for each scenario  

---

## 📁 Repository Structure


---

## 🔧 Requirements

```r
install.packages(c("TropFishR", "tidyverse"))
```
Reference and Attribution
This repository uses the ELEFAN implementation from TropFishR.
Please cite:

Mildenberger, T. K., Taylor, M. H., & Wolff, M. (2017).
TropFishR: an R package for fisheries analysis with length‑frequency data.  
Methods in Ecology and Evolution, 8(11), 1520–1527.
https://doi.org/10.1111/2041-210X.12791

---

# ✅ **CITATION.bib (ready to paste)**

```r
bibtex
@Article{TropFishR2017,
  title   = {TropFishR: an R package for fisheries analysis with length-frequency data},
  author  = {Mildenberger, Tobias K. and Taylor, Martin H. and Wolff, Matthias},
  journal = {Methods in Ecology and Evolution},
  year    = {2017},
  volume  = {8},
  number  = {11},
  pages   = {1520--1527},
  doi     = {10.1111/2041-210X.12791}
}
```
