# Risk-Controlled Selective Prediction for Diabetic Retinopathy Screening

This repository contains the research implementation and experimental notebooks associated with our study, **"Risk-Controlled Selective Prediction with Retinal Foundation Models for Referable Diabetic Retinopathy Screening Under Distribution Shift."**

The research investigates the reliability of automatic non-referral decisions in diabetic retinopathy (DR) screening using retinal foundation models, probability calibration, and statistically controlled threshold selection.

The framework is developed and evaluated on APTOS 2019, followed by external evaluation on IDRiD and Messidor-2 to investigate whether source-certified screening policies maintain their reliability under distribution shift.

The study also explores lesion-morphology-based screening approaches, including Grade-Boundary Lesion Screening (GBLS) and Shift-Robust Grade-Boundary Lesion Screening (SR-GBLS).

## Repository Structure

The repository contains eight Jupyter notebooks covering model development, external validation, statistical risk control, lesion-based screening, and experimental analysis.

| Notebook | Research component |
|---|---|
| `01_DR_APTOS_RETOUND.ipynb` | RETFound-Green development and evaluation on APTOS 2019 |
| `02_DR_APTOS_MedSigLIP.ipynb` | MedSigLIP-based feature extraction and screening experiments |
| `03_External_Validation.ipynb` | External evaluation using IDRiD and Messidor-2 |
| `04_DR_APTOS_DINOv2_Large.ipynb` | DINOv2-Large-based screening experiments |
| `05_DR_GBLS_SR_GBLS.ipynb` | Lesion-morphology screening using GBLS and SR-GBLS |
| `06_External_Failure_Analysis.ipynb` | External screening errors, grade-specific analysis, and risk–coverage evaluation |
| `07_Result_&_Analysis.ipynb` | Experimental results and comparative performance analysis |
| `DR_Major_Revision.ipynb` | Additional research experiments and updated results analysis |

## Research Objectives

The study focuses on three principal objectives:

1. **Risk-controlled screening:** Investigate automatic non-referral policies using calibrated retinal foundation-model predictions and Learn-Then-Test (LTT) certification.
2. **Reliability under distribution shift:** Evaluate how source-selected screening thresholds perform when transferred unchanged to independent retinal datasets.
3. **Lesion-informed screening:** Investigate whether retinal lesion-morphology features improve discrimination around the boundary between non-referable and referable DR.

## Datasets

Three retinal fundus image datasets are used in the study.

| Dataset | Retained images | Research purpose |
|---|---:|---|
| APTOS 2019 | 3,504 | Model development, probability calibration, risk calibration, and internal evaluation |
| IDRiD | 507 | Independent external evaluation |
| Messidor-2 | 1,740 | Independent external evaluation |

The retained image counts reflect dataset integrity screening, including SHA-256-based detection of exact duplicates and conflicting labels.

DR severity grades are grouped into two screening categories:

- **Non-referable DR:** Grades 0–1
- **Referable DR:** Grades 2–4

This operational definition is based on DR severity grades and does not independently incorporate diabetic macular edema as an additional referral criterion.

### Dataset Sources

- **APTOS 2019:** https://www.kaggle.com/competitions/aptos2019-blindness-detection
- **IDRiD:** https://ieee-dataport.org/open-access/indian-diabetic-retinopathy-image-dataset-idrid
- **Messidor-2:** https://www.adcis.net/en/third-party/messidor2/
- **RETFound benchmark resource:** https://github.com/rmaphoh/RETFound/blob/main/BENCHMARK.md

The Messidor-2 severity labels used in the research originate from a processed benchmark resource rather than the original official Messidor-2 release.

## Methodology

The experimental framework includes:

1. **Foundation-model feature extraction:** Frozen RETFound-Green, DINOv2-Large, and MedSigLIP encoders.
2. **Classification and probability calibration:** Lightweight binary classification heads followed by temperature scaling.
3. **Risk-controlled threshold selection:** Fixed-sequence Learn-Then-Test certification for automatic non-referral.
4. **External evaluation:** Source-trained models and source-selected screening policies transferred without target-specific recalibration.
5. **Lesion-informed screening:** Morphology-based GBLS and SR-GBLS investigations.
6. **Comparative analysis:** Classification performance, probability calibration, risk–coverage behavior, and alternative threshold-selection methods.
7. **Failure analysis:** Grade-specific false clearances and retrospective matched-coverage comparisons.


The primary screening endpoint is conditional automatic non-referral risk:

$$
R(t) = P\left(Y = 1 \mid A_t(X) = 1\right)
$$

where $Y = 1$ denotes referable DR and $A_t(X) = 1$ denotes automatic clearance at threshold $t$.

The corresponding coverage measures the proportion of images selected for automatic clearance.


## Key Findings

At the predefined **5% conditional-risk target**, the RETFound-Green screening framework obtained certified source-domain thresholds across all five APTOS experimental repetitions.

On held-out APTOS test images:

- **Mean automatic-clearance coverage:** 51.06%
- **Mean observed conditional risk:** 0.37%
- **Mean AUROC:** 0.9800

When the same screening policies were applied without recalibration to external datasets:

| Dataset | Mean auto-clear coverage | Mean observed risk |
|---|---:|---:|
| APTOS 2019 | 51.06% | 0.37% |
| IDRiD | 33.61% | 14.73% |
| Messidor-2 | 78.74% | 14.66% |

Both external cohorts exhibited observed risks above the predefined 5% target.

Additional investigations examined alternative retinal foundation models, threshold-selection methods, lesion-derived screening features, and grade-specific errors.

The results highlight that **strong classification performance and source-domain statistical certification do not necessarily guarantee reliable automatic non-referral decisions under distribution shift**.

## Reproducibility

The research experiments were implemented in Python using PyTorch and supporting scientific computing and machine-learning libraries.

The notebooks document the principal experimental stages, including feature extraction, classification, calibration, risk-based threshold selection, external evaluation, and comparative analysis.

Reproducing the experiments requires:

- Access to the relevant retinal image datasets and their corresponding labels.
- Appropriate pretrained foundation-model checkpoints.
- Compatible Python and machine-learning dependencies.
- Configuration of dataset directories, model paths, and execution environments.

The notebooks are provided as research implementations. Dataset files and pretrained checkpoints must be obtained from their respective sources as applicable.

## Research Authors

**Safayet Ullah**  
**Md. Jubayer Islam**  
**Tanvirul Hoque Faysal**

Department of Computer Science and Engineering  
Southeast University, Dhaka, Bangladesh

**Research Supervisor:** Prof. Dr. Abdul Kadar Muhammad Masum

---

**Research scope:** This repository documents retrospective computational research and experimental evaluation. The screening policies investigated here are not established as clinically validated autonomous screening systems.
