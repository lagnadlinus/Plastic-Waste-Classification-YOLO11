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

2. Open WaDaBa_Plastic_Classification_YOLO.ipynb in Google Colab or your local Jupyter environment.
3. Run evaluation cells to inspect metrics, inference validation tables, and prediction states immediately

Option 2: Full Reproduction (Data Acquisition Required)

To retrain the networks from scratch, you must satisfy the official dataset tracking requirements:
1. Request Data: Obtain the formal archive credentials directly from the WaDaBa Database Home Portal.
2. Local Assembly: Compile and compress the target assets into an archive matching the signature 04_yolo_cls_dataset.zip.
3. Execute Pipeline: Toggle the internal flags inside the notebook to rebuild properties:

RETRAIN_MODE = True
AUTO_TRAIN_IF_MISSING = True

Congratulations on finishing your assignment and getting good marks! It is a fantastic project to showcase to potential employers, as it demonstrates end-to-end machine learning skills, handling real-world data issues (imbalance), and building an interactive prototype (Gradio/Hugging Face).
Navigating the WaDaBa terms of use while publishing your work on GitHub requires addressing a few critical constraints, along with a step-by-step guide to putting this together cleanly and professionally.
The Legal Verdict: Public vs. Private?
Yes, you can absolutely make your GitHub repository PUBLIC, but with one strict condition:
You MUST NOT upload the raw WaDaBa dataset images or the .zip archive to your GitHub repository. ### Why?
The WaDaBa License Agreement explicitly states: "The database will not be further distributed, published, copied, or further disseminated in any way or form whatsoever." If you upload the images or the compressed zip file to GitHub, you violate their terms. However, your code, trained weights (.pt files), Hugging Face Space, and README documentation are completely fine to be public, provided you give them proper academic credit.
Step-by-Step Instructions to Upload to GitHub
Follow these steps to safely and professionally move your project from Google Drive/Colab onto a public GitHub repository.
Step 1: Create a New GitHub Repository
Go to your GitHub profile and create a New Repository.
Name it something clean like Plastic-Waste-Classification-YOLO11.
Set the visibility to Public.
Check the box to Add a README file and select Python for the .gitignore template.
Step 2: Organize Your Local Project Folder
Download the necessary files from your Google Drive folder to your local computer. Arrange them like this:
Plaintext
Plastic-Waste-Classification-YOLO11/
├── .gitignore
├── README.md
├── WaDaBa_Plastic_Classification_YOLO.ipynb
├── yolo11n-cls.pt
├── yolo11s-cls.pt
└── runs/
    └── classify/
        ├── baseline_yolo11n_cls/weights/best.pt
        └── improved_yolo11s_cls/weights/best.pt
Step 3: Configure Your .gitignore File (Crucial)
Open the .gitignore file in a text editor. Add the following lines to the bottom to ensure you never accidentally push dataset files to GitHub if you download them locally later:
Plaintext
# Ignore raw data folders
04_yolo_cls_dataset/
*.zip
*.tar.gz
.DS_Store
Step 4: Update Your Jupyter Notebook (.ipynb)
Before pushing your notebook to GitHub, open it in Colab and do a quick cleanup for your future employers:
Change RETRAIN_MODE = False so that if someone opens it, they know it's a demonstration notebook.
Ensure your outputs (graphs, confusion matrices) are saved and visible within the notebook cells so recruiters can see your results without running the code.
Step 5: Push the Code to GitHub
You can upload the files directly through the GitHub website using the "Upload files" button, or use the terminal:
Bash
git clone <your-github-repo-url>
# Move your notebook and weights into the cloned folder
git add .
git commit -m "Initial commit: Plastic waste classification model and weights"
git push origin main
Crafting a Professional README
A great README is what makes potential employers notice your work. Since you cannot provide the dataset, you must explain how they can get it. Here is a template structured perfectly for your project:
Markdown
# Multi-Class Plastic Waste Classification using YOLO11

An end-to-end computer vision project implementing deep learning to sort multi-class plastic waste (PET, PE-HD, PP, PS, and Other) using the Ultralytics YOLO11 framework.

## 🚀 Live Demo
Try out the interactive prototype hosted on Hugging Face Spaces: 
[Plastic Waste Classification Demo](https://huggingface.co/spaces/lagnadlinus/plastic-waste-classification-yolo11)

## 📊 Performance Comparison
| Model | Epochs | Parameters | Top-1 Accuracy | Top-5 Accuracy |
|---|---:|---:|---:|---:|
| YOLO11n-cls Baseline | 10 | 1.53M | 99.1% | 100% |
| YOLO11s-cls Improved | 20 | 5.44M | 99.5% | 100% |

## ⚠️ Dataset Notice & Terms of Use
This project utilizes the **WaDaBa Plastic Waste Database of Images**. Due to the dataset's licensing terms, the raw image files **cannot be shared publicly** in this repository.

To replicate this experiment:
1. Request access to the dataset by filling out the official contract form from the [WaDaBa Homepage](https://wadaba.pcz.pl/#home).
2. Once approved, download and compress the images into `04_yolo_cls_dataset.zip`.
3. Follow the parsing logic inside the notebook to restructure the filenames (e.g., matching `a01` to `PET`).

## 🛠️ References & Citations
If you use this work or the underlying data, please cite the original authors:

* Bobulski J., Piatkowski J., *PET waste classification method and Plastic Waste DataBase WaDaBa*, Conference Proc. IP&C 2018, Advances in Intelligent Systems and Computing, vol. 681, Springer Verlag, 2018, pp.57-64.
* Bobulski J., Kubanek M., *Deep Learning for Plastic Waste Classification System*, Applied Computational Intelligence and Soft Computing, 2021, art. no. 6626948.
Can other people contribute to making it better?
Yes! By hosting your code publicly, other developers can duplicate your repository, request access to the WaDaBa dataset themselves, and try different architectures (like YOLO11m or ViTs) or implement data augmentation to solve the class imbalance problem you noted.
By detailing the dataset limitations (missing PVC and PE-LD classes) in your README, you invite open-source collaboration while respecting academic licensing rules flawlessly. Ready to push this live? Let me know if you need help adjusting the Hugging Face configuration files or organizing the repo further.
