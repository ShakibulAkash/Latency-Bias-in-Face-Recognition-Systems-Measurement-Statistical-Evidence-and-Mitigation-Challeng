# Latency Bias in Face Recognition Systems
### Measurement, Statistical Evidence, and Mitigation Challenges for Eyeglass Wearers

This repository provides a **reproducible, deployment-oriented evaluation framework**
for analyzing **latency-based fairness** in real-time face recognition systems.
Unlike prior fairness studies that focus on predictive accuracy, this work shows
that **fairness violations emerge primarily in tail inference latency**, even when
mean latency remains statistically identical across groups.

The repository accompanies the research paper and contains all experimental
pipelines used for measurement, statistical validation, and mitigation analysis.

---

## 🔍 Problem Statement

Fairness analysis in face recognition systems has historically focused on **accuracy
disparities** across demographic groups. However, real-world deployments are
often constrained by **latency requirements**, where worst-case inference delays
(p95–p99) dominate user experience and system reliability.

This work investigates **latency bias** as a previously overlooked dimension of
algorithmic fairness. We show that:
- Mean inference latency can appear fair
- Severe **tail latency disparities** exist between subgroups
- These disparities are **invisible to average-based evaluation**

Eyeglass wearers are studied as a visually complex subgroup under **label-free,
realistic deployment constraints**.

---

## 🧪 Methodology Overview

The evaluation pipeline consists of:

1. **Label-Free Attribute Inference**
   - Eyeglasses inferred using a pretrained attribute classifier
   - Confidence filtering to ensure Responsible-AI compliance

2. **Balanced Cohort Construction**
   - Equal-sized eyeglasses vs. no-eyeglasses cohorts

3. **Latency Measurement**
   - End-to-end inference timing
   - Warmed system and repeated runs
   - Mean, median, p95, and p99 latency reporting

4. **Statistical Validation**
   - Non-parametric permutation testing
   - Bootstrap confidence intervals
   - Effect size analysis (Cohen’s d, Cliff’s δ)

5. **System-Level Attribution**
   - Multivariate regression controlling for:
     - Detection confidence
     - Number of detected faces
     - Visual complexity proxies

6. **Mitigation & Trade-off Analysis**
   - Reduced-resolution inference
   - Dynamic fallback strategies
   - Latency vs. fairness vs. fidelity evaluation

---

## 📊 Key Findings

- **Mean latency differences are statistically insignificant**
- **p99 latency differs by up to ~17 ms** between cohorts
- Fairness violations occur **only in the extreme tail**
- Latency disparities are **mediated by system-level factors**, not direct attribute causality
- Tail-latency mitigation introduces **non-trivial trade-offs** with recognition fidelity

---

## 📁 Repository Contents

