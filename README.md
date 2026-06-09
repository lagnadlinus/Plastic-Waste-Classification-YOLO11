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
