# ♻️ Automated Multi-Class Plastic Waste Classification System

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](https://www.python.org/)
[![Ultralytics YOLO](https://img.shields.io/badge/YOLO11-Ultralytics-orange.svg)](https://docs.ultralytics.com/)
[![Hugging Face Spaces](https://img.shields.io/badge/%F0%9F%A4%97%20Hugging%20Face-Spaces-yellow.svg)](https://huggingface.co/spaces/lagnadlinus/plastic-waste-classification-yolo11)
[![Academic License](https://img.shields.io/badge/License-WaDaBa%20Research-red.svg)](https://wadaba.pcz.pl/#home)

An end-to-end computer vision pipeline developed using the **Ultralytics YOLO11** framework to address multi-class plastic waste sorting. While standard models stop at binary identification (plastic vs. non-plastic), this system classifies unique polymer types to match automated municipal sorting requirements on industrial conveyor systems.

## 🚀 Live Interactive Demo
Test the production model directly via the Hugging Face Space app interface:
👉 **[Plastic Waste Classification Web Application](https://huggingface.co/spaces/lagnadlinus/plastic-waste-classification-yolo11)**

---

## 📊 Core Objectives & Workflow
1. **Filename Preprocessing Pipeline:** Engineered a standalone parsing script to extract encrypted multi-variable properties (plastic type, degradation level, lighting) directly from unstructured raw string metadata.
2. **Class Isolation & Distribution Tuning:** Structured the image database into ML-ready categorical distributions while handling class absence constraints (PVC, PE-LD).
3. **Architecture Scaling:** Evaluated a lightweight standard baseline (`YOLO11n-cls`) against an optimized higher-capacity alternative (`YOLO11s-cls`).
4. **Edge Deployment:** Deployed a complete operational prototype running an integrated Gradio interface tailored for simulated facility testing.

---

## 🛠️ Project Setup & Execution

### Option 1: Quick Evaluation (Saved Model Mode)
By default, the notebook is configured with `RETRAIN_MODE = False` to bypass full training loops and load pre-computed state evaluations immediately.

1. Clone this repository onto your machine:
   ```bash
   git clone [https://github.com/lagnadlinus/Plastic-Waste-Classification-YOLO11.git](https://github.com/lagnadlinus/Plastic-Waste-Classification-YOLO11.git)
   cd Plastic-Waste-Classification-YOLO11

2. Open `WaDaBa_Plastic_Classification_YOLO.ipynb` in Google Colab or your local Jupyter environment.
3. Run evaluation cells to inspect metrics, inference validation tables, and prediction states immediately.

### Option 2: Full Reproduction (Data Acquisition Required)

To retrain the networks from scratch, you must satisfy the official dataset tracking requirements:

1. **Request Data:** Obtain the formal archive credentials directly from the [WaDaBa Database Home Portal](https://wadaba.pcz.pl/#home).
2. **Local Assembly:** Compile and compress the target assets into an archive matching the signature `04_yolo_cls_dataset.zip`.
3. **Execute Pipeline:** Toggle the internal flags inside the notebook to rebuild properties:
```python
RETRAIN_MODE = True
AUTO_TRAIN_IF_MISSING = True

```



---

## ⚙️ Tech Stack & System Architecture

### Core Components

* **Framework Layer:** Python 3.10 executed inside an accelerated Google Colab T4 GPU environment.
* **Model Layer:** Ultralytics YOLO11 Classifier (Nano & Small target variations).
* **Interface Layer:** Gradio Engine serving a local browser-ready web application UI.
* **Production Deployment:** Hugging Face Spaces public application hosting hub.

### Functional Processing Pipeline

```text
[1. Raw WaDaBa Archive]
   └── Extracts encrypted property strings into structured attributes.

[2. Custom Preprocessing Pipeline]
   └── Parses: Material ID (Plastic Type), Deformation Level, and Light Type.

[3. Structured Data Partitioning]
   └── Formats assets into balanced ML-ready split directories (70% Train / 20% Val / 10% Test).

[4. Deep Learning Scaling Evaluator]
   ├── Baseline Network   --> YOLO11n-cls (10 Epochs) --> 99.1% Top-1 Accuracy
   └── Production Network --> YOLO11s-cls (20 Epochs) --> 99.5% Top-1 Accuracy

[5. Cloud Edge Implementation]
   └── Packs network weights into an active web interface deployed on Hugging Face Spaces.

```

---

## 📈 Performance Engineering Matrix

The system tracks target performance across variations in network scale. Extended convergence metrics validate stability across execution lifetimes:

| Evaluation Architecture | Training Lifespan | Total Feature Weights | Top-1 Accuracy | Top-5 Accuracy | Target Cross-Entropy Loss |
| --- | --- | --- | --- | --- | --- |
| **YOLO11n-cls Baseline** | 10 Epochs | 1.53M | 99.1% | 100.0% | 0.1404 |
| **YOLO11s-cls Production** | 20 Epochs | 5.44M | **99.5%** | **100.0%** | **0.0912** |

> 📌 **Engineering Insight:** While scaling to the production model outputs a +0.4% boost in structural accuracy, its primary value is a massive reduction in model loss. The expanded parameter threshold isolates deep morphological traits, securely resolving variances caused by highly crumpled or deformed target inputs.

---

## ⚠️ Real-World Limitations & Open-Source Collaboration

Hosting this pipeline publicly serves as a blueprint for production-grade municipal separation platforms. During testing, explicit deployment boundaries were identified:

* **Class Imbalance Realities:** The base collection features heavy categorical bias toward `PET` elements, matching expected consumer refuse ratios but challenging rare-class recognition.
* **Absence Constraints:** Complete structural real-world images for `PVC` and `PE-LD` were unavailable in the base release, forcing the network to resolve those types via nearest known target parameters.
* **Future Scaling Paths:** Community contributions are welcome! Developers accessing authorized data layers can submit Pull Requests introducing Synthetic Data Augmentation (GAN/Diffusion generation) or alternate Vision Transformer (`ViT`) backbones to improve minority class identification profiles.

---

## 📜 Academic Attributions & References

This implementation builds upon the foundational research established by the Czestochowa University of Technology. If adapting this framework, please cite the core literature sources below:

* **Data Registry Source:** *Bobulski J., Piatkowski J., PET waste classification method and Plastic Waste DataBase WaDaBa, Conference Proc. IP&C 2018, Advances in Intelligent Systems and Computing, vol. 681, Springer Verlag, 2018, pp.57-64.*
* **Deep Learning Methodology:** *Bobulski J., Kubanek M., Deep Learning for Plastic Waste Classification System, Applied Computational Intelligence and Soft Computing, 2021, art. no. 6626948 DOI: 10.1155/2021/6626948.*

```

```
