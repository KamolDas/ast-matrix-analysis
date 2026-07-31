# AST-Matrix: Audit Support System (ASS) for CLSI M23

## 🔬 Tiered Confusion-Matrix Audit Support System for Antimicrobial Susceptibility Testing Method Validation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo-RSV Lab.svg)](https://zenodo.org/communities/rsv-lab/records?q=&l=list&p=1&s=10&sort=newest)


## 📋 Overview

**AST-Matrix / Audit Support System (ASS)** is a standalone, CLSI M23-aligned method validation tool for antimicrobial susceptibility testing. It implements a five-layer tiered audit pipeline:

1. **Ingestion** - Load paired Reference/Candidate S-I-R-U calls
2. **Completeness Gate** - Data quality assessment
3. **Categorical Agreement** - S/I/R agreement with Cohen's Kappa
4. **Regulatory Binary Risk** - Very Major Error (VME) and Major Error (ME) with 95% CIs
5. **Verdict** - PASS / INVESTIGATE / FAIL with machine-readable trail


## 🎯 Why ASS-Matrix?

### The Problem

Clinical microbiology laboratories routinely compare a candidate AST method against a reference standard. Existing tools like AMRFinderPlus and ResFinder predict resistance from sequence data but **do not evaluate operational agreement between two phenotypic result streams**.

### The Solution

ASS-Matrix formalizes AST method comparison as a tiered confusion-matrix problem, applying:

- ✅ CLSI M23 acceptability thresholds
- ✅ Wilson 95% confidence intervals for small samples
- ✅ Cohen's Kappa with interpretation bands
- ✅ Category-specific sensitivity and PPV
- ✅ Naive vs. tiered comparison with discrepancy detection


## 🏆 Key Features

### Five-Layer Audit Pipeline

| Layer | Name | Function |
|-------|------|----------|
| 1 | **Ingestion** | Load paired Reference/Candidate calls; build 4×4 matrix |
| 2 | **Completeness Gate** | Require ≥ 90% data completeness |
| 3 | **Categorical Agreement** | 3×3 S/I/R matrix; Kappa; Minor Error |
| 4 | **Regulatory Binary Risk** | VME ≤ 1.5%, ME ≤ 3.0% with Wilson 95% CIs |
| 5 | **Verdict** | PASS / INVESTIGATE / FAIL with reason trail |

### Mathematical Rigor

- **VME**: $R \rightarrow S$ errors / total R × 100%
- **ME**: $S \rightarrow R$ errors / total S × 100%
- **Wilson 95% CI**: $(p + z^2/2n) \pm z \sqrt{p(1-p)/n + z^2/4n^2} / (1 + z^2/n)$
- **Cohen's Kappa**: $(P_o - P_e) / (1 - P_e)$
- **Completeness**: Complete pairs / Submitted pairs × 100%

### Visualization

- ✅ Publication-quality confusion matrices (3 tiers)
- ✅ Metrics dashboard with verdict display
- ✅ Sample-size adequacy plots
- ✅ Error distribution analysis
- ✅ Category-specific performance charts

### Export Formats

| Format | Content |
|--------|---------|
| **TXT** | Structured report with all metrics and matrices |
| **JSON** | Machine-readable summary |
| **CSV** | Raw data and summary table |
| **PNG** | Publication-quality figures (300 DPI) |
| **PDF** | Vector figures for journals |
| **SVG** | Editable vector graphics |
| **TIFF** | CMYK-ready for print |
| **EPS** | Vector for journal submissions |


## 🚀 Quick Start

### Installation

# Clone the repository
git clone https://github.com/KamolDas/ASS-Matrix.git
cd ASS-Matrix

# Install dependencies
pip install -r requirements.txt

# Run the notebook in Colab
# Open: https://colab.research.google.com/github/KamolDas/ASS-Matrix/blob/main/AST_Matrix_ASS_CLSI_M23.ipynb
