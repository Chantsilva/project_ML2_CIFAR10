# CIFAR-10 Image Classification  
### Custom CNNs & Transfer Learning (MobileNetV2, NASNetMobile)

This project explores image classification on the CIFAR-10 dataset using both **custom CNN architectures** and **transfer learning** with pretrained ImageNet models.  
It demonstrates end-to-end deep learning workflow: preprocessing, model building, training, evaluation, and performance comparison.

---

## 📌 Project Overview
The goal of this project is to understand how architecture depth, regularization, and pretrained models impact performance on CIFAR-10 (60,000 images, 10 classes).  
Four models of increasing complexity were implemented:

1. **Baseline CNN** (from scratch)  
2. **CNN+** (deeper, regularized CNN)  
3. **MobileNetV2** (Transfer Learning + Fine-Tuning)  
4. **NASNetMobile** (Transfer Learning + Fine-Tuning)

---

## 📁 Project Structure
```text
CIFAR10_DLProject/
│
├── CIFAR10_DLProject.ipynb      # Notebook
├── README.md                    # Project documentation
└── CIFAR10_presentation.ppt     # Project presentation
```

---

## 🧠 Models Developed

### **1️⃣ Baseline CNN (~282K params)**
A simple model trained from scratch.
- Test Accuracy: **0.68**
- Strengths: stable learning, no major overfitting  
- Limitations: insufficient capacity for fine-grained classes

---

### **2️⃣ CNN+ (~360K params)**
Enhanced CNN with:
- Data augmentation  
- Batch Normalization  
- Dropout & L2 regularization  
- Deeper architecture  

**Result:**  
- Test Accuracy: **0.86**  
- Strong generalization and fast convergence

---

### **3️⃣ MobileNetV2 (Transfer Learning)**
Workflow:
- Warm-up phase (base frozen)
- Fine-tune last layers

**Result:**  
- **Best model: 0.8945 accuracy**  
- Very stable learning curves  
- Excellent precision/recall across all classes

---

### **4️⃣ NASNetMobile (Transfer Learning)**
- Warm-up + partial fine-tuning  
- Strong vehicle-class recognition (ship, truck, automobile)  

**Result:**  
- Test Accuracy: **0.8602**

---

## 📊 Performance Comparison

| Model | Test Accuracy |
|-------|---------------|
| Baseline CNN | 0.68 |
| CNN+ | 0.86 |
| MobileNetV2 (TL) | **0.8945** |
| NASNetMobile (TL) | 0.8602 |

👉 **MobileNetV2 is the top performer**, balancing model size, pretrained features, and generalization ability.

---

## 📈 Learning Curve Insights

- **Baseline CNN:** steady improvement, capacity-limited  
- **CNN+:** excellent generalization, well-separated classes  
- **MobileNetV2:** very high initial validation accuracy from pretrained features  
- **NASNetMobile:** strong warm-up but plateaued earlier than MobileNetV2  

---

## 🔧 Tools & Technologies
- Python  
- TensorFlow / Keras  
- NumPy  
- Matplotlib  
- Google Colab  

---

## 🧾 Key Skills Demonstrated
- CNN architecture design  
- Transfer learning & fine-tuning  
- Data augmentation & regularization  
- Evaluation metrics (accuracy, precision, recall, F1)  
- Confusion matrices & classification reports  
- Training curve interpretation  
- Model comparison & reasoning  

---

## 🏁 Final Takeaway
This project demonstrates how **architectural improvements** and **transfer learning** significantly boost performance in image classification tasks.  
While the **Baseline CNN** showed the limits of training from scratch, **CNN+** highlighted the impact of depth and augmentation.  
**MobileNetV2 achieved the highest accuracy and most stable training behavior**, showcasing the power of pretrained ImageNet models.

---
