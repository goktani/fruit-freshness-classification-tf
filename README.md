# 🍎 Fruit Freshness Classification: Fresh vs. Rotten

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview
This project is a Computer Vision solution designed to classify fruits as **Fresh** or **Rotten**. It leverages **Transfer Learning** with the **EfficientNetV2B0** architecture to achieve high accuracy with a lightweight model.

The primary goal was to build a **robust data pipeline** capable of handling real-world noisy data (corrupt images) and prioritizing food safety by maximizing recall on the "Rotten" class.

## 🚀 Key Features
* **Robust Data Pipeline:** Implemented a custom `tf.data` pipeline with error handling to detect and exclude corrupt/non-image files before training.
* **Transfer Learning:** Utilized `EfficientNetV2B0` (pre-trained on ImageNet) for feature extraction.
* **Two-Stage Training:**
    1.  **Feature Extraction:** Training only the classifier head.
    2.  **Fine-Tuning:** Unfreezing the base model with a very low learning rate (`1e-5`) for domain adaptation.
* **Zero-Risk Approach:** Achieved **1.00 Recall** for the "Rotten" class, ensuring no spoiled fruit is misclassified as fresh.

## 📊 Results
The model was evaluated on a distinct test set.

| Metric | Score | Note |
| :--- | :--- | :--- |
| **Accuracy** | **96%** | High overall performance |
| **Recall (Rotten)** | **1.00** | **Critical Safety:** Zero "Rotten" items missed (0 False Negatives). |
| **Precision (Fresh)** | **1.00** | **High Efficiency:** If predicted "Fresh", it is guaranteed to be fresh. |

> **Business Insight:** The model operates with a "Safety First" principle. It successfully captures 100% of the rotten fruits. While it is slightly conservative (classifying a few complex fresh fruits as rotten to be safe), it ensures that **no rotten fruit ever reaches the customer.**

## 🛠️ Technologies Used
* **Deep Learning:** TensorFlow, Keras (EfficientNetV2)
* **Data Processing:** Pandas, NumPy, tf.data API
* **Visualization:** Matplotlib, Seaborn
* **Image Handling:** PIL (Python Imaging Library)

## 📂 Dataset
The dataset consists of **Apple, Banana, and Strawberry** images, categorized into *Fresh* and *Rotten*.
* *Source:* [Kaggle - Fresh vs Rotten Fruit Images](https://www.kaggle.com/datasets/abdulrafeyyashir/fresh-vs-rotten-fruit-images)

## ⚙️ Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone (https://github.com/goktani/fruit-freshness-classification-tf.git)
    cd fruit-freshness-classification-tf
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the notebook:**
    Open the `.ipynb` file in Jupyter Notebook, Google Colab, or Kaggle Kernels to see the training process.

## 👨‍💻 Author
**Göktan İren**
* *Computer Engineer & Junior Presales Engineer*
* [LinkedIn Profile](https://www.linkedin.com/in/goktani/)
* [Kaggle Profile](https://www.kaggle.com/goktani)

---
*If you find this repository helpful, please give it a ⭐!*
