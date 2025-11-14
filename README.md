# project_ML2_CIFAR10
# 🧠 CIFAR-10 Image Classification Project  
### 🔍 Comparing Custom CNNs and Transfer Learning Models

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange.svg)
![GoogleColab](https://img.shields.io/badge/Google%20Colab-Available-yellow.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)

---

## 1. 🏷️ Project Title & Short Description
A deep learning project comparing **custom CNN models** and **transfer learning architectures** to classify images from the CIFAR-10 dataset.

---

## 2. 🗂️ Dataset Description
We use the **CIFAR-10 dataset**, a classic benchmark for computer vision.

- **Source:** https://www.cs.toronto.edu/~kriz/cifar.html  
- **Images:** 60,000 (32×32 RGB)  
- **Train/Test:** 50,000 / 10,000  
- **Classes (10):** airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck  

**Notes:**
- Low resolution → challenging feature extraction  
- Some classes visually similar (cats vs dogs, ships vs airplanes)  
- Classes are balanced

---

## 3. 🎯 Research Goal / Question
**How does model complexity and pretraining affect accuracy on CIFAR-10?**  

We evaluated:

- 🧱 **Baseline CNN**  
- 🔧 **CNN+** (BatchNorm + GAP + Regularization)  
- 🚀 **MobileNetV2** (Transfer Learning)  
- 🧬 **NASNetMobile** (Transfer Learning)

---

## 4. 🛠️ Steps We Took

### **1️⃣ Data Preparation**
- Loaded CIFAR-10 via TensorFlow  
- Normalized pixel values  
- Applied data augmentation in CNN+

### **2️⃣ Baseline CNN**
- Two Conv2D + MaxPooling blocks  
- Flatten → Dense(64) → Dropout  
- Softmax output

### **3️⃣ CNN+ (Improved Model)**
- Added:
  - Batch Normalization  
  - Global Average Pooling  
  - L2 regularization + Dropout 0.5  
  - Data augmentation: flips, rotations, zoom, contrast  

### **4️⃣ Transfer Learning**
**MobileNetV2**  
- Resize to 160×160  
- Pretrained ImageNet base  
- Freeze → warm-up training → fine-tune top ~30 layers  

**NASNetMobile**  
- Resize to 224×224  
- Fine-tuning last ~20 layers  

### **5️⃣ Evaluation**
- Accuracy  
- Precision  
- Recall  
- F1-score  
- Confusion matrices  
- Visual accuracy comparison

---

## 5. 📊 Main Findings

- 🔹 **Baseline CNN:** ~0.685 accuracy  
- 🔹 **CNN+:** ~0.871 accuracy (big improvement with BN + GAP)  
- 🔹 **MobileNetV2:** **~0.897 (best result)**  
- 🔹 **NASNetMobile:** ~0.861 accuracy  
- 🧠 Transfer learning significantly improves generalization  
- 🎨 Augmentation and normalization are crucial for performance  
- 🔧 MobileNetV2 had the best trade-off between size and accuracy  

---

## 6. 💻 How to Reproduce the Project

### **📦 Installation**
Create a virtual environment (optional):

```bash
python -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Example `requirements.txt`:

```
tensorflow
numpy
matplotlib
scikit-learn
```


### ▶️ Running the Notebook
1. Open **CIFAR10.ipynb** in Google Colab  
2. Run all cells sequentially  
3. The notebook will:
   - Load and normalize CIFAR-10  
   - Train the baseline CNN, CNN+, MobileNetV2, and NASNetMobile  
   - Output accuracy and confusion matrices

⚙️ *Tip: Enable GPU runtime in Colab for faster training.*

---

## 7. 🚀 Next Steps / Ideas for Improvement

Future directions for enhancing this project include:

- Testing additional architectures (EfficientNet, ResNet50, Vision Transformers)  
- Using stronger data augmentation (Mixup, CutMix, Cutout)  
- Applying learning rate schedulers (OneCycle, CosineDecay)  
- Adding explainability tools like Grad-CAM  
- Deploying the best model using Streamlit or FastAPI  

---

## 8. 📁 Repository Structure
```
├── README.md
├── CIFAR10.ipynb               # Main Colab experiment notebook
├── presentation/               # Final project slides
├── results/                    # Accuracy plots, confusion matrices
└── requirements.txt            # Dependencies for running the project
```

---

## 9. 👥 Team Contributions

This project was developed collaboratively by:

- **Diogo Simões** — Implemented the model training in Colab, transfer learning pipelines  
- **Javier Garcia** — Model tuning, evaluation metrics, experiment iteration  
- **Chantal Silva** — Presentation design, documentation, README, workflow explanation  

✨ All team members contributed to interpreting results and discussing model performance.

---

## 🏁 Thank you!
Feel free to explore, run the notebook, or use this project as a reference for future deep learning work.




