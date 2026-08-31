# 🧠 Brain Tumor MRI Classification using CNN

A deep learning project that uses a **Convolutional Neural Network (CNN)** to classify brain MRI images into four categories: **Glioma, Meningioma, No Tumor, and Pituitary Tumor**.

The model is trained using TensorFlow/Keras on the **Brain Tumor MRI Dataset** available on Kaggle.

---

## 📌 Project Overview

Brain tumors are abnormal growths of cells within or around the brain. MRI is one of the primary imaging techniques used to examine brain abnormalities.

The objective of this project is to build a CNN-based image classification model capable of identifying the category of a brain MRI image.

### Classes

The model classifies MRI images into:

* **Glioma**
* **Meningioma**
* **No Tumor**
* **Pituitary**

---

## 📂 Dataset

The project uses the **Brain Tumor MRI Dataset** by Masoud Nickparvar.

**Dataset:** Brain Tumor MRI Dataset
**Source:** Kaggle
**License:** CC0 1.0

The dataset contains:

* **Training images:** 5,712
* **Testing images:** 1,311
* **Total images:** 7,023
* **Number of classes:** 4

---

## 🛠️ Technologies Used

* Python
* TensorFlow
* Keras
* OpenCV
* NumPy
* Matplotlib
* Scikit-learn
* Kaggle API

---

## 🧠 Model Architecture

A custom CNN architecture was implemented using TensorFlow/Keras.

```text
Input Image
512 × 512 × 3
      ↓
Conv2D (32 filters)
      ↓
Batch Normalization
      ↓
Max Pooling
      ↓
Conv2D (64 filters)
      ↓
Batch Normalization
      ↓
Max Pooling
      ↓
Conv2D (128 filters)
      ↓
Batch Normalization
      ↓
Max Pooling
      ↓
Flatten
      ↓
Dense (128)
      ↓
Dropout (0.2)
      ↓
Dense (64)
      ↓
Dropout (0.2)
      ↓
Dense (4)
      ↓
Softmax
```

### Model Parameters

The model contains approximately:

**63.08 million parameters**

The majority of these parameters come from the `Flatten → Dense(128)` layer.

---

## ⚙️ Data Preprocessing

The following preprocessing steps were applied:

1. MRI images were resized to **512 × 512 pixels**.
2. Pixel values were normalized from `[0, 255]` to `[0, 1]`.
3. Labels were inferred from the directory structure.
4. Images were loaded using TensorFlow's `image_dataset_from_directory`.

---

## 🏋️ Training

The model was trained using:

* **Optimizer:** Adam
* **Learning rate:** 0.0001
* **Loss function:** Sparse Categorical Crossentropy
* **Batch size:** 32
* **Maximum epochs:** 10
* **Early stopping:** Enabled
* **Dropout:** 0.2

### Training Results

| Epoch | Training Accuracy | Validation Accuracy |
| ----: | ----------------: | ------------------: |
|     1 |            63.73% |              22.88% |
|     2 |            79.07% |              30.89% |
|     3 |            85.70% |              72.62% |
|     4 |            88.67% |              89.24% |
|     5 |            91.69% |              91.53% |
|     6 |            92.84% |              91.23% |
| **7** |        **94.25%** |          **94.51%** |
|     8 |            95.41% |              91.91% |
|     9 |            95.79% |              92.75% |
|    10 |            96.75% |              94.43% |

### Best Validation Accuracy

The highest validation accuracy observed during training was:

> **94.51% — Epoch 7**

The model reached a final training accuracy of **96.75%** and validation accuracy of **94.43%** at Epoch 10.

---

## 📊 Model Performance

### Accuracy

* **Best validation accuracy:** 94.51%
* **Final training accuracy:** 96.75%
* **Final validation accuracy:** 94.43%

The relatively small gap between training and validation accuracy suggests that the model generalizes reasonably well on the provided validation/testing data, although further evaluation is required.

---

## 🔍 Single Image Prediction

The trained model can also classify an individual MRI image.

Example prediction output:

```text
Glioma       : 17.42%
Meningioma   : 46.48%
No Tumor     : 20.63%
Pituitary    : 15.46%
```

### Predicted Class

**Meningioma**

with a predicted probability of approximately **46.48%**.

The relatively low confidence indicates that this particular prediction is uncertain and should not be interpreted as a definitive diagnosis.

---

## 📈 Training Visualization

The project tracks both training and validation:

* Accuracy
* Loss

These curves can be used to analyze model convergence and potential overfitting.

---

## 🚀 Future Improvements

Several improvements can be made to the current model:

* [ ] Use a proper train/validation/test split
* [ ] Reduce image resolution to 224 × 224 for faster training
* [ ] Replace `Flatten()` with `GlobalAveragePooling2D()`
* [ ] Add data augmentation
* [ ] Add precision, recall and F1-score
* [ ] Generate a confusion matrix
* [ ] Experiment with class imbalance
* [ ] Implement transfer learning using EfficientNet/ResNet
* [ ] Add Grad-CAM for model interpretability
* [ ] Build a Streamlit interface for image upload and prediction
* [ ] Compare multiple CNN architectures

---

## ⚠️ Disclaimer

This project is developed for **educational and research purposes only**.

The model's predictions should **not be considered a medical diagnosis** or used as a substitute for evaluation by a qualified medical professional.

---

## 👨‍💻 Author

**Subham Badu**

B.Tech — Mining Engineering
National Institute of Technology, Rourkela

---

## ⭐ Acknowledgements

* TensorFlow/Keras for the deep learning framework
* Kaggle for dataset hosting
* Masoud Nickparvar for providing the Brain Tumor MRI Dataset
