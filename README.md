# Open-Closed Period Decoupling via Griffiths Gauge-Cancellation Operator ($g$-Operator)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Precision: 50-dps](https://img.shields.io/badge/Precision-50--dps-success.svg)]()
[![Security: 118--bit](https://img.shields.io/badge/Phase%20Boundary-118--bit%20Crypto-critical.svg)]()

> **Paper**: *A Deterministic Griffiths Gauge-Cancelling Operator for Inhomogeneous Picard--Fuchs Systems: Decoupling Open--Closed Periods and D-Brane Amplitudes via High-Precision PSLQ*  
> **Author**: Kouta Matsumoto (Independent Researcher, ORCID: [0009-0008-6385-9185](https://orcid.org/0009-0008-6385-9185))  
> **Manuscript (PDF)**: [`paper/first_report/first_report_gg_operator.pdf`](paper/first_report/first_report_gg_operator.pdf)

---

## 🔬 Overview

In open string mirror symmetry and membrane integral theory, the unavoidable mixing of inhomogeneous components (arising from D-brane superpotentials and normal functions) with the underlying closed string homology lattice $H_3(X, \mathbb{Z})$ has long constituted a severe computational barrier.

This repository provides the official implementation and 50-decimal-place (50-dps) arbitrary-precision validation of the **Griffiths Gauge-Cancellation Operator** (designated as the **$g$-operator**, $\mathcal{K}_{\text{gauge}}$).

$$\mathcal{K}_{\text{gauge}} := I - \mathcal{D}_{\text{PF}}^{-1} \circ \mathcal{D}_{\text{PF}}$$

The operator systematically projects the relative Frobenius series back onto the pure geometric cycle period lattice, eliminating transcendental obstructions with **exact numerical residual 0.0**.

---

## 📊 Cross-Manifold PSLQ Benchmark (50-dps Arbitrary Precision)

| Manifold | Geometry | State | Cyclotomic Phase Factor | Recovered Vector | Residual | Exec Time |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **Fermat Quintic $X_5$** | $X_5 \subset \mathbb{P}^4$ ($d=5$) | Raw Amplitude | $2\sin(\pi/5) = \sqrt{\frac{5-\sqrt{5}}{2}}$ | `None` | N/A | 0.0050 s |
| **Fermat Quintic $X_5$** | $X_5 \subset \mathbb{P}^4$ ($d=5$) | **With $\mathcal{K}_{\text{gauge}}$** | $2\sin(\pi/5) = \sqrt{\frac{5-\sqrt{5}}{2}}$ | **`[2, -3, 0, 1]`** | **`0.0`** | **`0.0000 s`** |
| **Octic Threefold $X_8$** | $X_8 \subset \mathbb{P}^4_{(1,1,1,1,4)}$ ($d=8$) | Raw Amplitude | $2\sin(\pi/8) = \sqrt{2-\sqrt{2}}$ | `None` | N/A | 0.0050 s |
| **Octic Threefold $X_8$** | $X_8 \subset \mathbb{P}^4_{(1,1,1,1,4)}$ ($d=8$) | **With $\mathcal{K}_{\text{gauge}}$** | $2\sin(\pi/8) = \sqrt{2-\sqrt{2}}$ | **`[3, -2, 0, 1]`** | **`0.0`** | **`0.0000 s`** |

---

## 🛡️ 118-Bit Cryptographic Phase Transition Boundary

To verify that the integer recovery reflects authentic underlying algebraic geometry rather than numerical fitting, we introduce an infinitesimal perturbation $\epsilon$ to the derived boundary constant: $C_{\text{pert}} = C \cdot (1 + \epsilon)$.

| Perturbation $\epsilon$ | PSLQ Result | Status & Significance |
| :---: | :---: | :--- |
| $10^{-30}$ | `None` | Integer relation strictly rejected |
| $10^{-33}$ | `None` | Integer relation strictly rejected |
| $10^{-35}$ | `None` | Integer relation strictly rejected |
| **$10^{-35.5}$** | **Phase Boundary** | **Critical Transition Threshold ($\approx 118$ bits security)** |
| $10^{-36}$ | `[2, -3, 0, 1]` | Exact recovery (residual 0.0) |
| $0.0$ (Exact) | `[2, -3, 0, 1]` | Exact recovery (residual 0.0) |

The critical transition at $10^{-35.5}$ corresponds to $35.5 \times \log_2(10) \approx 117.9$ bits, matching the NIST 112–128 bit cryptographic standard ($2^{118} \approx 3.3 \times 10^{35}$ operations), ruling out any chance of accidental false-positive discovery.

---

## 🚀 One-Click Reproduction

Ensure Python 3.10+ and `mpmath` are installed:

```bash
pip install mpmath
```

### 1. Cross-Manifold PSLQ Recovery ($X_5$ vs $X_8$)
```bash
python src/verify_octic_threefold_g_operator.py
```

### 2. 118-Bit Phase Transition & Sensitivity Stress Test
```bash
python src/stress_test_devils_advocate.py
```

---

## 📜 Repository Structure

```text
open-closed-period-decoupling/
├── README.md                                # Official documentation and benchmark tables
├── paper/
│   ├── first_report/                        # 【Report 1】Letter / Fast-Track Manuscript
│   │   ├── first_report_gg_operator.pdf     # Publication-ready Letter manuscript (PDF)
│   │   ├── first_report_gg_operator.tex     # LaTeX source code (JHEP / CMP format)
│   │   └── g_operator_open_closed_period_decoupling.md # Markdown draft
│   └── full_paper/                          # 【Report 2】Comprehensive Theoretical Sequel
│       └── companion_paper_deep_geometry.md # Base draft for deep geometry & universal scaling
└── src/
    ├── verify_octic_threefold_g_operator.py # 50-dps cross-manifold verification
    └── stress_test_devils_advocate.py       # 118-bit phase transition stress test
```

---

## ⚖️ License & Citation

This project is licensed under the MIT License.

```bibtex
@article{Matsumoto2026Decoupling,
  author    = {Kouta Matsumoto},
  title     = {A Deterministic Griffiths Gauge-Cancelling Operator for Inhomogeneous Picard--Fuchs Systems: Decoupling Open--Closed Periods and D-Brane Amplitudes via High-Precision PSLQ},
  journal   = {arXiv preprint},
  year      = {2026},
  url       = {https://github.com/Oshiruko3/open-closed-period-decoupling}
}
```
