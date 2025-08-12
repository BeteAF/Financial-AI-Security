## Overview

This directory focuses on Adversarial Machine Learning Attacks against tabular data credit scoring models. 
It contains 10 evasion attack notebooks: 7 white-box (FGM, BIM, PGD, C&W, EAD, JSMA, DeepFool) and 3 black-box (ZOO, HSJ, Boundary Attack) along with planned work on Model Extraction, Inference, and Poisoning attacks.

The primary goals are to:
- Demonstrate practical implementations of adversarial attacks on financial AI systems.
- Analyze vulnerabilities under white-box, black-box, and gray-box threat models.
- Lay the foundation for robust defenses against evasion, extraction, inference, and poisoning threats.

---

## Current Contents

### 1. Evasion Attacks on Credit Scoring Models (Tabular Data)
**White-box Attacks**
- Fast Gradient Method (FGM) (https://arxiv.org/abs/1412.6572)
- Basic Iterative Method (BIM) (https://arxiv.org/abs/1607.02533)
- Projected Gradient Descent (PGD) (https://arxiv.org/abs/1706.06083)
- Carlini & Wagner (C&W) (https://arxiv.org/abs/1608.04644)
- ElasticNet Attack (EAD) (https://arxiv.org/abs/1709.04114)
- Jacobian-based Saliency Map Attack (JSMA) (https://arxiv.org/abs/1511.07528)
- DeepFool (https://arxiv.org/abs/1511.04599)

**Black-box Attacks**
- Zeroth Order Optimization (ZOO) (https://arxiv.org/abs/1708.03999)
- HopSkipJump (HSJ) (https://arxiv.org/abs/1904.02144)
- Boundary Attack (https://arxiv.org/abs/1712.04248)

All attacks implemented using:
- **[Adversarial Robustness Toolbox (ART)](https://github.com/Trusted-AI/adversarial-robustness-toolbox)**
- **[Foolbox](https://github.com/bethgelab/foolbox)** (planned for cross-framework comparison)

Dataset: **German Credit Dataset** (tabular classification task)

---

## Future Roadmap

### Offensive Security
- **Model Extraction Attacks**
  - API-based extraction
  - Query-based imitation
- **Inference Attacks**
  - Membership inference
  - Attribute inference
- **Poisoning Attacks**
  - Data poisoning
  - Backdoor insertion

### Defensive Security
- **Robust Training**
  - Adversarial training
  - Defensive distillation
- **Input Filtering**
  - Outlier detection
  - Adversarial example detection
- **API Red Teaming**
  - Simulated malicious API consumers
  - Throttling and query monitoring

---

## Project Structure

 - credit_scoring/
   - models/
     - credit_scoring_model_german_dataset---logistic_regression.ipynb
     - credit_scoring_model_german_dataset---random_forest.ipynb
     - credit_scoring_model_german_dataset---xgboost.ipynb
     - saved_models/
       - logistic_regression.joblib
       - random_forest.joblib
       - xgboost.joblib
   - attacks/
     - evasion/
       - white_box/
         - art/
           - fgm_attack-art-logistic_regression.ipynb
           - bim_attack-art-logistic_regression.ipynb
           - pgd_attack-art-logistic_regression.ipynb
           - cw_attack-art-logistic_regression.ipynb
           - ead_attack-art-logistic_regression.ipynb
           - jsma_attack-art-logistic_regression.ipynb
           - deepfool_attack-art-logistic_regression.ipynb
         - foolbox/
           - fgm_attack-foolbox-logistic_regression.ipynb
           - bim_attack-foolbox-logistic_regression.ipynb
           - pgd_attack-foolbox-logistic_regression.ipynb
           - cw_attack-foolbox-logistic_regression.ipynb
           - ead_attack-foolbox-logistic_regression.ipynb
           - jsma_attack-foolbox-logistic_regression.ipynb
           - deepfool_attack-foolbox-logistic_regression.ipynb
         - README.md
       - black_box/
         - art/
           - zoo_attack-art-logistic_regression.ipynb
           - hsj_attack-art-logistic_regression.ipynb
           - boundary_attack-art-logistic_regression.ipynb
         - foolbox/
           - zoo_attack-foolbox-logistic_regression.ipynb
           - hsj_attack-foolbox-logistic_regression.ipynb
           - boundary_attack-foolbox-logistic_regression.ipynb
         - README.md
     - extraction/
       - art/
       - foolbox/
       - README.md
     - inference/
       - art/
       - foolbox/
       - README.md
     - poisoning/
       - art/
       - foolbox/
       - README.md
   - defenses/
     - art/
       - adversarial_training_art.ipynb
       - input_filters_art.ipynb
     - foolbox/
       - adversarial_training_foolbox.ipynb
       - input_filters_foolbox.ipynb
     - README.md
   - offensive_tests/
     - membership_inference_api_red_team.ipynb
     - README.md
 - README
