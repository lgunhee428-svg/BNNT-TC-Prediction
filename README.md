# BNNT-TC-Prediction
ML prediction of thermal conductivity in BNNT/Polymer composites

## Overview

Machine learning prediction of thermal conductivity (TC) in BN-based
polymer composites, based on experimental data collected from 9 literature
sources (2019–2025).

# 재현 논문 
This project reproduces and extends the methodology from
"LIU, Yinzhou, et al. Application of machine learning in predicting the thermal conductivity of single-filler polymer composites. Materials Today Communications, 2024, 39: 109116."
adding SHAP-based interpretability analysis not present in the original paper.

## Results

# 성능 비교 테이블 
| Model             | R²        | RMSE (W/mK) | Pearson R  |
|-------------------|-----------|-------------|------------|
| **GBDT**          | **0.981**  | 0.250       | **0.998**  |
| Random Forest     | 0.971     | 0.304       | 0.998      |
| XGBoost           | 0.965     | 0.331       | 0.996      |
| *논문 목표 (IJHMT)* | *0.981*  | —           | *0.981*    |

# Parity plot 이미지 
![Parity Plot](results/parity_plot.png)

# SHAP 피처 중요도 
![Feature Importance](results/feature_importance.png)

# 한 줄 해석 
> GBDT achieved R²=0.981, matching the paper's target.
> Filler loading and aspect ratio were the top predictors (SHAP).

## Dataset

# 규모 
- **39** experimental data points from **9** literature sources (2019–2025)
- **15** input features: filler loading, matrix type, aspect ratio,
  surface treatment, processing temperature, orientation, and more
- TC range: **0.19 – 11.9 W/mK** (63× span)
- Additional structural features from **Materials Project API**
  (Debye temperature, bulk modulus)

# 출처 논문 나열
**Sources:** YAN 2022, PORNEA 2023, HUYNH 2024, JIONG 2025,
SINGH 2019, WPU 2025, WuXN, WU 2018, LIM 2024

## Setup

# 1. 클론
```bash
git clone https://github.com/lgunhee428-svg/BNNT-TC-Prediction.git
cd BN-TC-Prediction
```

# 2. 패키지 설치
```bash
pip install -r requirements.txt
```

# 3. 노트북 실행
```bash
jupyter notebook notebooks/03_ML_models.ipynb
```

# 또는 Colab에서 바로 실행 (설치 불필요)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](Colab링크)
