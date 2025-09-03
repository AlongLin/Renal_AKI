## Validation of an AKI Prediction Model in Decompensated Cirrhosis using MIMIC-III

### Introduction
Acute kidney injury (AKI) is a common and serious complication in patients with decompensated cirrhosis. Conventional assessments of kidney function, such as serum creatinine (sCr) and estimated glomerular filtration rate (eGFR), are often unreliable in this population because of confounding factors, including malnutrition and ascites. This project develops and validates a predictive model for AKI using routine admission data to support early intervention and efficient resource use.

### Methods
- **Design**: Retrospective cohort study following TRIPOD guidelines.
- **Derivation cohort**: Patients with decompensated cirrhosis and normal sCr admitted to the Mengchao Hepatobiliary Hospital of Fujian Medical University (Dec 2016–Dec 2022).
- **External validation**: Independent cohort from the Medical Information Mart for Intensive Care III (MIMIC-III) database.
- **Outcome**: Onset of AKI during hospitalization per International Club of Ascites (ICA) criteria.
- **Predictor selection**: Least absolute shrinkage and selection operator (LASSO) regression.
- **Model**: Multivariable logistic regression with a clinical nomogram.
- **Internal validation**: Enhanced bootstrap.
- **Performance**: Discrimination and calibration; AUROC used for discrimination.
- **Clinical utility**: Decision curve analysis (DCA).

### Repository Structure
- `Analysis_renal_updated.Rmd`: Primary analysis workflow (model building, validation, and figures).
- `mimic-code/`: Helper scripts/utilities for MIMIC-III data extraction/processing (see folder-level notes for usage and provenance).

### Data Sources and Access
- **Internal cohort**: Hospital admissions from Mengchao Hepatobiliary Hospital (2016–2022) with normal sCr at baseline.
- **External validation cohort**: MIMIC-III v1.4. Access requires credentialed approval and data use agreement. See the official project page: [`https://physionet.org/content/mimiciii/1.4/`](https://physionet.org/content/mimiciii/1.4/).

This repository does not include protected health information (PHI). Users must independently obtain access to MIMIC-III and prepare the validation dataset following institutional and PhysioNet credentialing requirements.

### Reproducibility
- **Prerequisites**:
  - R (≥ 4.1 recommended)
  - R packages used in the analysis (install as needed): `glmnet`, `rms`, `pROC`, `ggplot2`, `dplyr`, `tidyr`, `rmarkdown`, and dependencies.
- **Run the analysis**:
  - Open `Analysis_renal_updated.Rmd` in RStudio and Knit; or
  - From a terminal:
    - `Rscript -e "rmarkdown::render('Analysis_renal_updated.Rmd')"`

Outputs include AUROC, calibration plots, decision curves, and a nomogram to facilitate clinical interpretation.

### Results (at a glance)
- Discrimination quantified by AUROC in derivation and external validation cohorts.
- Calibration assessed via calibration plots and statistics.
- Clinical utility evaluated via DCA across a range of threshold probabilities.
- Nomogram provided to translate model predictions into bedside decision support.

### Reporting Guidelines
This work adheres to the TRIPOD guideline for prediction model development and validation.

### Ethics and Compliance
- Internal cohort approvals/waivers per institutional review board (IRB) policies.
- MIMIC-III contains de-identified data; usage complies with PhysioNet credentialing and data use agreements.

### How to Cite
If you use this repository or build upon this work, please cite:
- Johnson AEW, Pollard TJ, Shen L, et al. MIMIC-III, a freely accessible critical care database. Scientific Data. 2016.
- Shenglong Lin. Validation of an AKI prediction model in decompensated cirrhosis using MIMIC-III. GitHub repository: https://github.com/AlongLin/Renal_AKI.git.

### License
Specify a license for reuse. If unsure, consider MIT, Apache-2.0, or GPL-3.0. Until specified, all rights reserved.

### Contact
- Maintainer: Shenglong Lin
- Email: alonglin2008@live.cn
