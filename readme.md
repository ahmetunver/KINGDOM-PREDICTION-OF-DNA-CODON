<div align="center">

# 🧬 Kingdom Prediction of DNA Codon

**TR** | [EN ↓](#-kingdom-prediction-of-dna-codon--english)

[![Python](https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-ML-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/Lisans-MIT-green?style=flat-square)](LICENSE)


*DNA kodon frekanslarından biyolojik krallıkları tahmin eden makine öğrenimi sistemi*

</div>

---

## 🇹🇷 Türkçe

### 📌 Proje Hakkında

Bu proje, **DNA kodon kullanım frekanslarını** analiz ederek organizmaların biyolojik **Krallığını** (Kingdom) tahmin etmeye yönelik bir makine öğrenimi çalışmasıdır. Kodon tercihleri (codon usage bias), farklı biyolojik krallıklar arasında belirgin farklılıklar gösterdiğinden sınıflandırma için güçlü bir ayırt edici özellik olarak kullanılmaktadır.

> DNA'daki her üç nükleotidlik grup (kodon) bir amino asidi kodlar. Farklı organizmalar aynı amino asidi kodlamak için farklı kodon tercihlerine sahiptir — bu frekans örüntüleri, organizmanın hangi krallığa ait olduğuna dair biyolojik bir parmak izi niteliği taşır.

### 🎯 Amaç

`codon_usage.csv` veri seti üzerinde kapsamlı bir ön işleme, özellik mühendisliği ve model karşılaştırması pipeline'ı oluşturarak:

- En yüksek sınıflandırma doğruluğuna ulaşan algoritmayı belirlemek
- Farklı boyut indirgeme ve özellik seçimi tekniklerinin etkisini karşılaştırmak
- Ensemble yöntemlerinin tek modeller üzerindeki avantajını araştırmak

### 📁 Proje Yapısı

```
KINGDOM-PREDICTION-OF-DNA-CODON/
│
├── codon_usage.csv                         # Ham veri seti
│
├── 📂 Ön İşleme & Özellik Mühendisliği
│   ├── AhmetUnver_..._preprocess.ipynb             # Temel ön işleme pipeline'ı
│   └── AhmetUnver_..._preprocess_FE_PCA.ipynb      # PCA ile boyut indirgeme
│
├── 📂 Ahmet Ünver — Modeller
│   ├── AhmetUnver_..._BaggingClassifier.ipynb      # Bagging Sınıflandırıcı
│   ├── AhmetUnver_..._LightGBM.ipynb               # LightGBM
│   ├── AhmetUnver_PERCEPTRON-Algoritmasi.ipynb     # Perceptron
│   └── AhmetUnver_QDA-Algoritmasi.ipynb            # Quadratic Discriminant Analysis
│
├── 📂 Cansu Ece — Modeller
│   ├── CansuEce-FE_FS_LR (2).ipynb                 # Lojistik Regresyon (FS)
│   ├── CansuEce-FE_FS_SVM (1).ipynb                # SVM (Özellik Seçimi)
│   ├── CansuEce-FE_PCA_LR.ipynb                    # Lojistik Regresyon (PCA)
│   ├── CansuEce-FE_PCA_SVM (2).ipynb               # SVM (PCA)
│   ├── Cansu_Ece_..._VotingClassifier.ipynb        # Voting Sınıflandırıcı
│   └── Cansu_Ece_..._XGBoost.ipynb                 # XGBoost
│
├── 📂 Fidan Akyürek — Modeller
│   ├── Fidan_Akyürek_..._BAC-2F-GENOM(1).ipynb     # Temel model denemeleri
│   ├── Fidan_Akyürek_..._BAC-2F-GENOM(2).ipynb     # Gelişmiş denemeler
│   ├── Fidan_Akyürek_..._HistgradientBoosting.ipynb # Histogram Gradient Boosting
│   └── Fidan_Akyürek_..._Stacking_Classifier.ipynb  # Stacking Sınıflandırıcı
│
├── 📂 Funda Bozburun — Modeller
│   ├── FundaBozburun_Decision_Tree_Algorithm.ipynb  # Karar Ağacı
│   ├── FundaBozburun_Logistic_Regression.ipynb      # Lojistik Regresyon
│   ├── Funda_Bozburun_..._AdaBoost_.ipynb           # AdaBoost
│   └── Funda_Bozburun_..._GradientBoosting.ipynb    # Gradient Boosting
│
└── 📂 Sultan Buse Görçüm — Modeller
    ├── SultanBuseGörçüm_..._ExtraTreesAlgorithm.ipynb      # Extra Trees
    ├── SultanBuseGörçüm_..._KNNAlgorithm.ipynb             # K-En Yakın Komşu
    ├── Sultan_Buse_Gorcum_..._BaggingClassifier_withSVC.ipynb  # Bagging + SVC
    └── Sultan_Buse_Gorcum_..._RandomForestClassifier.ipynb     # Random Forest + GridSearch
```

### 🧪 Uygulanan Algoritmalar

| Kategori | Algoritmalar |
|---|---|
| **Temel Modeller** | Logistic Regression, Decision Tree, KNN, Perceptron, QDA |
| **Destek Vektör Makineleri** | SVM / SVC |
| **Ensemble — Bagging** | Random Forest, Extra Trees, Bagging Classifier (SVC ile) |
| **Ensemble — Boosting** | AdaBoost, Gradient Boosting, Histogram Gradient Boosting, XGBoost, LightGBM |
| **Ensemble — Stacking/Voting** | Stacking Classifier, Voting Classifier |

### 🔬 Uygulanan Teknikler

**Ön İşleme:**
- Eksik veri analizi ve temizliği
- Hedef değişken (Kingdom) encoding
- Özellik normalizasyonu / standardizasyonu

**Özellik Mühendisliği & Seçimi:**
- PCA (Principal Component Analysis) — boyut indirgeme
- Feature Selection (FS) — önem tabanlı özellik seçimi
- Feature Engineering (FE) — yeni özellik türetme

**Model Değerlendirme:**
- Accuracy, Precision, Recall, F1-Score
- Confusion Matrix
- Cross-Validation
- GridSearchCV ile hiperparametre optimizasyonu

### 📊 Veri Seti

| Özellik | Detay |
|---|---|
| Dosya | `codon_usage.csv` |
| Kaynak | NCBI Codon Usage Database |
| Özellikler | 64 kodon frekansı + meta bilgiler |
| Hedef | Biyolojik Kingdom (Archaea, Bacteria, Eukaryota, Virüs vb.) |

### 🚀 Kurulum & Çalıştırma

```bash
# Repoyu klonlayın
git clone https://github.com/ahmetunver/KINGDOM-PREDICTION-OF-DNA-CODON.git
cd KINGDOM-PREDICTION-OF-DNA-CODON

# Gerekli kütüphaneleri yükleyin
pip install pandas numpy scikit-learn matplotlib seaborn xgboost lightgbm jupyter

# Jupyter Notebook'u başlatın
jupyter notebook
```

> Notebook'ları `preprocess` adımıyla başlatmanız önerilir, ardından ilgilendiğiniz model notebook'unu açabilirsiniz.



### 🛠️ Gereksinimler

```
Python >= 3.8
pandas
numpy
scikit-learn
xgboost
lightgbm
matplotlib
seaborn
jupyter
```

---

## 🇬🇧 Kingdom Prediction of DNA Codon — English

<div align="center">

*A machine learning system predicting biological kingdoms from DNA codon usage frequencies*

</div>

### 📌 About the Project

This project aims to predict the biological **Kingdom** of organisms by analyzing **DNA codon usage frequencies**. Since codon usage bias differs significantly across biological kingdoms, these frequency patterns serve as a powerful discriminative feature for classification.

> Every group of three nucleotides in DNA (a codon) encodes an amino acid. Different organisms prefer different codons for the same amino acid — these frequency patterns act as a biological fingerprint revealing which kingdom an organism belongs to.

### 🎯 Objective

Building a comprehensive preprocessing, feature engineering and model comparison pipeline on the `codon_usage.csv` dataset to:

- Identify the algorithm achieving the highest classification accuracy
- Compare the impact of different dimensionality reduction and feature selection techniques
- Investigate the advantage of ensemble methods over single models

### 📁 Project Structure

```
KINGDOM-PREDICTION-OF-DNA-CODON/
│
├── codon_usage.csv                         # Raw dataset
│
├── 📂 Preprocessing & Feature Engineering
│   ├── AhmetUnver_..._preprocess.ipynb             # Core preprocessing pipeline
│   └── AhmetUnver_..._preprocess_FE_PCA.ipynb      # Dimensionality reduction with PCA
│
├── 📂 Ahmet Ünver — Models
│   ├── AhmetUnver_..._BaggingClassifier.ipynb      # Bagging Classifier
│   ├── AhmetUnver_..._LightGBM.ipynb               # LightGBM
│   ├── AhmetUnver_PERCEPTRON-Algoritmasi.ipynb     # Perceptron
│   └── AhmetUnver_QDA-Algoritmasi.ipynb            # Quadratic Discriminant Analysis
│
├── 📂 Cansu Ece — Models
│   ├── CansuEce-FE_FS_LR (2).ipynb                 # Logistic Regression (FS)
│   ├── CansuEce-FE_FS_SVM (1).ipynb                # SVM (Feature Selection)
│   ├── CansuEce-FE_PCA_LR.ipynb                    # Logistic Regression (PCA)
│   ├── CansuEce-FE_PCA_SVM (2).ipynb               # SVM (PCA)
│   ├── Cansu_Ece_..._VotingClassifier.ipynb        # Voting Classifier
│   └── Cansu_Ece_..._XGBoost.ipynb                 # XGBoost
│
├── 📂 Fidan Akyürek — Models
│   ├── Fidan_Akyürek_..._BAC-2F-GENOM(1).ipynb     # Initial model experiments
│   ├── Fidan_Akyürek_..._BAC-2F-GENOM(2).ipynb     # Advanced experiments
│   ├── Fidan_Akyürek_..._HistgradientBoosting.ipynb # Histogram Gradient Boosting
│   └── Fidan_Akyürek_..._Stacking_Classifier.ipynb  # Stacking Classifier
│
├── 📂 Funda Bozburun — Models
│   ├── FundaBozburun_Decision_Tree_Algorithm.ipynb  # Decision Tree
│   ├── FundaBozburun_Logistic_Regression.ipynb      # Logistic Regression
│   ├── Funda_Bozburun_..._AdaBoost_.ipynb           # AdaBoost
│   └── Funda_Bozburun_..._GradientBoosting.ipynb    # Gradient Boosting
│
└── 📂 Sultan Buse Görçüm — Models
    ├── SultanBuseGörçüm_..._ExtraTreesAlgorithm.ipynb      # Extra Trees
    ├── SultanBuseGörçüm_..._KNNAlgorithm.ipynb             # K-Nearest Neighbors
    ├── Sultan_Buse_Gorcum_..._BaggingClassifier_withSVC.ipynb  # Bagging + SVC
    └── Sultan_Buse_Gorcum_..._RandomForestClassifier.ipynb     # Random Forest + GridSearch
```

### 🧪 Algorithms Applied

| Category | Algorithms |
|---|---|
| **Base Models** | Logistic Regression, Decision Tree, KNN, Perceptron, QDA |
| **Support Vector Machines** | SVM / SVC |
| **Ensemble — Bagging** | Random Forest, Extra Trees, Bagging Classifier (with SVC) |
| **Ensemble — Boosting** | AdaBoost, Gradient Boosting, Histogram Gradient Boosting, XGBoost, LightGBM |
| **Ensemble — Stacking/Voting** | Stacking Classifier, Voting Classifier |

### 🔬 Techniques Applied

**Preprocessing:**
- Missing value analysis and imputation
- Target variable (Kingdom) encoding
- Feature normalization / standardization

**Feature Engineering & Selection:**
- PCA (Principal Component Analysis) — dimensionality reduction
- Feature Selection (FS) — importance-based feature selection
- Feature Engineering (FE) — deriving new features

**Model Evaluation:**
- Accuracy, Precision, Recall, F1-Score
- Confusion Matrix
- Cross-Validation
- Hyperparameter optimization via GridSearchCV

### 📊 Dataset

| Property | Details |
|---|---|
| File | `codon_usage.csv` |
| Source | NCBI Codon Usage Database |
| Features | 64 codon frequencies + metadata |
| Target | Biological Kingdom (Archaea, Bacteria, Eukaryota, Virus, etc.) |

### 🚀 Setup & Usage

```bash
# Clone the repository
git clone https://github.com/ahmetunver/KINGDOM-PREDICTION-OF-DNA-CODON.git
cd KINGDOM-PREDICTION-OF-DNA-CODON

# Install required libraries
pip install pandas numpy scikit-learn matplotlib seaborn xgboost lightgbm jupyter

# Launch Jupyter Notebook
jupyter notebook
```

> It is recommended to start with the `preprocess` notebook, then open any model notebook of interest.



### 🛠️ Requirements

```
Python >= 3.8
pandas
numpy
scikit-learn
xgboost
lightgbm
matplotlib
seaborn
jupyter
```

---

<div align="center">

© 2024 — BAC-2F GENOM Grup Projesi

*Bioinformatics × Machine Learning*

🧬 DNA → Kodon Frekansları → Kingdom Tahmini 🔬

</div>
