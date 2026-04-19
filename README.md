# Growth-modelling-using-ELEFAN
# Non‑Bootstrap ELEFAN Workflow for Estimating VBGF Parameters  
This repository contains a reproducible R workflow for estimating **Von Bertalanffy Growth Function (VBGF)** parameters using **non‑bootstrap ELEFAN** routines from the **TropFishR** package.  
The workflow is designed to run automatically across multiple scenarios (GSA × period × sex).

## 🔍 ELEFAN Methods Used in This Workflow

This repository implements **three different ELEFAN optimisation approaches** from the TropFishR ecosystem to estimate Von Bertalanffy Growth Function (VBGF) parameters:

### 1. Classic ELEFAN
The traditional ELEFAN algorithm fits growth curves by scanning through combinations of **L∞** and **K** and selecting the parameter set that maximises the **Rn** goodness‑of‑fit statistic.  
This method is deterministic and fast, making it suitable for exploratory analyses or large scenarios.

### 2. ELEFAN_SA (Simulated Annealing)
ELEFAN_SA uses **simulated annealing**, a stochastic optimisation technique that allows controlled random jumps in parameter space.  
Advantages:
- Better at escaping local minima  
- More robust for noisy or sparse LFQ data  
- Produces smoother optimisation surfaces  

### 3. ELEFAN_GA (Genetic Algorithm)
ELEFAN_GA uses a **genetic algorithm** inspired by biological evolution.  
Advantages:
- Very effective for complex LFQ structures  
- Handles multimodal optimisation landscapes  
- Often finds higher‑quality solutions than classic ELEFAN  

### Why use all three?
Each optimisation method has strengths and weaknesses.  
Running all three allows:

- Cross‑validation of growth parameter estimates  
- Identification of stable parameter regions  
- Detection of scenarios where optimisation is difficult  
- More defensible biological interpretation  

The workflow automatically runs **ELEFAN**, **ELEFAN_SA**, and **ELEFAN_GA** for each scenario and stores:

- Parameter tables  
- Diagnostic plots  
- Optimisation summaries  

---

## 📦 Required R Packages

The workflow depends on the following packages:

```r
# Core
library(TropFishR)
library(fishboot)
library(here)

# Data and plots
library(readxl)
library(dplyr)
library(tidyr)
library(ggplot2)
library(stringr)

```
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

# bibtex

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
