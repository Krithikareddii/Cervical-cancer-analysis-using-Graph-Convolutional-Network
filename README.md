# Cervical Cancer Analysis using Graph Convolutional Networks (GCN)

## Overview
This project presents a graph-based deep learning framework for automated cervical cell classification from Pap smear images. The proposed approach integrates a pre-trained Convolutional Neural Network (ResNet-50) for feature extraction with a Graph Convolutional Network (GCN) to model relational similarities between cervical cell samples.

Unlike traditional CNN-only approaches, this method leverages both visual features and structural relationships between similar cells, improving classification robustness and interpretability.

---

## Dataset
- Dataset: SIPaKMeD (Smartphone Image-based Pap smear Dataset)
- Total Images: 4,049 single-cell images
- Number of Classes: 5
  - Superficial / Intermediate
  - Parabasal
  - Koilocytotic
  - Dyskeratotic
  - Metaplastic

---

## Methodology

### 1. Preprocessing
- Image resizing to match model input requirements
- Pixel normalization
- Data augmentation for improved generalization
- Train-validation-test split

### 2. Feature Extraction
- Pre-trained ResNet-50 model (classification layer removed)
- Extraction of 2048-dimensional feature embeddings

### 3. Graph Construction
- L2 normalization of feature vectors
- Cosine similarity computation
- k-Nearest Neighbor (kNN) graph formation
- Nodes represent images; edges represent similarity scores

### 4. Graph Convolutional Network
- Two GCN layers
- ReLU activation in hidden layer
- Softmax activation for multi-class classification

### 5. Training and Evaluation
- Loss Function: Cross-Entropy Loss
- Optimizer: Adam
- Evaluation Metrics:
  - Accuracy
  - Precision
  - Recall
  - F1-Score

---

## Technologies Used

### Frameworks
- PyTorch
- PyTorch Geometric

### Libraries
- Torchvision
- NumPy
- Scikit-learn
- Matplotlib

---

## Key Contributions
- Integration of CNN-based feature extraction with graph-based relational learning
- Construction of similarity-driven kNN graph for cervical cell modeling
- Multi-class classification using GCN architecture
- Performance evaluation using standard classification metrics

---

## Future Enhancements
- External validation using clinical datasets
- Explainability integration (e.g., Grad-CAM)
- Deployment as a clinical decision support system
