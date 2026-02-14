# 🌸 Flower Species Classification Using DenseNet201

This project implements a **deep learning–based image classification system** for identifying flower species using the **Oxford 102 Flower Dataset** and a **DenseNet201 transfer learning architecture**.

The model achieves high accuracy by leveraging pretrained ImageNet weights and fine-tuning on the flower dataset.

---

## 📁 Dataset

The dataset used is the **Oxford 102 Flower Dataset**, containing:

* **8,189 images**
* **102 flower categories**
* High variation in scale, lighting, and background

### Dataset Files

* `102flowers.tgz` → Raw images
* `imagelabels.mat` → Image label mappings

---

## ⚙️ Project Workflow

### 1️⃣ Download & Extract Dataset

Download the dataset files and extract them into the project directory.

---

### 2️⃣ Label Organization – `sorted.py`

The script:

* Reads `imagelabels.mat`
* Assigns correct label to each image
* Creates 102 folders automatically:

```
label_1/
label_2/
...
label_102/
```

---

### 3️⃣ Train/Validation Split – `split.py`

Splits dataset into training and validation sets.

```
dataset/
├── train/
│   ├── label_1/
│   ├── ...
└── val/
    ├── label_1/
    ├── ...
```

Prevents data leakage and ensures proper evaluation.

---

### 4️⃣ Model Training – `DenseNet201.ipynb`

The notebook performs:

* Data preprocessing & augmentation
* Transfer learning using **DenseNet201**
* Classifier fine-tuning
* Training & validation evaluation
* Saving trained weights (`model.pth`)

---

## 📊 Evaluation Results

Training: **5 epochs**

| Metric    | Value   |
| --------- | ------- |
| Accuracy  | **91%** |
| Precision | 0.9265  |
| Recall    | 0.9114  |
| F1-score  | 0.9107  |

### Observations

* Strong generalization
* Balanced precision & recall
* Accurate predictions on unseen images

---

## 🔍 Inference

The trained model can classify new flower images into one of 102 categories.

Basic workflow:

1. Load `model.pth`
2. Preprocess image
3. Predict class
4. Display result

---

## 🗂️ Project Structure

```
.
├── sorted.py
├── split.py
├── DenseNet201.ipynb
├── dataset/
│   ├── train/
│   └── val/
├── model.pth
└── README.md
```

---

## 🔧 Dependencies

Install requirements:

```bash
pip install tensorflow numpy matplotlib seaborn pillow scipy scikit-learn
```

If using PyTorch:

```bash
pip install torch torchvision
```

---

## 🚀 Key Features

* Transfer learning with DenseNet201
* Automated dataset organization
* Proper train/validation split
* High accuracy with few epochs
* Deployment-ready model

---

## 📌 Future Work

* Train longer for higher accuracy
* Add test dataset evaluation
* Grad-CAM visualization
* Flask / Streamlit deployment
* Mobile conversion (TFLite / ONNX)

---

## 📄 License

Academic and research use only.
