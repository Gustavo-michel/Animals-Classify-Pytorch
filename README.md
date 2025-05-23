# Animals-Classify-Pytorch

This project applies **Transfer Learning with PyTorch** to classify animal images using the **Animals-10** dataset from Kaggle. The complete pipeline is in the notebook, with support for training, evaluation and inference on new images. The trained model is available for download in `.pt` format.

---

## 📌 Overview

The `main.ipynb` notebook performs:

- Loading and preprocessing the Animals-10 dataset
- Using Transfer Learning with a pre-trained network (efficientnet_b0)
- Training and validation of the model
- Evaluation with metrics and visualization of results
- Inference in external images
- Saving and reusing the model (`.pt`)

---

## Dataset: Animals-10

The dataset used is the [Animals-10 (Alessio-Corrado)](https://www.kaggle.com/datasets/alessiocorrado99/animals10), containing **10 classes** of animals in over **26,000 images**:

- **Classes:** dog, cat, horse, spider, butterfly, chicken, sheep, cow, squirrel, elephant  
- The images have different sizes and are divided into folders (one for each class)

---

## Model Used: Transfer Learning with ResNet18

The base model is the pre-trained **efficientnet_b0**.

### Strategy:

- **Frozen layers:** The initial convolutional layers of efficientnet_b0 are kept frozen to preserve the learnings from ImageNet.
- **Final layer replaced:** The _head_ of the network (fully connected layer) is replaced by a layer with **10 outputs**, corresponding to the classes of Animals-10.

