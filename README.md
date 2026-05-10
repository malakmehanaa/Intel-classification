# Image Classification — Intel Scene Recognition
## Project overview

This project builds an end-to-end image classification pipeline on the Intel Image Classification dataset from Kaggle. It classifies natural scene images into 6 categories: `buildings`, `forest`, `glacier`, `mountain`, `sea`, `street`.

Two models are trained and compared:
- A CNN built entirely from scratch
- A Transfer Learning model using MobileNetV2 as backbone
  
## Dataset

- **Source:** [Intel Image Classification on Kaggle](https://www.kaggle.com/datasets/puneet6060/intel-image-classification)
- **Size:** ~25,000 images across 6 classes
- **Format:** Raw `.jpg` files organized in class folders

## Project structure

```
/
├── data_split/           
│   ├── train/
│   ├── val/
│   └── test/
├── models/                  
│   ├── scratch_best.keras
│   └── transfer_best.keras
├── results/                
│   ├── class_distribution.png
│   ├── sample_images.png
│   ├── augmentation.png
│   ├── scratch_curves.png
│   ├── scratch_confusion_matrix.png
│   ├── transfer_curves.png
│   ├── transfer_confusion_matrix.png
│   └── roc_curves.png
├── EDA_and_Preprocessing.ipynb
├── CNN_from_Scratch.ipynb
├── Transfer_and_Evaluation.ipynb
├── requirements.txt
└── README.md
```

## How to run

> Run the notebooks in order. Each notebook depends on outputs from the previous one.

### Step 1 — EDA and Preprocessing
- Splits the dataset into 70% train / 15% val / 15% test
- Checks for corrupted images
- Visualizes class distribution and augmentation examples
- Output: `data_split/` folder with all images organized

### Step 2 — CNN from Scratch
- Builds and trains a full CNN architecture from scratch
- Plots training curves (accuracy & loss)
- Evaluates on test set: classification report + confusion matrix heatmap
- Saves model to `models/scratch_best.keras`
- Saves predictions and metrics to `results/` for comparison

### Step 3 — Transfer Learning and Final Evaluation
- Builds a MobileNetV2-based transfer learning model manually
- Two-phase training: head-only first, then fine-tuning last 30 layers
- Full evaluation: classification report + confusion matrix
- Side-by-side comparison table of both models
- ROC/AUC curves for both models

## Team
- Malak Mohamed Salah - 230102892
- Sama Seraj - 240103344
- Mohamed Nasser - 230102231
